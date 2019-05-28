### Azure Functions C# Bindings Sample

A simple CRUD (Create, Read, Update, Delete) API is created to manage TODO items, using the following options as backing store:

- In-memory implementation
- Blob storage
- Table storage
- Cosmos DB
- Entity Framework Core

It's implemented using Azure Functions V2 in C#, and can be run against the local storage emulator for table storage, and the CosmosDb emulator.

### Get set up

You'll need to set up a `local.settings.json` file containing connection strings for the Azure Storage and Azure CosmosDb emulators. 

```js
{
    "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "UseDevelopmentStorage=true",
    "AzureWebJobsDashboard": "UseDevelopmentStorage=true",
    "FUNCTIONS_WORKER_RUNTIME": "dotnet",
    "SqlConnectionString": "Data Source=(LocalDB)\\MSSQLLocalDB;Integrated Security=true;Database=Todos",
    "CosmosDBConnection": "AccountEndpoint=https://localhost:8081/;AccountKey=C2y6yDjf5/R+ob0N8A7Cgv30VRDJIWEHLM+4QDU5DE2nQ9nDuVTqobD4b8mGGyPMbIZnqyMsEcaGQy67XIw/Jw=="
  }
}
```

To test the EF option, run the `TodoTable.sql` script to create the necessary table

### Testing Locally

You can run the `Test.ps1` PowerShell script to run a simple set of tests against the binding type of your choice, to create, read, update and delete todo items.

