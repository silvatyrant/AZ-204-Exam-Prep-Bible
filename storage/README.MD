# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure Storage](https://docs.microsoft.com/en-us/azure/storage/common/storage-account-overview)
-----------------
### General
**Storage Types**
* Blob Storage
  * Page
  * Append
  * Block
* Table Storage
* File Storage
  * Network attached storage
* Queue Storage
  * 64kB limit per message.
  * Less robust than [Service Bus queues](../servicebus/README.MD).
  * Queue size limited to storage account capacity.

### Tech Tips
* Blob event triggers not instantaneous - Not to be used for time-sensitive applications.
  
### High Availability / Scalability

**LRS - Locally Redundant Storage**
<img src="./assets/LRS-locally-redundant-storage.png" width=28%>

**GRS - Geo-Redundant Storage (and Read Access GRS)**
<img src="./assets/GRSorRAGRS-geo-redundant-storage.png" width=75%>

**ZRS - Zone Redundant Storage**
<img src="./assets/ZRS-zone-redundant-storage.png"  width=50%>

**GZRS - Geo-Zone Redundant Storage**
<img src="./assets/GZRS-geo-zone-redundant-storage.png"  width=80%>

### Notable Limits**
* Max of 5 PiB per storage account.
* Max blob size is 4.75 Terabytes.
* Blob storage limitation is 20000 IOPS (if throughput is > limit, consider creating additional account(s)).

### Labs

**Skills Measured in Examination**
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)

```
Develop solutions that use blob storage
- move items in Blob storage between storage accounts or containers
- set and retrieve properties and metadata
- perform operations on data by using the appropriate SDK
- implement storage policies, and data archiving and retention

Implement user authentication and authorization
-create and implement shared access signatures
```

**Relevant Tutorials**

### Related Services
[Azure VM](../azurevm/README.MD) | [Azure Service Bus](../servicebus/README.MD) | [Azure Functions](../functions/README.MD) | [Azure AD](../azuread/README.MD) | [Azure Key Vault](../keyvault/README.MD)