# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
accessTier     | Yes      | The identity type.
allowBlobPublicAccess | No       | Allow or disallow public access to all blobs or containers in the storage account. The default interpretation is true for this property.
allowCrossTenantReplication | No       | Allow or disallow cross AAD tenant object replication. The default interpretation is true for this property.
allowedCopyScope | Yes      | Restrict copy to and from Storage Accounts within an AAD tenant or with Private Links to the same VNet.
allowSharedKeyAccess | No       | Indicates whether the storage account permits requests to be authorized with the account access key via Shared Key. If false, then all requests, including shared access signatures, must be authorized with Azure Active Directory (Azure AD). The default value is null, which is equivalent to true.
userAssignedIdentities | No       | Gets or sets a list of key value pairs that describe the set of User Assigned identities that will be used with this storage account. The key is the ARM resource identifier of the identity. Only 1 User Assigned identity is permitted here.
azureFilesIdentityBasedAuthentication | No       | Settings for Azure Files identity based authentication.
customDomain   | No       | The custom domain assigned to this storage account. This can be set via Update.
defaultToOAuthAuthentication | No       | A boolean flag which indicates whether the default authentication is OAuth or not. The default interpretation is false for this property.
encryption     | No       | The encryption settings on the storage account.
immutableStorageWithVersioning | No       | This property enables and defines account-level immutability. Enabling the feature auto-enables Blob Versioning.
isHnsEnabled   | No       | Account HierarchicalNamespace enabled if sets to true.
isLocalUserEnabled | No       | Enables local users feature, if set to true
isNfsV3Enabled | No       | NFS 3.0 protocol support enabled if set to true.
isSftpEnabled  | No       | Enables Secure File Transfer Protocol, if set to true
keyPolicy      | No       | KeyPolicy assigned to the storage account.
largeFileSharesState | No       | Allow large file shares if sets to Enabled. It cannot be disabled once it is enabled.
minimumTlsVersion | No       | Set the minimum TLS version to be permitted on requests to storage. The default interpretation is TLS 1.0 for this property.
networkAcls    | No       | Network rule set
publicNetworkAccess | No       | Allow or disallow public network access to Storage Account. Value is optional but if passed in, must be 'Enabled' or 'Disabled'.
routingPreference | No       | Routing preference defines the type of network, either microsoft or internet routing to be used to deliver the user data, the default option is microsoft routing
sasPolicy      | No       | SasPolicy assigned to the storage account.
supportsHttpsTrafficOnly | No       | Allows https traffic only to storage service if sets to true. The default value is true since API version 2019-04-01.

### accessTier

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The identity type.

- Allowed values: `Cool`, `Hot`

### allowBlobPublicAccess

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Allow or disallow public access to all blobs or containers in the storage account. The default interpretation is true for this property.

- Default value: `True`

### allowCrossTenantReplication

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Allow or disallow cross AAD tenant object replication. The default interpretation is true for this property.

- Default value: `True`

### allowedCopyScope

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Restrict copy to and from Storage Accounts within an AAD tenant or with Private Links to the same VNet.

- Allowed values: `AAD`, `PrivateLink`

### allowSharedKeyAccess

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Indicates whether the storage account permits requests to be authorized with the account access key via Shared Key. If false, then all requests, including shared access signatures, must be authorized with Azure Active Directory (Azure AD). The default value is null, which is equivalent to true.

### userAssignedIdentities

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Gets or sets a list of key value pairs that describe the set of User Assigned identities that will be used with this storage account. The key is the ARM resource identifier of the identity. Only 1 User Assigned identity is permitted here.

### azureFilesIdentityBasedAuthentication

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Settings for Azure Files identity based authentication.

### customDomain

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The custom domain assigned to this storage account. This can be set via Update.

### defaultToOAuthAuthentication

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

A boolean flag which indicates whether the default authentication is OAuth or not. The default interpretation is false for this property.

- Default value: `False`

### encryption

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The encryption settings on the storage account.

### immutableStorageWithVersioning

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

This property enables and defines account-level immutability. Enabling the feature auto-enables Blob Versioning.

### isHnsEnabled

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Account HierarchicalNamespace enabled if sets to true.

- Default value: `False`

### isLocalUserEnabled

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Enables local users feature, if set to true

- Default value: `False`

### isNfsV3Enabled

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

NFS 3.0 protocol support enabled if set to true.

- Default value: `False`

### isSftpEnabled

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Enables Secure File Transfer Protocol, if set to true

- Default value: `False`

### keyPolicy

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

KeyPolicy assigned to the storage account.

### largeFileSharesState

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Allow large file shares if sets to Enabled. It cannot be disabled once it is enabled.

- Default value: `Disabled`

- Allowed values: `Disabled`, `Enabled`

### minimumTlsVersion

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Set the minimum TLS version to be permitted on requests to storage. The default interpretation is TLS 1.0 for this property.

- Default value: `TLS1_0`

- Allowed values: `TLS1_0`, `TLS1_1`, `TLS1_2`

### networkAcls

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Network rule set

### publicNetworkAccess

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Allow or disallow public network access to Storage Account. Value is optional but if passed in, must be 'Enabled' or 'Disabled'.

- Default value: `Enabled`

- Allowed values: `Disabled`, `Enabled`

### routingPreference

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Routing preference defines the type of network, either microsoft or internet routing to be used to deliver the user data, the default option is microsoft routing

### sasPolicy

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

SasPolicy assigned to the storage account.

### supportsHttpsTrafficOnly

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Allows https traffic only to storage service if sets to true. The default value is true since API version 2019-04-01.

- Default value: `True`

## Outputs

Name | Type | Description
---- | ---- | -----------
StorageAccountPropertiesCreateParameters | object | The parameters used to create the storage account.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": "reference/storageaccountpropertiescreateparameters.json"
    },
    "parameters": {
        "accessTier": {
            "value": ""
        },
        "allowBlobPublicAccess": {
            "value": true
        },
        "allowCrossTenantReplication": {
            "value": true
        },
        "allowedCopyScope": {
            "value": ""
        },
        "allowSharedKeyAccess": {
            "value": null
        },
        "userAssignedIdentities": {
            "value": {}
        },
        "azureFilesIdentityBasedAuthentication": {
            "value": {}
        },
        "customDomain": {
            "value": {}
        },
        "defaultToOAuthAuthentication": {
            "value": false
        },
        "encryption": {
            "value": {}
        },
        "immutableStorageWithVersioning": {
            "value": {}
        },
        "isHnsEnabled": {
            "value": false
        },
        "isLocalUserEnabled": {
            "value": false
        },
        "isNfsV3Enabled": {
            "value": false
        },
        "isSftpEnabled": {
            "value": false
        },
        "keyPolicy": {
            "value": {}
        },
        "largeFileSharesState": {
            "value": "Disabled"
        },
        "minimumTlsVersion": {
            "value": "TLS1_0"
        },
        "networkAcls": {
            "value": {}
        },
        "publicNetworkAccess": {
            "value": "Enabled"
        },
        "routingPreference": {
            "value": {}
        },
        "sasPolicy": {
            "value": {}
        },
        "supportsHttpsTrafficOnly": {
            "value": true
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
