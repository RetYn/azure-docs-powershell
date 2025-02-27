---
external help file:
Module Name: Az.Logz
online version: https://learn.microsoft.com/powershell/module/az.logz/get-azlogzmonitoruserrole
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitorUserRole.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitorUserRole.md
---

# Get-AzLogzMonitorUserRole

## SYNOPSIS
List the user's roles configured on Logz.io side for the account corresponding to the monitor resource.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.logz/get-azlogzmonitoruserrole) for up-to-date information.

## SYNTAX

```
Get-AzLogzMonitorUserRole -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-EmailAddress <String>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
List the user's roles configured on Logz.io side for the account corresponding to the monitor resource.

## EXAMPLES

### Example 1: List the user's roles configured on Logz.io side for the account corresponding to the monitor resource
```powershell
Get-AzLogzMonitorUserRole -ResourceGroupName logz-rg-test -Name pwsh-logz04
```

```output
Role
----
None
```

This command lists the user's roles configured on Logz.io side for the account corresponding to the monitor resource.

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

### -EmailAddress
Email of the user used by Logz for contacting them if needed

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Monitor resource name

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

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

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

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IUserRoleResponse

## NOTES

ALIASES

## RELATED LINKS

