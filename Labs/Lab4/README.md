# Lab 4 - Bicep - Advanced Topics
Purpose: The purpose of this lab is to practice advanced Bicep topics usch as modules, loops, and conditions.
steps:
1. Create a new file called "advanced.bicep" in the "bicep" folder.
2. Write a configuration that deploys:
    - A resource group (subscription scope) [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.resources/resourcegroups?pivots=deployment-language-bicep)
    - A virtual network with a single subnet. [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.network/virtualnetworks?pivots=deployment-language-bicep)
    - A dynamic number of nics using a loop (one for each VM) [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.network/networkinterfaces?pivots=deployment-language-bicep)
    - A dynamic number of virtual machines using a loop [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.compute/virtualmachines?pivots=deployment-language-bicep)
    - Use a parameter to control the number and properties of the VMs
    - the parameter should be an array of objects, each object should contain the properties of the VM:
        - name
        - size
        - os
        - a boolean to indicate if the VM should have a system assigned identity
    here is an example of the parameter:
    ```bicep
    param vms array = [
        {
            name: 'vm1'
            size: 'Standard_B1s'
            os: 'Windows'
            hasIdentity: true
        }
        {
            name: 'vm2'
            size: 'Standard_B2ms'
            os: 'Linux'
            hasIdentity: false
        }
    ]
    ```
    - The managed identity deployment should be conditional based on the value of the boolean in the VM object
    