# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
federatedIdentityClientId | Yes      | ClientId of the multi-tenant application to be used in conjunction with the user-assigned identity for cross-tenant customer-managed-keys server-side encryption on the storage account.
userAssignedIdentity | Yes      | Resource identifier of the UserAssigned identity to be associated with server-side encryption on the storage account.

### federatedIdentityClientId

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

ClientId of the multi-tenant application to be used in conjunction with the user-assigned identity for cross-tenant customer-managed-keys server-side encryption on the storage account.

### userAssignedIdentity

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Resource identifier of the UserAssigned identity to be associated with server-side encryption on the storage account.

## Outputs

Name | Type | Description
---- | ---- | -----------
EncryptionIdentity | object | Encryption identity for the storage account.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/encryptionidentity.json"
    },
    "parameters": {
        "federatedIdentityClientId": {
            "value": ""
        },
        "userAssignedIdentity": {
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
