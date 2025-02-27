---
description: Configure Azure PowerShell global settings using centralized and granular AzConfig cmdlets
ms.custom: devx-track-azurepowershell
ms.date: 03/03/2023
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Configure Azure PowerShell global settings
---

# Configure Azure PowerShell global settings

Azure PowerShell supports several global settings like disabling breaking change warning messages.
Before Az PowerShell module version 9, there wasn't a centralized or granular way to configure
global settings for Azure PowerShell.

## Centralized configuration

The Az PowerShell module version 9 and higher includes cmdlets for managing the configuration of
global settings for Azure PowerShell. These `*-AzConfig` cmdlets are part of the Az.Accounts
PowerShell module:

- [Get-AzConfig][get-azconfig]
- [Update-AzConfig][update-azconfig]
- [Export-AzConfig][export-azconfig]
- [Import-AzConfig][import-azconfig]
- [Clear-AzConfig][clear-azconfig]

## Granular settings

You can apply settings that are only effective in a particular scope. The valid values for the
**Scope** parameter are:

- `Current User`. The default when applying a setting.
- `Process`. Setting is only applied to the current PowerShell session.
- `Default`. Readonly scope where the default value hasn't been changed.
- `Environment`. Readonly scope where the value has been configured via an environment variable.

Besides scopes, you can apply the settings to all Az PowerShell modules or only a single module.
With the **AppliesTo** parameter, you can specify how broad you want the setting applied. The value
`Az` indicates the setting is applied to all modules available that are part of Azure PowerShell.

To disable the breaking change warning message for cmdlets in the **Az.Compute** module, use the
`Update-AzConfig` cmdlet with the **DisplayBreakingChangeWarning** and **AppliesTo** parameters as
shown in the following example.

```azurepowershell-interactive
Update-AzConfig -DisplayBreakingChangeWarning $false -AppliesTo Az.Compute
```

In this scenario, the breaking change warning message remains active for cmdlets in all Az
PowerShell modules except **Az.Compute**.

## Default subscription

By default, when you authenticate to Azure, all subscriptions that you can access are retrieved. The
first subscription that's returned by Azure is used unless you specify a subscription with
`Connect-AzAccount`. This behavior can be dangerous, for example if the first subscription returned
is a production environment.

To configure your default subscription, you use the `Update-AzConfig` cmdlet with the
**DefaultSubscriptionForLogin** parameter as shown in the following example.

```azurepowershell-interactive
Update-AzConfig -DefaultSubscriptionForLogin <Subscription ID or Name>
```

> [!NOTE]
> Not to be confused with **the subscription of the default context**, the
> **DefaultSubscriptionForLogin** configuration takes effect only when authenticating to Azure.

## Replicating settings

To replicate your settings from one environment to another, you use the `Export-AzConfig` cmdlet to
export the settings to a JSON file.

```azurepowershell-interactive
Export-AzConfig -Path $HOME\AzConfig.json
```

To import your settings, use the `Import-AzConfig` cmdlet and reference the previously exported
JSON file.

```azurepowershell-interactive
Import-AzConfig -Path $HOME\AzConfig.json
```

## Clearing configuration

To reset the configuration setting of one or more Azure PowerShell global settings to the default,
use the `Clear-AzConfig` cmdlet. In the following example, the **DefaultSubscriptionForLogin**
setting is cleared.

```azurepowershell-interactive
Clear-AzConfig -DefaultSubscriptionForLogin
```

<!-- link references -->
[get-azconfig]: /powershell/module/az.accounts/get-azconfig
[update-azconfig]:/powershell/module/az.accounts/update-azconfig
[export-azconfig]: /powershell/module/az.accounts/export-azconfig
[import-azconfig]: /powershell/module/az.accounts/import-azconfig
[clear-azconfig]: /powershell/module/az.accounts/clear-azconfig
