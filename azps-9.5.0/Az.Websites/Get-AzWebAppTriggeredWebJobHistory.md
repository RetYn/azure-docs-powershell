---
external help file: Az.Websites-help.xml
Module Name: Az.Websites
online version: https://learn.microsoft.com/powershell/module/az.websites/get-azwebapptriggeredwebjobhistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppTriggeredWebJobHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppTriggeredWebJobHistory.md
---

# Get-AzWebAppTriggeredWebJobHistory

## SYNOPSIS
Get or list triggered web job's history for an app.

## SYNTAX

### List (Default)
```
Get-AzWebAppTriggeredWebJobHistory -AppName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### Get
```
Get-AzWebAppTriggeredWebJobHistory -AppName <String> -Id <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-PassThru] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzWebAppTriggeredWebJobHistory -InputObject <IWebsitesIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [<CommonParameters>]
```

## DESCRIPTION
Get or list triggered web job's history for an app.

## EXAMPLES

### Example 1: List triggered web job's history for an app
```powershell
Get-AzWebAppTriggeredWebJobHistory -ResourceGroupName webjob-rg-test -AppName appService-test01 -Name triggeredjob-01
```
```output
Kind Name                                                 ResourceGroupName
---- ----                                                 -----------------
     appService-test01/triggeredjob-01/202201040249386155 webjob-rg-test
     appService-test01/triggeredjob-01/202201040236300466 webjob-rg-test
```

This command lists triggered web job's history for an app.

### Example 2: Get triggered web job's history for an app
```powershell
Get-AzWebAppTriggeredWebJobHistory -ResourceGroupName webjob-rg-test -AppName appService-test01 -Name triggeredjob-01 -Id 202201040236300466
```
```output
Kind Name                                                 ResourceGroupName
---- ----                                                 -----------------
     appService-test01/triggeredjob-01/202201040236300466 webjob-rg-test
```

This command get triggered web job's history for an app.

### Example 3: Get triggered web job's history for an app by pipeline
```powershell
$logs =  Get-AzWebAppTriggeredWebJobHistory -ResourceGroupName webjob-rg-test -AppName appService-test01 -Name triggeredjob-01
$logs[0].Id | Get-AzWebAppTriggeredWebJobHistory
```
```output
Kind Name                                                 ResourceGroupName
---- ----                                                 -----------------
     appService-test01/triggeredjob-01/202201040236300466 webjob-rg-test
```

This command get triggered web job's history for an app by pipeline.

## PARAMETERS

### -AppName
Site name.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Id
History ID.

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

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Name of Web Job.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns true when the command succeeds

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group to which the resource belongs.

```yaml
Type: System.String
Parameter Sets: List, Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Your Azure subscription ID.
This is a GUID-formatted string (e.g.
00000000-0000-0000-0000-000000000000).

```yaml
Type: System.String[]
Parameter Sets: List, Get
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.IWebsitesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Websites.Models.Api20210201.ITriggeredJobHistory

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


INPUTOBJECT `<IWebsitesIdentity>`: Identity Parameter
  - `[Authprovider <String>]`: The auth provider for the users.
  - `[DomainName <String>]`: The custom domain name.
  - `[EnvironmentName <String>]`: The stage site identifier.
  - `[FunctionAppName <String>]`: Name of the function app registered with the static site build.
  - `[Id <String>]`: Resource identity path
  - `[JobHistoryId <String>]`: History ID.
  - `[Location <String>]`: Location where you plan to create the static site.
  - `[Name <String>]`: Name of the static site.
  - `[PrivateEndpointConnectionName <String>]`: Name of the private endpoint connection.
  - `[ResourceGroupName <String>]`: Name of the resource group to which the resource belongs.
  - `[Slot <String>]`: Name of the deployment slot. If a slot is not specified, the API deletes a deployment for the production slot.
  - `[SubscriptionId <String>]`: Your Azure subscription ID. This is a GUID-formatted string (e.g. 00000000-0000-0000-0000-000000000000).
  - `[Userid <String>]`: The user id of the user.
  - `[WebJobName <String>]`: Name of Web Job.

## RELATED LINKS
