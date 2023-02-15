# Microsoft Dynamics CRM - Web Services

Microsoft Dynamics CRM provides two important web services that are used to access CRM from an external application and invoke web methods to perform common business data operations such as create, delete, update, and find in CRM.

Consider the following scenarios −

*   You have an external .NET application, which needs to talk to CRM. For example, you may want to insert a Contact record in CRM when a new customer is registered in your external application.
    
*   Or maybe, you want to search records in CRM and display the search results in your external application.
    

In such scenarios, you can use the web services exposed by CRM to consume them in your application and perform create, delete, update, and find operations in CRM.

IDiscoveryService Web Service
-----------------------------

This web service returns a list of organizations that the specified user belongs to and the URL endpoint for each of the organization.

IOrganizationService Web Service
--------------------------------

This web service is the primary web service used for accessing data and metadata in CRM. The IOrganizationService uses two important assemblies –**Microsoft.Xrm.Sdk.dll** and **Microsoft.Crm.Sdk.Proxy.dll**. These assemblies can be found in the CRM SDK package inside the **Bin** folder.

**Microsoft.Xrm.Sdk.dll**

This assembly defines the core xRM methods and types, including proxy classes to make the connection to Microsoft Dynamics CRM simpler, authentication methods, and the service contracts.

**Microsoft.Crm.Sdk.Proxy.dll**

This assembly defines the requests and responses for non-core messages as well as enumerations required for working with the organization data. Following are the namespaces supported by these two assemblies.

Each of these assemblies support certain messages, which will be used to work with the data stored in any entity. A complete list of messages supported by them can be found in the following links −

**Supported xRM Messages** − [https://learn.microsoft.com/en-us/dotnet/api/microsoft.xrm.sdk.messages?view=dataverse-sdk-latest](https://learn.microsoft.com/en-us/dotnet/api/microsoft.xrm.sdk.messages?view=dataverse-sdk-latest)

**Supported CRM Messages** − [https://learn.microsoft.com/en-us/dotnet/api/microsoft.crm.sdk.messages?view=dataverse-sdk-latest](https://learn.microsoft.com/en-us/dotnet/api/microsoft.crm.sdk.messages?view=dataverse-sdk-latest)

IOrganizationService Web Service Methods
----------------------------------------

The **IOrganizationService** provides eight methods that allows you to perform all the common operations on the system and custom entities as well as organization metadata.

| Sr.No | Method | Description |
|--------|--------|--------------|
|1|**IOrganizationService.Create** | Creates a record.
|2|**IOrganizationService.Update** | Updates an existing record. |
|3|**IOrganizationService. Retrieve** | Retrieves a record. |
|4 | **IOrganizationService. RetrieveMultiple**|Retrieves a collection of records.|
|5|**IOrganizationService. Delete**|Deletes a record.|
|6|**IOrganizationService. Associate**|Creates a link between records.|
|7|**IOrganizationService.Disassociate**| Deletes a link between records.|
|8 |**IOrganizationService.Execute**|Used for common record processing as well as specialized processing such as case resolution, duplicate detection, etc.|

Web Service Example
-------------------

To understand how the web services work in CRM, we will look at an example provided by CRM SDK. In this example, we will create a new Account record, update it, and then finally delete it using the CRM **IOrganizationService** web service.

You can go step-by-step throughh the code on booking an appointment for a user in your organization with the sample [here]
(https://github.com/microsoft/PowerApps-Samples/tree/master/dataverse/orgsvc/C%23/BookAppointment)

Various Samples for you to test and learn are here: [https://github.com/microsoft/PowerApps-Samples/tree/master/dataverse/orgsvc/C%23](https://github.com/microsoft/PowerApps-Samples/tree/master/dataverse/orgsvc/C%23)

Use your Github skills to star and fork the repro
### Conclusion

In this chapter, we dealt with two important web services provided by CRM and a working example of how these web services can be used from an external application to perform various CRUD operations.

