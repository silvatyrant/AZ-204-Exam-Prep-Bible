# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[App Service](https://docs.microsoft.com/en-us/azure/app-service)
-------------

## General
**App Service Plan Types**
| Consumption plan (serverless) | Premium plan | Dedicated plan|
| --- | --- | --- |
| | | |
 

## Tech Tips


## High Availability / Scalability

* Traffic Manager
* [Best Practices](https://docs.microsoft.com/en-us/azure/architecture/checklist/resiliency-per-service#app-service)



**Deployment Slots**
  * [Custom warm-up options](https://docs.microsoft.com/en-us/azure/app-service/deploy-staging-slots#Warm-up):
     1. <applicationInitialization\> tag in web.config [(more info)](https://ruslany.net/2017/11/most-common-deployment-slot-swap-failures-and-how-to-fix-them/)
     2. Add the following to app settings:
```
	WEBSITE_SWAP_WARMUP_PING_PATH
 	WEBSITE_SWAP_WARMUP_PING_STATUSES
```
**[Swapped vs. Unswapped Configuration](https://docs.microsoft.com/en-us/azure/app-service/deploy-staging-slots)**

| Swapped | Not Swapped |
| --- | --- |
|General settings, such as framework version, 32/64-bit, web sockets |Publishing endpoints                                 |
|App settings (can be configured to stick to a slot)                 |Custom domain names                                  |
|Connection strings (can be configured to stick to a slot)           |Non-public certificates and TLS/SSL settings         |
|Handler mappings                                                    |Scale settings                                       |
|Public certificates                                                 |WebJobs schedulers                                   |
|WebJobs content                                                     |IP restrictions                                      |
|Hybrid connections *                                                |Always On                                            |
|Service endpoints *                                                 |Diagnostic settings                                  |
|Azure Content Delivery Network *                                    |Cross-origin resource sharing (CORS)                 |
|Path mappings                                                       |Virtual network integration                          |
|																	 |Managed identities								   |
|																	 |Settings that end with the suffix _EXTENSION_VERSION |





## [Notable Limits](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/azure-subscription-service-limits#app-service-limits)
|Criteria|Free|Shared|Basic|Standard|Premium|Isolated (ASE)|
|---|---|---|---|---|---|---|
|Max apps in ASP| 10 | 100| * | * | * | * |

* If you scale an app in the Basic tier to two instances, you have 350 concurrent connections for each of the two instances. For Standard tier and above, there are no theoretical limits to web sockets, but other factors can limit the number of web sockets. For example, maximum concurrent requests allowed (defined by maxConcurrentRequestsPerCpu) are: 7,500 per small VM, 15,000 per medium VM (7,500 x 2 cores), and 75,000 per large VM (18,750 x 4 cores).
* The maximum IP connections are per instance and depend on the instance size: 1,920 per B1/S1/P1V3 instance, 3,968 per B2/S2/P2V3 instance, 8,064 per B3/S3/P3V3 instance.
* App Service Isolated SKUs can be internally load balanced (ILB) with Azure Load Balancer, so there's no public connectivity from the internet. As a result, some features of an ILB Isolated App Service must be used from machines that have direct access to the ILB network endpoint.
* Run custom executables and/or scripts on demand, on a schedule, or continuously as a background task within your App Service instance. Always On is required for continuous WebJobs execution. There's no predefined limit on the number of WebJobs that can run in an App Service instance. There are practical limits that depend on what the application code is trying to do.

## Labs
**Skills Measured in Examination**
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)
```
Create Azure App Service Web Apps
- create an Azure App Service Web App
- enable diagnostics logging
- deploy code to a web app
- configure web app settings including SSL, API settings, and connection strings
- implement autoscaling rules including scheduled autoscaling and autoscaling by
operational or system metrics
```
**Relevant Tutorials**
[

## Related Services
