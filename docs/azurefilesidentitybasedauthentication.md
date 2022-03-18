# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
activeDirectoryProperties | No       | Settings properties for Active Directory (AD).
defaultSharePermission | No       | Default share permission for users using Kerberos authentication if RBAC role is not assigned.
directoryServiceOptions | No       | Indicates the directory service used.

### activeDirectoryProperties

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Settings properties for Active Directory (AD).

### defaultSharePermission

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Default share permission for users using Kerberos authentication if RBAC role is not assigned.

- Default value: `None`

- Allowed values: `None`, `StorageFileDataSmbShareContributor`, `StorageFileDataSmbShareElevatedContributor`, `StorageFileDataSmbShareReader`

### directoryServiceOptions

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Indicates the directory service used.

- Default value: `None`

- Allowed values: `None`, `AADDS`, `AD`

## Outputs

Name | Type | Description
---- | ---- | -----------
AzureFilesIdentityBasedAuthentication | object | Settings for Azure Files identity based authentication.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/azurefilesidentitybasedauthentication.json"
    },
    "parameters": {
        "activeDirectoryProperties": {
            "value": {}
        },
        "defaultSharePermission": {
            "value": "None"
        },
        "directoryServiceOptions": {
            "value": "None"
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
