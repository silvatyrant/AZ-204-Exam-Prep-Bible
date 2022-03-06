# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[API Management](https://docs.microsoft.com/en-us/azure/api-management/api-management-key-concepts)
--------------
### General
* [Authentication Policies](https://docs.microsoft.com/bs-cyrl-ba/azure/api-management/api-management-authentication-policies)

### Tech Tips
**Create new APIM service using AzureRM Powershell Module**
```powershell
New-AzApiManagement -Name "myapim" -ResourceGroupName "myResourceGroup" -Location "West US" -Organization "Contoso" -AdminEmail "admin@contoso.com"
```
:warning: This is a long-running operation. It can take between 30 and 40 minutes to create and activate an API Management service in this tier.

### High Availability / Scalability

### Notable Limits**

### Labs

**Skills Measured in Examination**
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)

```
Implement API Management
- create an APIM instance
- configure authentication for APIs
- define policies for APIs
```

**Relevant Tutorials**
