---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Peering.dll-Help.xml
Module Name: Az.Peering
online version: https://learn.microsoft.com/powershell/module/az.peering/get-azpeeringcdnpeeringprefix
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringCdnPeeringPrefix.md
---

# Get-AzPeeringCdnPeeringPrefix

## SYNOPSIS
Lists all of the advertised prefixes for cdn in the specified peering location

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.peering/get-azpeeringcdnpeeringprefix) for up-to-date information.

## SYNTAX

```
Get-AzPeeringCdnPeeringPrefix [-PeeringLocation] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Lists all of the advertised prefixes for cdn in the specified peering location

## EXAMPLES

### Example 1
```powershell
Get-AzPeeringCdnPeeringPrefix -PeeringLocation "Seattle"
```

Lists all of the advertised prefixes for cdn in the specified physical peering location

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

### -PeeringLocation
The Physical Location Different from Azure Region.
Use Get-AzPeeringLocation -Kind \<kind\> use City name as key to check if the peering location exists or Use Get-AzPeeringLocation -Kind \<kind\> to get all the peering locations to select.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Peering.Models.PSCdnPeeringPrefix

## NOTES

## RELATED LINKS
