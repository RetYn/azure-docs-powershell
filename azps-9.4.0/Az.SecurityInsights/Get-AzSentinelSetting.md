---
external help file: 
Module Name: Az.SecurityInsights
online version: https://learn.microsoft.com/powershell/module/az.securityinsights/get-azsentinelsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/help/Get-AzSentinelSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/help/Get-AzSentinelSetting.md
---

# Get-AzSentinelSetting

## SYNOPSIS
Gets a setting.

## SYNTAX

### List (Default)
```
Get-AzSentinelSetting -ResourceGroupName <String> -WorkspaceName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Get
```
Get-AzSentinelSetting -ResourceGroupName <String> -SettingsName <String> -WorkspaceName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzSentinelSetting -InputObject <ISecurityInsightsIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Gets a setting.

## EXAMPLES

### Example 1: List all Settings
```powershell
 Get-AzSentinelSetting -ResourceGroupName "myResourceGroupName" -workspaceName "myWorkspaceName"
```

```output
Kind      : EntityAnalytics
Name      : EntityAnalytics
IsEnabled : True

Kind      : EyesOn
Name      : EyesOn
IsEnabled : True

Kind : IPSyncer
Name : IPSyncer

Kind      : Anomalies
Name      : Anomalies
IsEnabled : True

Kind       : Ueba
Name       : Ueba
DataSource : {AuditLogs, AzureActivity, SecurityEvent, SigninLogs}
```

This command lists all Settings under a Microsoft Sentinel workspace.

### Example 2: Get a Setting
```powershell
 Get-AzSentinelSetting -ResourceGroupName "myResourceGroupName" -workspaceName "myWorkspaceName" -SettingsName "Anomalies"
```

```output
Kind      : Anomalies
Name      : Anomalies
IsEnabled : True
```

This command gets a Setting.

### Example 3: Get a Setting by object Id
```powershell
 $Settings = Get-AzSentinelSetting -ResourceGroupName "myResourceGroupName" -workspaceName "myWorkspaceName"
 $Settings[0] | Get-AzSentinelSetting
```

```output
Kind      : Anomalies
Name      : Anomalies
IsEnabled : True
```

This command gets a Setting by object

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.Models.ISecurityInsightsIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SettingsName
The setting name.
Supports - Anomalies, EyesOn, EntityAnalytics, Ueba

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String[]
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
The name of the workspace.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.Models.ISecurityInsightsIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.Models.Api20210901Preview.ISettings

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


`INPUTOBJECT <ISecurityInsightsIdentity>`: Identity Parameter
  - `[ActionId <String>]`: Action ID
  - `[AlertRuleTemplateId <String>]`: Alert rule template ID
  - `[AutomationRuleId <String>]`: Automation rule ID
  - `[BookmarkId <String>]`: Bookmark ID
  - `[ConsentId <String>]`: consent ID
  - `[DataConnectorId <String>]`: Connector ID
  - `[EntityId <String>]`: entity ID
  - `[EntityQueryId <String>]`: entity query ID
  - `[EntityQueryTemplateId <String>]`: entity query template ID
  - `[Id <String>]`: Resource identity path
  - `[IncidentCommentId <String>]`: Incident comment ID
  - `[IncidentId <String>]`: Incident ID
  - `[MetadataName <String>]`: The Metadata name.
  - `[Name <String>]`: Threat intelligence indicator name field.
  - `[RelationName <String>]`: Relation Name
  - `[ResourceGroupName <String>]`: The name of the resource group. The name is case insensitive.
  - `[RuleId <String>]`: Alert rule ID
  - `[SentinelOnboardingStateName <String>]`: The Sentinel onboarding state name. Supports - default
  - `[SettingsName <String>]`: The setting name. Supports - Anomalies, EyesOn, EntityAnalytics, Ueba
  - `[SourceControlId <String>]`: Source control Id
  - `[SubscriptionId <String>]`: The ID of the target subscription.
  - `[WorkspaceName <String>]`: The name of the workspace.

## RELATED LINKS

