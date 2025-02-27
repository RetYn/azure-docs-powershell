---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: DBA7AD5F-CC13-417A-B753-F998942530BB
online version: https://learn.microsoft.com/powershell/module/az.apimanagement/get-azapimanagement
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagement.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Get-AzApiManagement.md
---

# Get-AzApiManagement

## SYNOPSIS

Gets a list or a particular API Management Service description.

> [!NOTE]
>This is the previous version of our documentation. Please consult [the most recent version](/powershell/module/az.apimanagement/get-azapimanagement) for up-to-date information.

## SYNTAX

### GetBySubscription (Default)

```powershell
Get-AzApiManagement [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceGroup

```powershell
Get-AzApiManagement -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResource

```powershell
Get-AzApiManagement -ResourceGroupName <String> -Name <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByResourceId

```
Get-AzApiManagement -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION

The **Get-AzApiManagement** cmdlet gets a list of all API Management services under subscription or specified resource group or a particular API Management.

## EXAMPLES

### Example 1: Get all API Management services

```powershell
Get-AzApiManagement
```

This command gets all API Management services within a subscription.

### Example 2: Get an API Management services by a specific name

```powershell
Get-AzApiManagement -ResourceGroupName "contosogroup" -Name "contoso"
```

```output
PublicIPAddresses                     : {52.143.79.150}
PrivateIPAddresses                    :
Id                                    : /subscriptions/4f5285a3-9fd7-40ad-91b1-d8fc3823983d/resourceGroups/contosogroup/providers/Microsoft.ApiManagement/service/contoso
Name                                  : contoso
Location                              : West US 2
Sku                                   : Premium
Capacity                              : 1
CreatedTimeUtc                        : 10/13/2021 5:49:32 PM
ProvisioningState                     : Succeeded
RuntimeUrl                            : https://contoso.azure-api.net
RuntimeRegionalUrl                    : https://contoso-westus2-01.regional.azure-api.net
PortalUrl                             : https://contoso.portal.azure-api.net
DeveloperPortalUrl                    : https://contoso.developer.azure-api.net
ManagementApiUrl                      : https://contoso.management.azure-api.net
ScmUrl                                : https://contoso.scm.azure-api.net
PublisherEmail                        : glfeokti@microsoft.com
OrganizationName                      : fsdfsdfs
NotificationSenderEmail               : apimgmt-noreply@mail.windowsazure.com
VirtualNetwork                        :
VpnType                               : None
PortalCustomHostnameConfiguration     :
ProxyCustomHostnameConfiguration      : {contoso.azure-api.net}
ManagementCustomHostnameConfiguration :
ScmCustomHostnameConfiguration        :
DeveloperPortalHostnameConfiguration  :
SystemCertificates                    :
Tags                                  : {}
AdditionalRegions                     : {}
SslSetting                            : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementSslSetting
Identity                              : Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementServiceIdentity
EnableClientCertificate               :
Zone                                  :
DisableGateway                        : False
MinimalControlPlaneApiVersion         :
PublicIpAddressId                     :
PlatformVersion                       : stv2
PublicNetworkAccess                   : Enabled
PrivateEndpointConnections            : {kjoshipeconnection, kjoshipeeus}
ResourceGroupName                     : contosogroup
```

This command gets all API Management service by name.


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

### -Name

Specifies the name of API Management service.

```yaml
Type: System.String
Parameter Sets: GetByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName

Specifies the name of the resource group under in which this cmdlet gets the API Management service.

```yaml
Type: System.String
Parameter Sets: GetByResourceGroup, GetByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId

Arm ResourceId of the API Management service.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagement

## NOTES

## RELATED LINKS

[Backup-AzApiManagement](./Backup-AzApiManagement.md)

[New-AzApiManagement](./New-AzApiManagement.md)

[Remove-AzApiManagement](./Remove-AzApiManagement.md)

[Restore-AzApiManagement](./Restore-AzApiManagement.md)
