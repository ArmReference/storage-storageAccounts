# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
allowProtectedAppendWrites | Yes      | 	This property can only be changed for disabled and unlocked time-based retention policies. When enabled, new blocks can be written to an append blob while maintaining immutability protection and compliance. Only new blocks can be added and any existing blocks cannot be modified or deleted.
immutabilityPeriodSinceCreationInDays | Yes      | The immutability period for the blobs in the container since the policy creation, in days.
state          | No       | The ImmutabilityPolicy state defines the mode of the policy. Disabled state disables the policy, Unlocked state allows increase and decrease of immutability retention time and also allows toggling allowProtectedAppendWrites property, Locked state only allows the increase of the immutability retention time. A policy can only be created in a Disabled or Unlocked state and can be toggled between the two states. Only a policy in an Unlocked state can transition to a Locked state which cannot be reverted.

### allowProtectedAppendWrites

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

	This property can only be changed for disabled and unlocked time-based retention policies. When enabled, new blocks can be written to an append blob while maintaining immutability protection and compliance. Only new blocks can be added and any existing blocks cannot be modified or deleted.

### immutabilityPeriodSinceCreationInDays

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The immutability period for the blobs in the container since the policy creation, in days.

### state

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The ImmutabilityPolicy state defines the mode of the policy. Disabled state disables the policy, Unlocked state allows increase and decrease of immutability retention time and also allows toggling allowProtectedAppendWrites property, Locked state only allows the increase of the immutability retention time. A policy can only be created in a Disabled or Unlocked state and can be toggled between the two states. Only a policy in an Unlocked state can transition to a Locked state which cannot be reverted.

- Default value: `Disabled`

- Allowed values: `Disabled`, `Locked`, `Unlocked`

## Outputs

Name | Type | Description
---- | ---- | -----------
AccountImmutabilityPolicyProperties | object | This defines account-level immutability policy properties.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/accountimmutabilitypolicproperties.json"
    },
    "parameters": {
        "allowProtectedAppendWrites": {
            "value": null
        },
        "immutabilityPeriodSinceCreationInDays": {
            "value": 0
        },
        "state": {
            "value": "Disabled"
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
