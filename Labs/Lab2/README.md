# Lab2 – Scopes
Purpose: The purpose of this lab is to understand how to deploy to deifferent scopes in Azure.
steps:
1. Create a new file called "subnet.bicep" in the "bicep" folder.
2. Make sure the target scope is "Subscription".
3. Write a configuration that deploys a resource group.
4. Write a module block to call the main.bicep file from Lab1.

Tip: You can use the documentation on scopes to help you with this lab. [reference](https://learn.microsoft.com/en-us/azure/azure-resource-manager/bicep/deploy-to-subscription?tabs=azure-cli)

Example code:

```bicep
targetScope = 'subscription'

resource rg 'Microsoft.Resources/resourceGroups@2023-07-01' = {
  name: 'RG-Bicep10'
  location: 'northeurope'
}

module exampleModule 'Demo1.bicep' = {
  name: 'exampleModule'
  scope: resourceGroup(rg.name)
}
```
