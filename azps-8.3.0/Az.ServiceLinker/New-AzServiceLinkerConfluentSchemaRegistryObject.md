---
external help file:
Module Name: Az.ServiceLinker
online version: https://learn.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkerconfluentschemaregistryobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerConfluentSchemaRegistryObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerConfluentSchemaRegistryObject.md
---

# New-AzServiceLinkerConfluentSchemaRegistryObject

## SYNOPSIS
Create an in-memory object for ConfluentSchemaRegistry.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.servicelinker/new-azservicelinkerconfluentschemaregistryobject) for up-to-date information.

## SYNTAX

```
New-AzServiceLinkerConfluentSchemaRegistryObject -Endpoint <String> [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for ConfluentSchemaRegistry.

## EXAMPLES

### Example 1: Create an target resource object for schema registry on confluent cloud
```powershell
New-AzServiceLinkerConfluentSchemaRegistryObject -Endpoint "https://psrc-xxxx.westus2.azure.confluent.cloud"
```

```output
Endpoint
--------
https://psrc-xxxx.westus2.azure.confluent.cloud
```

Create an target resource object for schema registry on confluent cloud

## PARAMETERS

### -Endpoint
The endpoint of service.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ConfluentSchemaRegistry

## NOTES

ALIASES

## RELATED LINKS

