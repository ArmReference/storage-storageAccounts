# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The resource name
location       | No       | Resource location.
sku            | Yes      | The SKU of the storage account.
kind           | Yes      |
extendedLocation | No       | The complex type of the extended location.
identity       | No       | Identity for the resource.
properties     | No       | The parameters used to create the storage account.
tags           | No       | Resource tags.
DependsOn      | No       | Pass dependencies

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The resource name

### location

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Resource location.

- Default value: `[resourceGroup().location]`

### sku

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The SKU of the storage account.

### kind

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)



- Allowed values: `BlobStorage`, `BlockBlobStorage`, `FileStorage`, `Storage`, `StorageV2`

### extendedLocation

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The complex type of the extended location.

### identity

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Identity for the resource.

### properties

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The parameters used to create the storage account.

### tags

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Resource tags.

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
        "location": {
            "value": "[resourceGroup().location]"
        },
        "sku": {
            "value": {}
        },
        "kind": {
            "value": ""
        },
        "extendedLocation": {
            "value": {}
        },
        "identity": {
            "value": {}
        },
        "properties": {
            "value": {}
        },
        "tags": {
            "value": {}
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
