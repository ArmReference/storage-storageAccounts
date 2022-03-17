# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The resource name
sku            | Yes      | The SKU of the storage account.
kind           | Yes      |
DependsOn      | No       | Pass dependencies

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The resource name

### sku

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The SKU of the storage account.

- Allowed values: `Standard_LRS`, `Standard_GRS`, `Standard_RAGRS`, `Standard_ZRS`, `Premium_LRS`

### kind

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)



- Allowed values: `Storage`, `StorageV2`, `BlobStorage`

### DependsOn

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Pass dependencies

## Outputs

Name | Type | Description
---- | ---- | -----------
storageAccounts | object |

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/storageAccounts.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "sku": {
            "value": ""
        },
        "kind": {
            "value": ""
        },
        "DependsOn": {
            "value": []
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
