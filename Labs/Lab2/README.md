# Lab 2 - Develop Your First Bicep Template
Purpose: The purpose of this lab is to develop your first Bicep template.
Steps:
1. Open Visual Studio Code Termianl and run ```az login``` to login to your Azure account.
2. Create a new file called "rg.bicep" in the "bicep" folder.
3. Write a configuration that deploys:
    - A virtual network with a single subnet. [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.network/virtualnetworks?pivots=deployment-language-bicep)
    - A public IP address [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.network/publicipaddresses?pivots=deployment-language-bicep)
    - A network security group [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.network/networksecuritygroups?pivots=deployment-language-bicep)
    - A virtual network interface card [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.network/networkinterfaces?pivots=deployment-language-bicep)
    - A virtual machine [reference](https://learn.microsoft.com/en-us/azure/templates/microsoft.compute/virtualmachines?pivots=deployment-language-bicep)

4. Deploy into the resource group you created in Lab 1 by running the following command in the terminal:
    ```bash
    az deployment group create --resource-group <resource-group-name> --template-file rg.bicep
    ```
5. Make sure you use parameters and variables in your Bicep file to make it reusable and easy to maintain.