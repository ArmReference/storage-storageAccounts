# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
expirationAction | No       | The SAS expiration action. Can only be Log.
sasExpirationPeriod | Yes      | The SAS expiration period, DD.HH:MM:SS.

### expirationAction

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The SAS expiration action. Can only be Log.

- Default value: `Log`

- Allowed values: `Log`

### sasExpirationPeriod

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The SAS expiration period, DD.HH:MM:SS.

## Outputs

Name | Type | Description
---- | ---- | -----------
SasPolicy | object | SasPolicy

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/saspolicy.json"
    },
    "parameters": {
        "expirationAction": {
            "value": "Log"
        },
        "sasExpirationPeriod": {
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
