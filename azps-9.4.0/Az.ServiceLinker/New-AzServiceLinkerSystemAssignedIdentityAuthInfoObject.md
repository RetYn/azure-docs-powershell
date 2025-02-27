---
external help file: 
Module Name: Az.ServiceLinker
online version: https://learn.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkersystemassignedidentityauthinfoobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject.md
---

# New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject

## SYNOPSIS
Create an in-memory object for SystemAssignedIdentityAuthInfo.

## SYNTAX

```
New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for SystemAssignedIdentityAuthInfo.

## EXAMPLES

### Example 1: Create linker's auth info with system assigned identity
```powershell
New-AzServiceLinkerSystemAssignedIdentityAuthInfoObject  
```

```output
AuthType
--------
systemAssignedIdentity
```

Create linker's auth info with system assigned identity

## PARAMETERS

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.SystemAssignedIdentityAuthInfo

## NOTES

ALIASES

## RELATED LINKS

