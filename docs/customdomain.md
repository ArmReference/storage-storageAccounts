# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
name           | Yes      | Gets or sets the custom domain name assigned to the storage account. Name is the CNAME source.
useSubDomainName | No       | Indicates whether indirect CName validation is enabled. Default value is false. This should only be set on updates.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Gets or sets the custom domain name assigned to the storage account. Name is the CNAME source.

### useSubDomainName

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Indicates whether indirect CName validation is enabled. Default value is false. This should only be set on updates.

- Default value: `False`

## Outputs

Name | Type | Description
---- | ---- | -----------
CustomDomain | object | The custom domain assigned to this storage account. This can be set via Update

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/customdomain.json"
    },
    "parameters": {
        "name": {
            "value": ""
        },
        "useSubDomainName": {
            "value": false
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
