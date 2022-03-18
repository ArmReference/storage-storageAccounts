# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
blob           | No       | A service that allows server-side encryption to be used.
file           | No       | A service that allows server-side encryption to be used.
queue          | No       | A service that allows server-side encryption to be used.
table          | No       | A service that allows server-side encryption to be used.

### blob

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A service that allows server-side encryption to be used.

### file

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A service that allows server-side encryption to be used.

### queue

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A service that allows server-side encryption to be used.

### table

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A service that allows server-side encryption to be used.

## Outputs

Name | Type | Description
---- | ---- | -----------
EncryptionServices | object | A list of services that support encryption.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/encryptionservices.json"
    },
    "parameters": {
        "blob": {
            "value": {}
        },
        "file": {
            "value": {}
        },
        "queue": {
            "value": {}
        },
        "table": {
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
