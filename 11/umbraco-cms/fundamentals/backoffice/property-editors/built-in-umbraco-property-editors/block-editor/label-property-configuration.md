# Configuring Block Editor Label Properties

When configuring a block, the label property allows you to define a label for the appearance of the Block in the editor. The label can use AngularJS template string syntax to display values of properties. Example: `My Block {{myPropertyAlias}}` will be shown as: `My Block FooBar`.

You can also use more advanced expressions using AngularJS filters. Example: `{{myPropertyAlias | limitTo:100}}` or for a property using the Richtext editor `{{myPropertyAlias | ncRichText | truncate:true:100}}`.

It is also possible to use properties from the settings model by using `{{$settings.propertyAlias}}`.

In some cases, you might want to create a fallback label. This can be achieved using the following format: `{{myProperty || $contentTypeName}}`.

This example will show the name of the ElementType when the value of `myProperty` is not defined.

## Useful Angular filters

As well as the [default AngularJS filters](https://docs.angularjs.org/api/ng/filter), Umbraco ships with additional filters which are useful for setting the Label field of Block editors.

| Filter                                                                                             | Description                                             | Property type               | Parameters                                                                                                                                                                                                    |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------------------- | --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ncNodeName                                                                                         | Gets the name of a node                                 | Umbraco node                |                                                                                                                                                                                                               |
| ncRichText                                                                                         | Strips HTML                                             | Richtext editor             |                                                                                                                                                                                                               |
| mediaItemResolver                                                                                  | Retrieves a Media Item object                           | Media Picker                |                                                                                                                                                                                                               |
| [limitTo](https://docs.angularjs.org/api/ng/filter/limitTo)                                        | AngularJS native truncate                               | String                      | n: maximum length of the string                                                                                                                                                                               |
| [truncate](https://apidocs.umbraco.com/v10/ui/#/api/umbraco.filters.filter:truncate)               | Umbraco's richer truncate function                      | String                      | <p>wordwise: boolean to indicate whether to truncate a string mid-word or not<br>max: maximum length of the string<br>tail (optional): string to indicate a truncated string, "<code>…</code>" by default</p> |
| [umbWordLimit](https://apidocs.umbraco.com/v10/ui/#/api/umbraco.filters.filter:umbWordLimit)       | Truncates to a number of words (rather than characters) | String                      | n: maximum number of words in string                                                                                                                                                                          |
| [umbCmsTitleCase](https://apidocs.umbraco.com/v10/ui/#/api/umbraco.filters.filter:umbCmsTitleCase) | Converts a string to title case                         | String                      |                                                                                                                                                                                                               |
| [umbCmsJoinArray](https://apidocs.umbraco.com/v10/ui/#/api/umbraco.filters.filter:umbCmsJoinArray) | Joins an array into one string                          | Array (of string or object) | <p>separator: string used to join values together, e.g. "<code>,</code> "<br>prop (optional): string key indicating which property to join when used on an array of objects</p>                               |

### Example: mediaItemResolver

This is how you could use the filter for a Media Picker of the type `Umbraco.MediaPicker3` with multiple images:

```
{{(myPropertyAlias[0].mediaKey | mediaItemResolver).name}}
```

The `mediaKey` is a Guid like `c7a4526c-6b32-4665-a047-5b3e7256d973`.

For the Media Name, the same could be achieved using `ncNodeName` like shown below:

{% code overflow="wrap" %}
```
{{myPropertyAlias[0].mediaKey ? ('umb://media/'+myPropertyAlias[0].mediaKey.split("-").join("") | ncNodeName) : 'No Image' }}
```
{% endcode %}

The `ncNodeName` value expects a UDI like `umb://media/c7a4526c6b324665a0475b3e7256d973`.

### Custom filters

If the filters do not suit your needs, you can create custom filters by creating a plugin in `App_Plugins` and adding a filter module.

An example `package.manifest` file is:

```json
{
    "name": "MyFilters",
    "version": "1.0.0",
    "allowPackageTelemetry": false,
    "javascript": [
        "/App_Plugins/MyFilters/myFilter.filter.js"
    ]
}
```

With `myFilter.filter.js` containing:

```javascript
angular.module("umbraco.filters").filter("myFilter", function () {
  return function (input, parameter1, parameter2, etc) {
      // Apply any custom logic to modify the output value and return a string
      return `My filter says: "${input}"`;
  }
});
```

## Special variables

| Variable           | Description                                                                |
| ------------------ | -------------------------------------------------------------------------- |
| `$index`           | The 1-based index of this block item in the current block list             |
| `$contentTypeName` | The name of the Element Type used for the Block                            |
| `$settings`        | Provides access to the settings model for the block (if configured)        |
| `$layout`          | Provides access to the layout model for the block (columnSpan and rowSpan) |
