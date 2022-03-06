# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure Monitor (and other instrumenting)](https://docs.microsoft.com/en-us/azure/azure-monitor/overview)
-----------------

### General
**Azure Monitor**
 * Data Collector packages for custom metrics

**Azure Service Health**
 * Azure Service Health for notification of service interruption in AZ


**[Azure Application Insights](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview)**
 * [Third-party dependency tracking requires that we store two properties in the DB](https://docs.microsoft.com/en-us/azure/azure-monitor/app/custom-operations-tracking):
   * Telemetry.Context.Operation.Id
   * Telemetry.Id

### Tech Tips

### High Availability / Scalability

### Notable Limits**

### Labs
**Skills Measured in Examination**
Source: Exam AZ-204: Developing Solutions for Microsoft Azure - Skills Measured (updated March 26 2021)

Section: Instrument solutions to support monitoring
and logging
- [ ] Configure an app or service to use Application Insights
- [ ] Analyze and troubleshoot solutions by using Azure Monitor
- [ ] Implement Application Insights web tests and alerts

[Set up Azure Monitor for your Python application](https://docs.microsoft.com/en-us/azure/azure-monitor/app/opencensus-python)