# AZ-204: Developing Solutions for Microsoft Azure - Exam Prep Notes

<div style="text-align: right"> <a href="..\README.MD">Index</a> | <a href="..\RESOURCES.MD">Resources</a> </div>

----
[Azure Service Bus](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview)
-----------------
### General

* Fully-managed enterprise-level messaging bus.
* Queues and topics.
* More robust than Storage queues. [(see comparison)](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-azure-and-service-bus-queues-compared-contrasted)
* [How to know which messaging service to choose](https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services)

### Tech Tips
**[Subscribing to topic on Service Bus using .NET SDK](https://www.c-sharpcorner.com/article/azure-service-bus-topic-and-subscription-pub-sub)**
```csharp
class Program
    {  
        // Instantiate subscriptionClient
        static ISubscriptionClient subscriptionClient;

        // Main function
        static void Main(string[] args)
        {  
              // Declare variables
              string sbConnectionString = "Endpoint=sb://mobilerecharge.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=KVb9ubc9XaV0dT/1dMjW9CzPWvA/JGvVvUZ64U21IBI=";  
              string sbTopic = "offers";  
              string sbSubscription = "akki5677";  
              try  
                    { 
                    // Assign object to subscriptionClient
                    subscriptionClient = new SubscriptionClient(sbConnectionString, sbTopic, sbSubscription);
                    // Declare messageHandlerOptions (MaxConcurrentCalls and AutoComplete)
                    var messageHandlerOptions = new MessageHandlerOptions(ExceptionReceivedHandler)
                    {
                        MaxConcurrentCalls = 1,
                        AutoComplete = false  
                    };
                    // Start processing messages
                    subscriptionClient.RegisterMessageHandler
                        (
                            ReceiveMessagesAsync, 
                            messageHandlerOptions
                        );
                    }
              // In the event of any exceptions, print exception to stdout
              catch (Exception ex)
              {
                  Console.WriteLine(ex.Message);
              }
              finally
              {
                  Console.ReadKey();
                  subscriptionClient.CloseAsync();
              }
              ...
        }
    }
```
  Supports 3 filter conditions for subscribers:
  * **Correlation Filters**
    * A `CorrelationFilter` holds a set of conditions that are matched against one or more of an arriving message's user or system properties.
    * Common use to match against `CorrelationId` property, but can also be used to match against `ContentType`, `Label`, `MessageId`, `ReplyTo`, `ReplyToSessionId`, `SessionId`, `To`.
    * Can also be used to match user-defined properties.
    * Case-sensitive for string expressions.
    * If multiple conditions are set, all must be matched.
  * **Boolean Filters**
    * The `TrueFilter` and `FalseFilter`either cause all arriving messages (true) or none of the arriving messages (false) to be selected for the filter.
  * **SQL Filters**
    * A `SQLFilter` holds a SQL-like conditional expression that is evaluted in the broker against the arriving messages' user-defined properties and system properties.
    * All system properties must be prefixed with `sys.` in the conditional expression.
### High Availability / Scalability

### Notable Limits**

### Labs
