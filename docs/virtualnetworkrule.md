# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
action         | No       | The action of virtual network rule.
id             | Yes      | Full resource id of a vnet subnet

### action

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The action of virtual network rule.

- Default value: `Allow`

### id

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Full resource id of a vnet subnet

## Outputs

Name | Type | Description
---- | ---- | -----------
VirtualNetworkRule | object | VirtualNetworkRule

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/virtualnetworkrule.json"
    },
    "parameters": {
        "action": {
            "value": "Allow"
        },
        "id": {
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
