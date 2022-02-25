# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
Cosmos DB
---------
### General

### Tech Tips

### High Availability / Scalability
* [Best Practices](https://docs.microsoft.com/en-us/azure/architecture/checklist/resiliency-per-service#cosmos-db)
  * Replicate the DB across regions.
  * Cosmos DB can have one write and multiple read regions.
  * If the write region fails, you can read from another replica.


### Notable Limits**

### Labs
**Skills Measured in Examination**
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)

```
Develop solutions that use Cosmos DB storage
- select the appropriate API and SDK for a solution
- implement partitioning schemes and partition keys
- perform operations on data and Cosmos DB containers
- set the appropriate consistency level for operations
- manage change feed notifications
```