---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 9A6F140C-9F1C-4701-9603-FC6107FCAF92
online version: https://learn.microsoft.com/powershell/module/az.compute/set-azvmbootdiagnostic
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMBootDiagnostic.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMBootDiagnostic.md
---

# Set-AzVMBootDiagnostic

## SYNOPSIS
Modifies boot diagnostics properties of a virtual machine.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.compute/set-azvmbootdiagnostic) for up-to-date information.

## SYNTAX

### EnableBootDiagnostics
```
Set-AzVMBootDiagnostic [-VM] <PSVirtualMachine> [-Enable] [[-ResourceGroupName] <String>]
 [[-StorageAccountName] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DisableBootDiagnostics
```
Set-AzVMBootDiagnostic [-VM] <PSVirtualMachine> [-Disable] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-AzVMBootDiagnostic** cmdlet modifies boot diagnostics properties of a virtual machine.

## EXAMPLES

### Example 1: Enable boot diagnostics
```powershell
$VM = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "ContosoVM07"
Set-AzVMBootDiagnostic -VM $VM -Enable -ResourceGroupName "ResourceGroup11" -StorageAccountName "DiagnosticStorage"
Update-AzVM -VM $VM -ResourceGroupName "ResourceGroup11"
```

The first command gets the virtual machine named ContosoVM07 by using **Get-AzVM**.
The command stores it in the $VM variable.
The second command enables boot diagnostics for the virtual machine in $VM.
Diagnostics data is stored in the specified account.

## PARAMETERS

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with azure.

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

### -Disable
Indicates that this cmdlet disables the boot diagnostics for the virtual machine.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DisableBootDiagnostics
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Indicates that this cmdlet enables the boot diagnostics for the virtual machine.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: EnableBootDiagnostics
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Specifies the name of the resource group of storage account.

```yaml
Type: System.String
Parameter Sets: EnableBootDiagnostics
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Specifies the name of the storage account in which to save boot diagnostics data. If not provided, it will look for a StorageUri in the BootDiagnostic Profile in the PSVirtualMachine object provided in the '-VM' parameter. If StorageUri is null, it will default to used a managed storage account.

```yaml
Type: System.String
Parameter Sets: EnableBootDiagnostics
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine for which this cmdlet changes boot diagnostics.
To obtain a virtual machine object, use the Get-AzVM cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Get-AzVM](./Get-AzVM.md)

[Get-AzVMBootDiagnosticsData](./Get-AzVMBootDiagnosticsData.md)


