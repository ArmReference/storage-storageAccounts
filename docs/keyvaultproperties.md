# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
keyname        | Yes      | The name of KeyVault key.
keyvaulturi    | Yes      | The Uri of KeyVault.
keyversion     | Yes      | The version of KeyVault key.

### keyname

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of KeyVault key.

### keyvaulturi

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The Uri of KeyVault.

### keyversion

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The version of KeyVault key.

## Outputs

Name | Type | Description
---- | ---- | -----------
KeyVaultProperties | object | Properties of key vault.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/keyvaultproperties.json"
    },
    "parameters": {
        "keyname": {
            "value": ""
        },
        "keyvaulturi": {
            "value": ""
        },
        "keyversion": {
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
