# Azure template

## Parameters

Parameter name | Required | Description
-------------- | -------- | -----------
accountType    | Yes      | Specifies the Active Directory account type for Azure Storage.
azureStorageSid | Yes      | Specifies the security identifier (SID) for Azure Storage.
domainGuid     | Yes      | Specifies the domain GUID.
domainName     | Yes      | Specifies the primary domain that the AD DNS server is authoritative for.
domainSid      | Yes      | Specifies the security identifier (SID).
forestName     | Yes      | Specifies the Active Directory forest to get.
netBiosDomainName | Yes      | Specifies the NetBIOS domain name.
samAccountName | Yes      | Specifies the Active Directory SAMAccountName for Azure Storage.

### accountType

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the Active Directory account type for Azure Storage.

- Allowed values: `Computer`, `User`

### azureStorageSid

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the security identifier (SID) for Azure Storage.

### domainGuid

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the domain GUID.

### domainName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the primary domain that the AD DNS server is authoritative for.

### domainSid

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the security identifier (SID).

### forestName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the Active Directory forest to get.

### netBiosDomainName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the NetBIOS domain name.

### samAccountName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Specifies the Active Directory SAMAccountName for Azure Storage.

## Outputs

Name | Type | Description
---- | ---- | -----------
ActiveDirectoryProperties | object | Settings properties for Active Directory (AD).

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.1",
    "metadata": {
        "template": "reference/activedirectoryproperties.json"
    },
    "parameters": {
        "accountType": {
            "value": ""
        },
        "azureStorageSid": {
            "value": ""
        },
        "domainGuid": {
            "value": ""
        },
        "domainName": {
            "value": ""
        },
        "domainSid": {
            "value": ""
        },
        "forestName": {
            "value": ""
        },
        "netBiosDomainName": {
            "value": ""
        },
        "samAccountName": {
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
