---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://learn.microsoft.com/powershell/module/az.network/new-azapplicationgatewayfirewallpolicyexclusion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayFirewallPolicyExclusion.md
---

# New-AzApplicationGatewayFirewallPolicyExclusion

## SYNOPSIS
Creates an exclusion on the Firewall Policy

## SYNTAX

```
New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable <String> -SelectorMatchOperator <String>
 -Selector <String> [-ExclusionManagedRuleSet <PSApplicationGatewayFirewallPolicyExclusionManagedRuleSet[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **New-AzApplicationGatewayFirewallPolicyExclusion** cmdlet a new exclusion rule list for firewall policy.

## EXAMPLES

### Example 1
```powershell
$exclusionEntry = New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable "RequestHeaderNames" -SelectorMatchOperator "StartsWith" -Selector "xyz"
```

This command creates a new exclusion-entry for the variable named RequestHeaderNames and operator named StartsWith and Selector named xyz. The exclusion entry is saved in $exclusionEntry.

### Example 2
```powershell
$exclusionEntry = New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable "RequestHeaderKeys" -SelectorMatchOperator "Contains" -Selector "abc"
```

This command creates a new exclusion-entry for the variable named RequestHeaderKeys and operator named Contains and Selector named abc. The exclusion entry is saved in $exclusionEntry.

### Example 3
```powershell
$exclusionEntry = New-AzApplicationGatewayFirewallPolicyExclusion -MatchVariable "RequestHeaderNames" -SelectorMatchOperator "StartsWith" -Selector "xyz" -ExclusionManagedRuleSet $exclusionManagedRuleSet
```

This command creates a new exclusion-entry for the variable named RequestHeaderNames and operator named StartsWith, Selector named xyz and ExclusionManagedRuleSet named $exclusionManagedRuleSet. The exclusion entry is saved in $exclusionEntry.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

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

### -MatchVariable
The variable to be excluded.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: RequestHeaderNames, RequestCookieNames, RequestArgNames, RequestHeaderKeys, RequestCookieKeys, RequestArgKeys, RequestHeaderValues, RequestCookieValues, RequestArgValues

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Selector
When variable is a collection, operator used to specify which elements in the collection this exclusion applies to.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SelectorMatchOperator
When variable is a collection, operate on the selector to specify which elements in the collection this exclusion applies to.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Equals, Contains, StartsWith, EndsWith, EqualsAny

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExclusionManagedRuleSet
List of Exclusion Managed ruleSets.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusionManagedRuleSet[]
Parameter Sets: (All)
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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayFirewallPolicyExclusion

## NOTES

## RELATED LINKS
