---
title: CreateDefaultEmailTemplatesTask
description: API reference for CreateDefaultEmailTemplatesTask in Umbraco Commerce
---
## CreateDefaultEmailTemplatesTask

```csharp
public class CreateDefaultEmailTemplatesTask : 
    PipelineTaskWithTypedArgsBase<InitStorePipelineArgs, Store>
```

**Inheritance**

* class [PipelineTaskWithTypedArgsBase&lt;!0,!1&gt;](../../umbraco-commerce-common/umbraco-commerce-common-pipelines/pipelinetaskwithtypedargsbase-2.md)

**Namespace**
* [Umbraco.Commerce.Core.Pipelines.Store.Tasks](README.md)

### Constructors

#### CreateDefaultEmailTemplatesTask

```csharp
public CreateDefaultEmailTemplatesTask(IEmailTemplateService emailTemplateService)
```


### Methods

#### Execute

```csharp
public override PipelineResult<Store> Execute(InitStorePipelineArgs args)
```


<!-- DO NOT EDIT: generated by xmldocmd for Umbraco.Commerce.Core.dll -->
