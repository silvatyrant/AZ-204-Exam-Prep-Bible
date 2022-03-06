# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure Logic Apps](https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-overview)
------------------

### General
**B2B Integration**
 * [Enterprise Integration Pack (EIP)](https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-enterprise-integration-overview)
   * Make use of integration accounts, which are cloud-based containers within Azure which simplify how you store, manage and use B2B artifacts for B2B comms.
     * Trading partners
     * Agreements
     * Maps
     * Schemas
     * Certificates
   * Run custom code from your workflows using built-in code execution operations with Azure Functions.
   * Use enterprise integration connectors that support standards such as EDI and EAI.
    </br>
    Steps to start building Logic App B2B workflows:
    <img src=".\assets\EIP_workflow.png"></img>

* Integration Accounts
  |Tier|Description|SLA|
  |---|---|---|
  |Basic| For scenarios where you want only message handling or to acta as a small business partner that has a trading parnter relationship with a larger business entity.| Supported by the Logic Apps SLA|
  |Standard|For scenarios where you have more complex B2B relationships and increased numbers of entities that you must manage. | Supported by the Logic Apps SLA|
  |Free|For exploratory scenarios, not production. Limited availability in regions, throughput and usage. The free tier is only for public regions in Azure. eg West US or SE Asia but not Azure China 21Vianet or Azure Government.|***Not*** supported by the Logic Apps SLA. |
### Tech Tips
Downgrading (or upgrading) an Integration Account:
```azure-cli
az resource update --resource-group FabrikamIntegration-RG --resource-type Microsoft.Logic/integrationAccounts --name Fabrikam-Integration --subscription XXXXXXXXXXXXXXXXX --set sku.name=Basic
```
### High Availability / Scalability

### Notable Limits**


### Labs

