# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
type           | No       | The identity type.
userAssignedIdentities | No       | Gets or sets a list of key value pairs that describe the set of User Assigned identities that will be used with this storage account. The key is the ARM resource identifier of the identity. Only 1 User Assigned identity is permitted here.

### type

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The identity type.

- Default value: `None`

- Allowed values: `None`, `SystemAssigned`, `SystemAssigned,UserAssigned`, `UserAssigned`

### userAssignedIdentities

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Gets or sets a list of key value pairs that describe the set of User Assigned identities that will be used with this storage account. The key is the ARM resource identifier of the identity. Only 1 User Assigned identity is permitted here.

## Outputs

Name | Type | Description
---- | ---- | -----------
Identity | object | Identity for the resource.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/identity.json"
    },
    "parameters": {
        "type": {
            "value": "None"
        },
        "userAssignedIdentities": {
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
