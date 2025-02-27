---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://learn.microsoft.com/powershell/module/az.synapse/get-azsynapseworkspacepackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseWorkspacePackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseWorkspacePackage.md
---

# Get-AzSynapseWorkspacePackage

## SYNOPSIS
Gets a workspace package.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.synapse/get-azsynapseworkspacepackage) for up-to-date information.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseWorkspacePackage -WorkspaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseWorkspacePackage -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-AzSynapseWorkspacePackage** cmdlet gets a workspace package.

## EXAMPLES

### Example 1
```powershell
Get-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace
```

This command gets information about all workspace packages in the workspace named ContosoWorkspace.

### Example 2
```powershell
Get-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace -Name ContosoWorkspacePackage
```

This command gets information about the workspace package named ContosoWorkspacePackage in the workspace named ContosoWorkspace.

### Example 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseWorkspacePackage -Name ContosoWorkspacePackage
```

This command gets information about the workspace package named ContosoWorkspacePackage in the workspace named ContosoWorkspace through pipeline.

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

### -Name
The workspace package name.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PackageName, Package

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Name of Synapse workspace.

```yaml
Type: System.String
Parameter Sets: GetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
workspace input object, usually passed through the pipeline.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: GetByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage

## NOTES

## RELATED LINKS
