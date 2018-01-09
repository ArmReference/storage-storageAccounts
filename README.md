# storage-storageAccounts
Reference template
```
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "1.0.0.0",
  "parameters": {
    "StorageAccountName": {
      "type": "string",
      "defaultValue": ""
    },
    "ContainerName": {
      "type": "string",
      "defaultValue": ""
    },
    "SasToken": {
      "type": "string",
      "defaultValue": ""
    }
  },
  "variables": {
    "Provider": "/Microsoft.Storage",
    "Resource": "/storageAccounts",
    "templateUri": "[concat('https://',parameters('StorageAccountName'),'.blob.core.windows.net/',parameters('ContainerName'),variables('Provider'),variables('Resource'))]"
  },
  "resources": [
    {
      "name": "CreateStorageAccount",
      "type": "Microsoft.Resources/deployments",
      "apiVersion": "2016-09-01",
      "dependsOn": [ ],
      "properties": {
        "mode": "Incremental",
        "templateLink": {
          "uri": "[concat(variables('templateUri'), '/storageAccounts.json', parameters('SasToken'))]",
          "contentVersion": "2017.09.01.0"
        },
        "parameters": {
          "name": {
            "value": "[concat(uniquestring(resourceGroup().id), 'standardsa')]"
          },
          "sku": {
            "value": "Standard_LRS"
          },
          "kind": {
            "value": "Storage"
          }
        }
      }
    }
  ],
  "outputs": {
    "Empty": {
      "type": "object",
      "value": "[reference('CreateStorageAccount').outputs.storageAccounts.value]"
    }
  }
}
```
