# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
publishInternetEndpoints | Yes      | A boolean flag which indicates whether internet routing storage endpoints are to be published
publishMicrosoftEndpoints | Yes      | A boolean flag which indicates whether microsoft routing storage endpoints are to be published
routingChoice  | Yes      | Routing Choice defines the kind of network routing opted by the user.

### publishInternetEndpoints

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

A boolean flag which indicates whether internet routing storage endpoints are to be published

### publishMicrosoftEndpoints

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

A boolean flag which indicates whether microsoft routing storage endpoints are to be published

### routingChoice

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Routing Choice defines the kind of network routing opted by the user.

- Allowed values: `InternetRouting`, `MicrosoftRouting`

## Outputs

Name | Type | Description
---- | ---- | -----------
RoutingPreference | object | Routing preference defines the type of network, either microsoft or internet routing to be used to deliver the user data, the default option is microsoft routing

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/routingpreference.json"
    },
    "parameters": {
        "publishInternetEndpoints": {
            "value": null
        },
        "publishMicrosoftEndpoints": {
            "value": null
        },
        "routingChoice": {
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
