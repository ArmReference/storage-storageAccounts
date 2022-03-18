# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The name of the extended location.
type           | No       | The type of extendedLocation.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the extended location.

### type

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The type of extendedLocation.

- Default value: `EdgeZone`

## Outputs

Name | Type | Description
---- | ---- | -----------
ExtendedLocation | object | The complex type of the extended location.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/extendedlocation.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "type": {
            "value": "EdgeZone"
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
