# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure CDN (Content Delivery Network)](https://docs.microsoft.com/en-us/azure/cdn/cdn-overview)
------------------------------------
### General

**How it works**
1. A user (Alice) requests a file (also called an asset) by using a URL with a special domain name, such as <endpoint name>.azureedge.net. This name can be an endpoint hostname or a custom domain. The DNS routes the request to the best performing POP location, which is usually the POP that is geographically closest to the user.

2. If no edge servers in the POP have the file in their cache, the POP requests the file from the origin server. The origin server can be an Azure Web App, Azure Cloud Service, Azure Storage account, or any publicly accessible web server.

3. The origin server returns the file to an edge server in the POP.

4. An edge server in the POP caches the file and returns the file to the original requestor (Alice). The file remains cached on the edge server in the POP until the time-to-live (TTL) specified by its HTTP headers expires. If the origin server didn't specify a TTL, the default TTL is seven days.

5. Additional users can then request the same file by using the same URL that Alice used, and can also be directed to the same POP.

6. If the TTL for the file hasn't expired, the POP edge server returns the file directly from the cache. This process results in a faster, more responsive user experience.
   
     <img src="assets/cdn-overview.png" width=55%></img>

  * CDN Providers
    * Microsoft (Standard)
    * Akamai (Standard)
    * Verizon (Standard and Premium)
  * CDN is decentralised, but metadata will reside in region of resource group.



### Tech Tips

### High Availability / Scalability

### Notable Limits**

|Resource|Limit|
|---|---|
|Azure Content Delivery Network profiles		|25|
|Content Delivery Network endpoints per profile	|25|
|Custom domains per endpoint					|25|
|Maximum origin group per profile				|10|
|Maximum origin per origin group				|10|
|Maximum number of rules per CDN endpoint		|25|
|Maximum number of match conditions per rule	|10|
|Maximum number of actions per rule				|5 |



### Labs

### Related Services
