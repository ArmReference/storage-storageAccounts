# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | The SKU name. Required for account creation; optional for update. Note that in older versions, SKU name was called accountType.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The SKU name. Required for account creation; optional for update. Note that in older versions, SKU name was called accountType.

- Allowed values: `Premium_LRS`, `Premium_ZRS`, `Standard_GRS`, `Standard_GZRS`, `Standard_LRS`, `Standard_RAGRS`, `Standard_RAGZRS`, `Standard_ZRS`

## Outputs

Name | Type | Description
---- | ---- | -----------
sku  | object | The SKU of the storage account.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/sku.json"
    },
    "parameters": {
        "name": {
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
