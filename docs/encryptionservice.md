# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
enabled        | No       | A boolean indicating whether or not the service encrypts the data as it is stored. Encryption at rest is enabled by default today and cannot be disabled.
keyType        | Yes      | Encryption key type to be used for the encryption service. 'Account' key type implies that an account-scoped encryption key will be used. 'Service' key type implies that a default service key is used.

### enabled

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A boolean indicating whether or not the service encrypts the data as it is stored. Encryption at rest is enabled by default today and cannot be disabled.

- Default value: `True`

### keyType

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Encryption key type to be used for the encryption service. 'Account' key type implies that an account-scoped encryption key will be used. 'Service' key type implies that a default service key is used.

- Allowed values: `Account`, `Service`

## Outputs

Name | Type | Description
---- | ---- | -----------
EncryptionService | object | A service that allows server-side encryption to be used.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/encryptionservice.json"
    },
    "parameters": {
        "enabled": {
            "value": true
        },
        "keyType": {
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
