---
external help file:
Module Name: Az.MachineLearningServices
online version: https://learn.microsoft.com/powershell/module/az.MLWorkspace/new-AzMLWorkspaceMLFlowModelJobOutputObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/New-AzMLWorkspaceMLFlowModelJobOutputObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/MachineLearningServices/help/New-AzMLWorkspaceMLFlowModelJobOutputObject.md
---

# New-AzMLWorkspaceMLFlowModelJobOutputObject

## SYNOPSIS
Create an in-memory object for MLFlowModelJobOutput.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.machinelearningservices/new-azmlworkspacemlflowmodeljoboutputobject) for up-to-date information.

## SYNTAX

```
New-AzMLWorkspaceMLFlowModelJobOutputObject -Type <JobOutputType> [-Description <String>]
 [-Mode <OutputDeliveryMode>] [-Uri <String>] [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for MLFlowModelJobOutput.

## EXAMPLES

### Example 1: Create an in-memory object for MLFlowModelJobOutput
```powershell
New-AzMLWorkspaceMLFlowModelJobOutputObject
```

Create an in-memory object for MLFlowModelJobOutput

## PARAMETERS

### -Description
Description for the output.

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

### -Mode
Output Asset Delivery Mode.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Support.OutputDeliveryMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
[Required] Specifies the type of job.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Support.JobOutputType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri
Output Asset URI.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.MachineLearningServices.Models.Api20220501.MlFlowModelJobOutput

## NOTES

ALIASES

## RELATED LINKS

