---
external help file:
Module Name: Azs.Compute.Admin
online version: https://docs.microsoft.com/powershell/module/azs.compute.admin/set-azscomputequota
schema: 2.0.0
---

# Set-AzsComputeQuota

## SYNOPSIS
Creates or Updates a Compute Quota with the provided quota parameters.

## SYNTAX

```
Set-AzsComputeQuota -NewQuota \<IQuota> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Creates or Updates a Compute Quota with the provided quota parameters.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```powershell
$myComputeQuota = Get-AzsComputeQuota -Name MyComputeQuota
```

PS C:\\> $myComputeQuota.CoresLimit = 99; 

PS C:\\> Set-AzsComputeQuota -NewQuota $myComputeQuota

AvailabilitySetCount               : 10
CoresLimit                         : 99
Id                                 : /subscriptions/74c72bdc-d917-431c-a377-8ca80f4238a0/providers/Microsoft.Compute.Admin/locations/northwest/quotas/MyComputeQuota
Location                           : northwest
Name                               : MyComputeQuota
PremiumManagedDiskAndSnapshotSize  : 2048
StandardManagedDiskAndSnapshotSize : 2048
Type                               : Microsoft.Compute.Admin/quotas
VMScaleSetCount                    : 0
VirtualMachineCount                : 100

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

### -NewQuota
Holds Compute quota information used to control resource allocation.
To construct, see NOTES section for NEWQUOTA properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SubscriptionId
Subscription credentials that uniquely identify Microsoft Azure subscription.
The subscription ID forms part of the URI for every service call.

```yaml
Type: System.String
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

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ComputeAdmin.Models.Api202101.IQuota

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


NEWQUOTA \<IQuota>: Holds Compute quota information used to control resource allocation.
  - `[Location <String>]`: Location of the resource.
  - `[AvailabilitySetCount \<Int32?>]`: Maximum number of availability sets allowed.
  - `[CoresLimit \<Int32?>]`: Maximum number of cores allowed.
  - `[DdagpuCount \<Int32?>]`: Maximum number of dda gpus allowed.
  - `[PartitionedGpuCount \<Int32?>]`: Maximum number of partitioned gpus allowed.
  - `[PremiumManagedDiskAndSnapshotSize \<Int32?>]`: Maximum number of managed disks and snapshots of type premium allowed.
  - `[StandardManagedDiskAndSnapshotSize \<Int32?>]`: Maximum number of managed disks and snapshots of type standard allowed.
  - `[VMScaleSetCount \<Int32?>]`: Maximum number of scale sets allowed.
  - `[VirtualMachineCount \<Int32?>]`: Maximum number of virtual machines allowed.

## RELATED LINKS

