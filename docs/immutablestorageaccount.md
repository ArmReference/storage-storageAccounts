# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
enabled        | Yes      | A boolean flag which enables account-level immutability. All the containers under such an account have object-level immutability enabled by default.
immutabilityPolicy | Yes      | This defines account-level immutability policy properties.

### enabled

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

A boolean flag which enables account-level immutability. All the containers under such an account have object-level immutability enabled by default.

### immutabilityPolicy

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

This defines account-level immutability policy properties.

## Outputs

Name | Type | Description
---- | ---- | -----------
ImmutableStorageAccount | object | This property enables and defines account-level immutability. Enabling the feature auto-enables Blob Versioning.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/immutablestorageaccount.json"
    },
    "parameters": {
        "enabled": {
            "value": null
        },
        "immutabilityPolicy": {
            "value": {}
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
