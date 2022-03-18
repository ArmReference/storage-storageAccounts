# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
bypass         | No       | Specifies whether traffic is bypassed for Logging/Metrics/AzureServices. Possible values are any combination of Logging,Metrics,AzureServices (For example, 'Logging, Metrics'), or None to bypass none of those traffics.
defaultAction  | Yes      | Specifies the default action of allow or deny when no other rules match.
ipRules        | No       | Sets the IP ACL rules
resourceAccessRules | No       | Sets the resource access rules.
virtualNetworkRules | No       | TSets the virtual network rules

### bypass

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Specifies whether traffic is bypassed for Logging/Metrics/AzureServices. Possible values are any combination of Logging,Metrics,AzureServices (For example, 'Logging, Metrics'), or None to bypass none of those traffics.

- Default value: `None`

- Allowed values: `AzureServices`, `Logging`, `Metrics`, `None`

### defaultAction

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the default action of allow or deny when no other rules match.

- Allowed values: `Allow`, `Deny`

### ipRules

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Sets the IP ACL rules

### resourceAccessRules

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Sets the resource access rules.

### virtualNetworkRules

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

TSets the virtual network rules

## Outputs

Name | Type | Description
---- | ---- | -----------
NetworkRuleSet | object | Network rule set

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/networkruleset.json"
    },
    "parameters": {
        "bypass": {
            "value": "None"
        },
        "defaultAction": {
            "value": ""
        },
        "ipRules": {
            "value": []
        },
        "resourceAccessRules": {
            "value": []
        },
        "virtualNetworkRules": {
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
