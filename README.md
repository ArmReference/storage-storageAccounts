[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FArmReference%2Fstorage-storageAccounts%2F1.0.0.0%2Fazuredeploy.json)
# Create StorageAccount

This template creates a StorageAccount in Azure

AAzure Storage is a Microsoft-managed service providing cloud storage that is highly available, secure, durable, scalable, and redundant. Azure Storage includes Azure Blobs (objects), Azure Data Lake Storage Gen2, Azure Files, Azure Queues, and Azure Tables.

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
StorageAccountName | No       |
ContainerName  | No       |
SasToken       | No       |

### StorageAccountName

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)



### ContainerName

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)



### SasToken

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)



## Outputs

Name | Type | Description
---- | ---- | -----------
Empty | object |

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "azuredeploy.json"
    },
    "parameters": {
        "StorageAccountName": {
            "value": ""
        },
        "ContainerName": {
            "value": ""
        },
        "SasToken": {
            "value": ""
        }
    }
}
```

### Command line

#### PowerShell

```powershell
New-AzResourceGroupDeployment -Name <deployment-name> -ResourceGroupName <resource-group-name> -TemplateFile <path-to-template> -TemplateParameterFile <path-to-templateparameter>
```

#### Azure CLI

```text
az group deployment create --name <deployment-name> --resource-group <resource-group-name> --template-file <path-to-template> --parameters @<path-to-templateparameterfile>
```
