---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Sql.dll-Help.xml
Module Name: Az.Sql
online version: https://learn.microsoft.com/powershell/module/Az.sql/Get-AzSqlInstanceTransparentDataEncryptionProtector
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlInstanceTransparentDataEncryptionProtector.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Sql/Sql/help/Get-AzSqlInstanceTransparentDataEncryptionProtector.md
---

# Get-AzSqlInstanceTransparentDataEncryptionProtector

## SYNOPSIS
Gets the Transparent Data Encryption (TDE) protector for a SQL managed instance.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.sql/get-azsqlinstancetransparentdataencryptionprotector) for up-to-date information.

## SYNTAX

### AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorDefaultParameterSet (Default)
```
Get-AzSqlInstanceTransparentDataEncryptionProtector [-ResourceGroupName] <String> [-InstanceName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorInputObjectParameterSet
```
Get-AzSqlInstanceTransparentDataEncryptionProtector [-Instance] <AzureSqlManagedInstanceModel>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorResourceIdParameterSet
```
Get-AzSqlInstanceTransparentDataEncryptionProtector [-InstanceResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Get-AzSqlInstanceTransparentDataEncryptionProtector cmdlet gets the TDE protector for the specified SQL managed instance.

## EXAMPLES

### Example 1
```powershell
Get-AzSqlInstanceTransparentDataEncryptionProtector -ResourceGroupName 'ContosoResourceGroup' -InstanceName 'ContosoManagedInstanceName'
```

```output
ResourceGroupName              : ContosoResourceGroup
ManagedInstanceName            : ContosoManagedInstanceName
Type                           : AzureKeyVault
ManagedInstanceKeyVaultKeyName : contoso_contosokey_01234567890123456789012345678901
KeyId                          : https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901
```

This command gets the TDE protector for the managed instance named ContosoManagedInstanceName in resource group named ContosoResourceGroup.

### Example 2: Using managed instance object
```powershell
$managedInstance = Get-AzSqlInstance -Name 'ContosoManagedInstanceName' -ResourceGroupName 'ContosoResourceGroup'
Get-AzSqlInstanceTransparentDataEncryptionProtector -Instance $managedInstance
```

```output
ResourceGroupName              : ContosoResourceGroup
ManagedInstanceName            : ContosoManagedInstanceName
Type                           : AzureKeyVault
ManagedInstanceKeyVaultKeyName : contoso_contosokey_01234567890123456789012345678901
KeyId                          : https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901
```

This command gets the TDE protector for the managed instance named ContosoManagedInstanceName in resource group named ContosoResourceGroup.

### Example 3: Using managed instance resource id
```powershell
$managedInstance = Get-AzSqlInstance -Name 'ContosoManagedInstanceName' -ResourceGroupName 'ContosoResourceGroup'
Get-AzSqlInstanceTransparentDataEncryptionProtector -InstanceResourceId $managedInstance.ResourceId
```

```output
ResourceGroupName              : ContosoResourceGroup
ManagedInstanceName            : ContosoManagedInstanceName
Type                           : AzureKeyVault
ManagedInstanceKeyVaultKeyName : contoso_contosokey_01234567890123456789012345678901
KeyId                          : https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901
```

This command gets the TDE protector for the managed instance named ContosoManagedInstanceName in resource group named ContosoResourceGroup.

### Example 4: Using piping
```powershell
$managedInstance = Get-AzSqlInstance -Name 'ContosoManagedInstanceName' -ResourceGroupName 'ContosoResourceGroup'
$managedInstance | Get-AzSqlInstanceTransparentDataEncryptionProtector
```

```output
ResourceGroupName              : ContosoResourceGroup
ManagedInstanceName            : ContosoManagedInstanceName
Type                           : AzureKeyVault
ManagedInstanceKeyVaultKeyName : contoso_contosokey_01234567890123456789012345678901
KeyId                          : https://contoso.vault.azure.net/keys/contosokey/01234567890123456789012345678901
```

This command gets the TDE protector for the managed instance named ContosoManagedInstanceName in resource group named ContosoResourceGroup.

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

### -Instance
The instance input object

```yaml
Type: Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel
Parameter Sets: AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorInputObjectParameterSet
Aliases: InputObject

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InstanceName
The instance name

```yaml
Type: System.String
Parameter Sets: AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorDefaultParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceResourceId
The instance resource id

```yaml
Type: System.String
Parameter Sets: AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorResourceIdParameterSet
Aliases: ResourceId

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
The Resource Group Name

```yaml
Type: System.String
Parameter Sets: AzureSqlRmManagedInstanceTransparentDataEncryptionProtectorDefaultParameterSet
Aliases:

Required: True
Position: 0
Default value: None
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

### Microsoft.Azure.Commands.Sql.ManagedInstance.Model.AzureSqlManagedInstanceModel
System.String

## OUTPUTS

### Microsoft.Azure.Commands.Sql.TransparentDataEncryption.Model.AzureRmSqlManagedInstanceTransparentDataEncryptionProtectorModel

## NOTES

## RELATED LINKS
