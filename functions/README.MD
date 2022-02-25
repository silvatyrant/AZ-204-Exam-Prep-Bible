# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure Functions](https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview)
----------

[![Azure Functions Overview Video - Source YouTube](https://img.youtube.com/vi/8-jz5f_JyEQ/0.jpg)](https://youtu.be/8-jz5f_JyEQ)

### General

[**Hosting Plans**](https://docs.microsoft.com/en-us/azure/azure-functions/functions-scale)
* Consumption (serverless) plan
  * Default plan.
  * Auto-scale out.
  * Pay-as-you-run.
* [Functions Premium](https://docs.microsoft.com/en-us/azure/azure-functions/functions-premium-plan?tabs=azurecli)
  * SKU starts with "E" eg. `EP1` (for Elastic Plan).
  * VNet capability.
  * No cold starts. [Pre-warmed](https://docs.microsoft.com/en-us/azure/azure-functions/functions-premium-plan?tabs=azurecli#pre-warmed-instances) & [Always ready](https://docs.microsoft.com/en-us/azure/azure-functions/functions-premium-plan?tabs=azurecli#always-ready-instances) instances.
  * 1, 2 and 4 core instances.
  * [Unlimited execution duration](https://docs.microsoft.com/en-us/azure/azure-functions/functions-premium-plan?tabs=azurecli#longer-run-duration), with 60 minutes guaranteed.
  * Scale dynamically based on incoming events.
  * Custom host OS image.
* Dedicated [(App Service) plan](../appservice/README.MD#general)
  * SKU starts with "P" eg. `P1V2` (for Premium Plan).
  * Won't scale dynamically and may increase costs.
* ASE (App Service Environment)
* Kubernetes (Direct or Azure Arc)

**Anatomy of Functions**

1. Function App
   * A function app is comprised of one or more individual functions that are managed, deployed, and scaled together. A logical collection of functions.
   * Functions within a Function App share a pricing plan, deployment method and runtime version. 

2. Bindings & Triggers
   * Triggers
     * Cause the function to be executed.
     * Exactly one trigger per function.
     * Triggers have data associated with it.
   * [Bindings](https://docs.microsoft.com/en-us/azure/azure-functions/add-bindings-existing-function?tabs=csharp)
     * How functions integrate with other Azure services.
     * Can be input (parameters), output bindings or both (`inout`). This is known as the `direction`.


    Example `function.json`:
     ```json
     {
         "dataType": "binary",
         "type": "httpTrigger",
         "name": "req",
         "direction": "in"
     }
     ```

    Supported Bindings 
    | Azure Service* | 1.x | >= 2.x | Trigger | Input | Output |
    |---|---|---|---|---|---|
    |[Blob Storage](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-storage-blob)| :heavy_check_mark: |  :heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|
    |[Azure Cosmos DB](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-cosmosdb-v2) | :heavy_check_mark: | :heavy_check_mark:| :heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:|
    |[Azure SQL](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-azure-sql)| |:heavy_check_mark:| |:heavy_check_mark:|:heavy_check_mark:|
    |[Event Grid](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-event-grid)|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:| |:heavy_check_mark:|
    |[Event Hubs](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-event-hubs)|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:| |:heavy_check_mark:|
    |[Queue Storage](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-storage-queue)|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:| |:heavy_check_mark:|
    |[Service Bus](https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-service-bus)|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:| |:heavy_check_mark:|
    |Table Storage|:heavy_check_mark:|:heavy_check_mark:| |:heavy_check_mark: |:heavy_check_mark:|
    |Timer|:heavy_check_mark:|:heavy_check_mark:|:heavy_check_mark:| | |
    **\*** Only Azure services relevant to AZ-204 Exam Skills Measured (see [here](https://docs.microsoft.com/en-us/azure/azure-functions/functions-triggers-bindings?tabs=csharp#supported-bindings) for full table).  

3. Folder Structure and Files
   * `host.json` - Hosted in the function root directory and contains runtime-specific config. 
   * `function.json`
   * `local.settings.json` - Contains all the app settings for the Function App, but for testing locally. These configs be overridden when running in Azure.
   * `./bin` - Hosted in root and contains any libary packages that the function requires.

  




**Durable Functions**

  
**[Custom Handlers](https://docs.microsoft.com/en-us/azure/azure-functions/functions-custom-handlers)**

### Tech Tips

### High Availability / Scalability

### Notable Limits**

### Labs
**Skills Measured in Examination**
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)

```
Implement Azure functions
- create and deploy Azure Functions apps
- implement input and output bindings for a function
- implement function triggers by using data operations, timers, and webhooks
- implement Azure Durable Functions
- implement custom handlers
```

 * [Create durable function in Python](https://docs.microsoft.com/en-us/azure/azure-functions/durable/quickstart-python-vscode)
 * [Create a Go or Rust function in Azure using Visual Studio Code](https://docs.microsoft.com/en-us/azure/azure-functions/create-first-function-vs-code-other?tabs=go%2Clinux)

See serverlesslibrary.net for Function tutorials and code samples.

### Related Services
 [Azure App Service](../appservice/README.MD) | [Azure SQL Database](../sqldb/README.MD) | [Azure Blob Storage](../storage/README.MD) | [Azure Logic Apps](../logicapps/README.MD)