---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://learn.microsoft.com/powershell/module/az.accounts/get-azcontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Get-AzContext.md
---

# Get-AzContext

## SYNOPSIS
Gets the metadata used to authenticate Azure Resource Manager requests.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.accounts/get-azcontext) for up-to-date information.

## SYNTAX

### GetSingleContext (Default)
```
Get-AzContext [-DefaultProfile <IAzureContextContainer>] [[-Name] <String>] [<CommonParameters>]
```

### ListAllContexts
```
Get-AzContext [-ListAvailable] [-RefreshContextFromTokenCache] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-AzContext cmdlet gets the current metadata used to authenticate Azure Resource Manager requests.
This cmdlet gets the Active Directory account, Active Directory tenant, Azure subscription, and the targeted Azure environment.
Azure Resource Manager cmdlets use these settings by default when making Azure Resource Manager requests. When the available amount of subscription exceeds the default limit of 25, some subscriptions may not show up in the results of `Get-AzContext -ListAvailable`. Please run `Connect-AzAccount -MaxContextPopulation <int>` to get more contexts.

## EXAMPLES

### Example 1: Getting the current context
```powershell
Connect-AzAccount
Get-AzContext
```

```Output
Name                                     Account             SubscriptionName    Environment         TenantId
----                                     -------             ----------------    -----------         --------
Subscription1 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription1       AzureCloud          xxxxxxxx-x...
```

In this example we are logging into our account with an Azure subscription using Connect-AzAccount, and then we are getting the context of the current session by calling Get-AzContext.

### Example 2: Listing all available contexts
```powershell
Get-AzContext -ListAvailable
```

```Output
Name                                     Account             SubscriptionName    Environment         TenantId
----                                     -------             ----------------    -----------         --------
Subscription1 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription1       AzureCloud          xxxxxxxx-x...
Subscription2 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription2       AzureCloud          xxxxxxxx-x...
Subscription3 (xxxxxxxx-xxxx-xxxx-xxx... test@outlook.com    Subscription3       AzureCloud          xxxxxxxx-x...
```

In this example, all currently available contexts are displayed.  The user may select one of these contexts using Select-AzContext.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant and subscription used for communication with azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ListAvailable
List all available contexts in the current session.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAllContexts
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the context

```yaml
Type: System.String
Parameter Sets: GetSingleContext
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RefreshContextFromTokenCache
Refresh contexts from token cache

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ListAllContexts
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureContext

## NOTES

## RELATED LINKS

[Set-AzContext](./Set-AzContext.md)

[Connect-AzAccount](./Connect-AzAccount.md)
