# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
identity       | Yes      | Encryption identity for the storage account.
keySource      | Yes      | The encryption keySource (provider). Possible values (case-insensitive): Microsoft.Storage, Microsoft.Keyvault
keyvaultproperties | Yes      | Properties of key vault.
requireInfrastructureEncryption | Yes      | A boolean indicating whether or not the service applies a secondary layer of encryption with platform managed keys for data at rest.
services       | Yes      | A list of services that support encryption

### identity

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Encryption identity for the storage account.

### keySource

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The encryption keySource (provider). Possible values (case-insensitive): Microsoft.Storage, Microsoft.Keyvault

- Allowed values: `Microsoft.Keyvault`, `Microsoft.Storage`

### keyvaultproperties

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Properties of key vault.

### requireInfrastructureEncryption

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

A boolean indicating whether or not the service applies a secondary layer of encryption with platform managed keys for data at rest.

### services

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

A list of services that support encryption

## Outputs

Name | Type | Description
---- | ---- | -----------
Encryption | object | The encryption settings on the storage account.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/encryption.json"
    },
    "parameters": {
        "identity": {
            "value": {}
        },
        "keySource": {
            "value": ""
        },
        "keyvaultproperties": {
            "value": {}
        },
        "requireInfrastructureEncryption": {
            "value": null
        },
        "services": {
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
