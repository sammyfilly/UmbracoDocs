# Release notes

In this section, we have summarized the changes to Umbraco Workflow released in each version. Each version is presented with a link to the [Workflow issue tracker](https://github.com/umbraco/Umbraco.Workflow.Issues/issues) showing a list of issues resolved in the release. We also link to the individual issues themselves from the detail.

If there are any breaking changes or other issues to be aware of when upgrading they are also noted here.

{% hint style="info" %}
If you are upgrading to a new major version, you can find information about the breaking changes in the [Version Specific Upgrade Notes](version-specific-upgrade-notes.md) article
{% endhint %}

## Release History

In this section, you can find the release notes for each version of Umbraco Workflow. For each major version, you can find the details about each release.

<details>

<summary>Version 12</summary>

#### [12.1.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F12.1.0) (September 5th 2023)

* Fixes bug where setting content review period to zero didn't exclude content from review [#28](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/28)
* Improves configuration options and handling for content reviews [#31](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/31)
* Fixes bug where variant workflows were not correctly scheduled [#42](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/42)
* Fixes bug when Swedish culture broke to differing unicode symbols when representing negative numbers [#44](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/44)
* Adds external reviewer option for content reviews
* Adds ability to schedule a publish workflow for both release and expire [#43](https://github.com/umbraco/Umbraco.Workflow.Issues/discussions/43)
* UX improvements for initiating workflows
* Removes 'Applies to' option from node-level workflow configuration as it was superceded by the equivalent global setting

* BREAKING CHANGE: `ContentReviewReminderEmailer.SendReviewReminders.reviews` parameter changes from `Dictionary<UserGroupPoco, List<ContentReviewConfigPoco>>` to `Dictionary<IWorkflowGroup, List<ContentReviewConfigPoco>>`, which in turn changes the type of the `SentEntities` property in `WorkflowContentReviewsEmailNotificationsSendingNotification` and `WorkflowContentReviewsEmailNotificationsSentNotification`. `UserGroupPoco` implements `IWorkflowGroup`, but contains properties not present on the interface. These can be accessed by casting to the implemented type.

#### [12.0.1](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F12.0.1) (August 1st 2023)

* Adds Dutch localization [#23](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/23)
* Additional localization cleanup and improvements
* Fixes Swagger generation error [#29](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/29)
* Updates migration to avoid constraint errors [#35](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/35)

#### [12.0.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F12.0.0) (June 29th 2023)

* Fixes filtering workflows initiated by the current user when FlowType is Exclude [#25](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/25)
* Ensures Document Type configuration for Content Reviews displays the license overlay on non-licensed installs [#24](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/24) 
* Adds configuration option to allow administrators to edit content in an active workflow, regardless of content lock settings [#18](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/18)
* Fixes possible divide-by-zero error in chart generation
* Ensure workflow activity chart only shows stats box when stats exist

</details>

<details>

<summary>Version 11</summary>

#### [11.3.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.3.0) (September 5th 2023)

* Fixes bug where setting content review period to zero didn't exclude content from review [#28](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/28)
* Improves configuration options and handling for content reviews [#31](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/31)
* Fixes bug where variant workflows were not correctly scheduled [#42](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/42)
* Fixes bug when Swedish culture broke to differing unicode symbols when representing negative numbers [#44](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/44)
* Adds external reviewer option for content reviews
* Adds ability to schedule a publish workflow for both release and expire [#43](https://github.com/umbraco/Umbraco.Workflow.Issues/discussions/43)
* UX improvements for initiating workflows
* Removes 'Applies to' option from node-level workflow configuration as it was superceded by the equivalent global setting
* Aligns embedded licensing UI with Umbraco.Licenses

* BREAKING CHANGE: `ContentReviewReminderEmailer.SendReviewReminders.reviews` parameter changes from `Dictionary<UserGroupPoco, List<ContentReviewConfigPoco>>` to `Dictionary<IWorkflowGroup, List<ContentReviewConfigPoco>>`, which in turn changes the type of the `SentEntities` property in `WorkflowContentReviewsEmailNotificationsSendingNotification` and `WorkflowContentReviewsEmailNotificationsSentNotification`. `UserGroupPoco` implements `IWorkflowGroup`, but contains properties not present on the interface. These can be accessed by casting to the implemented type.

#### [11.2.3](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.2.3) (August 1st 2023)

* Adds Dutch localization [#23](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/23)
* Additional localization cleanup and improvements
* Updates migration to avoid constraint errors [#35](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/35)

#### [11.2.2](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.2.2) (June 29th 2023)

* Fixes filtering workflows initiated by the current user when FlowType is Exclude [#25](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/25)
* Ensures Document Type configuration for Content Reviews displays the license overlay on non-licensed installs [#24](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/24) 
* Adds configuration option to allow administrators to edit content in an active workflow, regardless of content lock settings [#18](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/18)
* Fixes possible divide-by-zero error in chart generation
* Ensure workflow activity chart only shows stats box when stats exist

#### [11.2.1](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.2.1) (May 23rd 2023)

* Ensure all Document Type properties are available when configuring conditional workflow stages
* Ensure license prompt is displayed only when install is unlicensed
* Fixes bug where default approval threshold wasn't set correctly when adding new workflow stages
* Fixes bug where querying published nodes for content reviews resulted in an ambiguous column name in the generated query [#17](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/17)
* Fixes bug where users were not persisted as approval group members if they were assigned as part of group creation   

#### [11.2.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.2.0) (May 9th 2023)

* **FEATURE** => Introduces [approval thresholds](getting-started/approval-thresholds.md).

#### [11.1.2](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.1.2) (April 18th 2023)

* **FEATURE** => Introduces optional configuration for mandatory comments
* **FEATURE** => Modifies content lock to allow edits until the first workflow action is completed
* Ensure notifications inheriting from ObjectNotification have a public Target property [#13](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/13)
* Improve UI notification when publish fails on workflow completion
* Improve logged messages when publish fails on workflow completion
* Renames `/App_Plugins/Backoffice` to `/App_Plugins/backoffice` for Linux file path resolution [#14](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/14)
* Ensure the `canEdit` flag is set correctly when the Workflow application state changes
* Ensure canceled workflows are never marked as actioned by admin when canceled by the original change requestor, regardless of their admin status

#### [11.1.1](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.1.1) (March 8th 2023)

* Fixes bug in workflow detail overlay [#12](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/12)

#### [11.1.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F11.1.0) (March 7th 2023)

* **FEATURE** => History cleanup and retention policies
* Fixes tree collision issue when multiple trees share class names [#11](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/11)
* Ensure the version number is included in the package manifest
* Improve UI/UX in submit workflow component
* Ensure notification emails are sent when a task is rejected [#9](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/9)
* Remove `async void` signatures
* Extends valid local license environment names
* Ensure signalR hub is not re-initialized once running

</details>

<details>

<summary>Version 10</summary>

#### [10.3.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.3.0) (September 5th 2023)

* Fixes bug where setting content review period to zero didn't exclude content from review [#28](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/28)
* Improves configuration options and handling for content reviews [#31](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/31)
* Fixes bug where variant workflows were not correctly scheduled [#42](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/42)
* Fixes bug when Swedish culture broke to differing unicode symbols when representing negative numbers [#44](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/44)
* Adds external reviewer option for content reviews
* Adds ability to schedule a publish workflow for both release and expire [#43](https://github.com/umbraco/Umbraco.Workflow.Issues/discussions/43)
* UX improvements for initiating workflows
* Removes 'Applies to' option from node-level workflow configuration as it was superceded by the equivalent global setting
* Aligns embedded licensing UI with Umbraco.Licenses

* BREAKING CHANGE: `ContentReviewReminderEmailer.SendReviewReminders.reviews` parameter changes from `Dictionary<UserGroupPoco, List<ContentReviewConfigPoco>>` to `Dictionary<IWorkflowGroup, List<ContentReviewConfigPoco>>`, which in turn changes the type of the `SentEntities` property in `WorkflowContentReviewsEmailNotificationsSendingNotification` and `WorkflowContentReviewsEmailNotificationsSentNotification`. `UserGroupPoco` implements `IWorkflowGroup`, but contains properties not present on the interface. These can be accessed by casting to the implemented type.

#### [10.2.3](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.2.3) (August 1st 2023)

* Adds Dutch localization [#23](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/23)
* Additional localization cleanup and improvements
* Updates migration to avoid constraint errors [#35](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/35)

#### [10.2.2](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.2.2) (June 29th 2023)

* Fixes filtering workflows initiated by the current user when FlowType is Exclude [#25](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/25)
* Ensures Document Type configuration for Content Reviews displays the license overlay on non-licensed installs [#24](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/24) 
* Adds configuration option to allow administrators to edit content in an active workflow, regardless of content lock settings [#18](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/18)
* Fixes possible divide-by-zero error in chart generation
* Ensure workflow activity chart only shows stats box when stats exist
    
#### [10.2.1](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.2.1) (May 23rd 2023)

* Ensure all Document Type properties are available when configuring conditional workflow stages
* Ensure license prompt is displayed only when install is unlicensed
* Fixes bug where default approval threshold wasn't set correctly when adding new workflow stages
* Fixes bug where querying published nodes for content reviews resulted in an ambiguous column name in the generated query [#17](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/17)
* Fixes bug where users were not persisted as approval group members if they were assigned as part of group creation

#### [10.2.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.2.0) (May 9th 2023)

* **FEATURE** => Introduces [approval thresholds](getting-started/approval-thresholds.md)

#### [10.1.2](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.1.2) (April 18th 2023)

* **FEATURE** => Introduces optional configuration for mandatory comments
* **FEATURE** => Modifies content lock to allow edits until the first workflow action is completed
* Ensure notifications inheriting from ObjectNotification have a public Target property [#13](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/13)
* Improve UI notification when publish fails on workflow completion
* Improve logged messages when publish fails on workflow completion
* Renames `/App_Plugins/Backoffice` to `/App_Plugins/backoffice` for Linux file path resolution [#14](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/14)
* Ensure the `canEdit` flag is set correctly when the Workflow application state changes
* Ensure canceled workflows are never marked as actioned by admin when canceled by the original change requestor, regardless of their admin status

#### [10.1.1](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.1.1) (March 8th 2023)

* Fixes bug in workflow detail overlay [#12](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/12)

#### [10.1.0](https://github.com/umbraco/Umbraco.Workflow.Issues/issues?q=is%3Aissue+is%3Aclosed+label%3Arelease%2F10.1.01) (March 7th 2023)

* **FEATURE** => History cleanup and retention policies
* Fixes tree collision issue when multiple trees share class names [#11](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/11)
* Ensure the version number is included in the package manifest
* Improve UI/UX in submit workflow component
* Ensure notification emails are sent when a task is rejected [#9](https://github.com/umbraco/Umbraco.Workflow.Issues/issues/9)
* Remove `async void` signatures
* Extends valid local license environment names
* Ensure signalR hub is not re-initialized once running

</details>
