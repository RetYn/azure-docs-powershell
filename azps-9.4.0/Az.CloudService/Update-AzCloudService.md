---
external help file: 
Module Name: Az.CloudService
online version: https://learn.microsoft.com/powershell/module/az.cloudservice/update-azcloudservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Update-AzCloudService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CloudService/help/Update-AzCloudService.md
---

# Update-AzCloudService

## SYNOPSIS
Create or update a cloud service.
Please note some properties can be set only during cloud service creation.

## SYNTAX

```
Update-AzCloudService -InputObject <ICloudServiceIdentity> -Parameter <ICloudService>
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Create or update a cloud service.
Please note some properties can be set only during cloud service creation.

## EXAMPLES

### Example 1: Add RDP extension to existing cloud service
```powershell
# Create RDP extension object
$rdpExtension = New-AzCloudServiceRemoteDesktopExtensionObject -Name "RDPExtension" -Credential $credential -Expiration $expiration -TypeHandlerVersion "1.2.1"
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"
# Add RDP extension to existing cloud service extension object
$cloudService.ExtensionProfile.Extension = $cloudService.ExtensionProfile.Extension + $rdpExtension
# Update cloud service
$cloudService | Update-AzCloudService
```

Above set of commands adds a RDP extension to already existing cloud service named ContosoCS that belongs to the resource group named ContosOrg.

### Example 2: Remove all extensions from cloud service
```powershell
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"
# Set extension to empty list
$cloudService.ExtensionProfile.Extension = @()
# Update cloud service
$cloudService | Update-AzCloudService
```

Above set of commands removes all extensions from existing cloud service named ContosoCS that belongs to the resource group named ContosOrg.

### Example 3: Remove RDP extension from cloud service
```powershell
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"
# Remove extension by name RDPExtension
$cloudService.ExtensionProfile.Extension = $cloudService.ExtensionProfile.Extension | Where-Object { $_.Name -ne "RDPExtension" }
# Update cloud service
$cloudService | Update-AzCloudService
```

Above set of commands removes RDP extension from existing cloud service named ContosoCS that belongs to the resource group named ContosOrg.

### Example 4: Scale-Out / Scale-In role instances
```powershell
# Get existing cloud service
$cloudService = Get-AzCloudService -ResourceGroupName "ContosOrg" -CloudServiceName "ContosoCS"

# Scale-out all role instance count by 1
$cloudService.RoleProfile.Role | ForEach-Object {$_.SkuCapacity += 1}

# Scale-in ContosoFrontend role instance count by 1
$role = $cloudService.RoleProfile.Role | Where-Object {$_.Name -eq "ContosoFrontend"}
$role.SkuCapacity -= 1

# Update cloud service configuration as per the new role instance count
$cloudService.Configuration = $configuration

# Update cloud service
$cloudService | Update-AzCloudService
```

Above set of commands shows how to scale-out and scale-in role instance count for cloud service named ContosoCS that belongs to the resource group named ContosOrg.

## PARAMETERS

### -AsJob
Run the command as a job

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

### -InputObject
Identity Parameter
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

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

### -Parameter
Describes the cloud service.
To construct, see NOTES section for PARAMETER properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.ICloudServiceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CloudService.Models.Api20210301.ICloudService

## NOTES

ALIASES

COMPLEX PARAMETER PROPERTIES

To create the parameters described below, construct a hash table containing the appropriate properties. For information on hash tables, run Get-Help about_Hash_Tables.


INPUTOBJECT `<ICloudServiceIdentity>`: Identity Parameter
  - `[CloudServiceName <String>]`: 
  - `[IPConfigurationName <String>]`: The IP configuration name.
  - `[Id <String>]`: Resource identity path
  - `[Location <String>]`: Name of the location that the OS version pertains to.
  - `[NetworkInterfaceName <String>]`: The name of the network interface.
  - `[OSFamilyName <String>]`: Name of the OS family.
  - `[OSVersionName <String>]`: Name of the OS version.
  - `[PublicIPAddressName <String>]`: The name of the public IP Address.
  - `[ResourceGroupName <String>]`: 
  - `[RoleInstanceName <String>]`: Name of the role instance.
  - `[RoleName <String>]`: Name of the role.
  - `[SubscriptionId <String>]`: Subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
  - `[UpdateDomain <Int32?>]`: Specifies an integer value that identifies the update domain. Update domains are identified with a zero-based index: the first update domain has an ID of 0, the second has an ID of 1, and so on.

PARAMETER `<ICloudService>`: Describes the cloud service.
  - `Location <String>`: Resource location.
  - `[AllowModelOverride <Boolean?>]`: (Optional) Indicates whether the role sku properties (roleProfile.roles.sku) specified in the model/template should override the role instance count and vm size specified in the .cscfg and .csdef respectively.         The default value is `false`.
  - `[Configuration <String>]`: Specifies the XML service configuration (.cscfg) for the cloud service.
  - `[ConfigurationUrl <String>]`: Specifies a URL that refers to the location of the service configuration in the Blob service. The service package URL  can be Shared Access Signature (SAS) URI from any storage account.         This is a write-only property and is not returned in GET calls.
  - `[ExtensionProfile <ICloudServiceExtensionProfile>]`: Describes a cloud service extension profile.
    - `[Extension <IExtension[]>]`: List of extensions for the cloud service.
      - `[AutoUpgradeMinorVersion <Boolean?>]`: Explicitly specify whether platform can automatically upgrade typeHandlerVersion to higher minor versions when they become available.
      - `[ForceUpdateTag <String>]`: Tag to force apply the provided public and protected settings.         Changing the tag value allows for re-running the extension without changing any of the public or protected settings.         If forceUpdateTag is not changed, updates to public or protected settings would still be applied by the handler.         If neither forceUpdateTag nor any of public or protected settings change, extension would flow to the role instance with the same sequence-number, and         it is up to handler implementation whether to re-run it or not
      - `[Name <String>]`: The name of the extension.
      - `[ProtectedSetting <String>]`: Protected settings for the extension which are encrypted before sent to the role instance.
      - `[ProtectedSettingFromKeyVaultSecretUrl <String>]`: 
      - `[Publisher <String>]`: The name of the extension handler publisher.
      - `[RolesAppliedTo <String[]>]`: Optional list of roles to apply this extension. If property is not specified or '*' is specified, extension is applied to all roles in the cloud service.
      - `[Setting <String>]`: Public settings for the extension. For JSON extensions, this is the JSON settings for the extension. For XML Extension (like RDP), this is the XML setting for the extension.
      - `[SourceVaultId <String>]`: Resource Id
      - `[Type <String>]`: Specifies the type of the extension.
      - `[TypeHandlerVersion <String>]`: Specifies the version of the extension. Specifies the version of the extension. If this element is not specified or an asterisk (*) is used as the value, the latest version of the extension is used. If the value is specified with a major version number and an asterisk as the minor version number (X.), the latest minor version of the specified major version is selected. If a major version number and a minor version number are specified (X.Y), the specific extension version is selected. If a version is specified, an auto-upgrade is performed on the role instance.
  - `[NetworkProfile <ICloudServiceNetworkProfile>]`: Network Profile for the cloud service.
    - `[LoadBalancerConfiguration <ILoadBalancerConfiguration[]>]`: List of Load balancer configurations. Cloud service can have up to two load balancer configurations, corresponding to a Public Load Balancer and an Internal Load Balancer.
      - `FrontendIPConfiguration <ILoadBalancerFrontendIPConfiguration[]>`: Specifies the frontend IP to be used for the load balancer. Only IPv4 frontend IP address is supported. Each load balancer configuration must have exactly one frontend IP configuration.
        - `Name <String>`: The name of the resource that is unique within the set of frontend IP configurations used by the load balancer. This name can be used to access the resource.
        - `[PrivateIPAddress <String>]`: The virtual network private IP address of the IP configuration.
        - `[PublicIPAddressId <String>]`: Resource Id
        - `[SubnetId <String>]`: Resource Id
      - `Name <String>`: The name of the Load balancer
      - `[Id <String>]`: Resource Id
    - `[SwappableCloudService <ISubResource>]`: The id reference of the cloud service containing the target IP with which the subject cloud service can perform a swap. This property cannot be updated once it is set. The swappable cloud service referred by this id must be present otherwise an error will be thrown.
      - `[Id <String>]`: Resource Id
  - `[OSProfile <ICloudServiceOSProfile>]`: Describes the OS profile for the cloud service.
    - `[Secret <ICloudServiceVaultSecretGroup[]>]`: Specifies set of certificates that should be installed onto the role instances.
      - `[SourceVaultId <String>]`: Resource Id
      - `[VaultCertificate <ICloudServiceVaultCertificate[]>]`: The list of key vault references in SourceVault which contain certificates.
        - `[CertificateUrl <String>]`: This is the URL of a certificate that has been uploaded to Key Vault as a secret.
  - `[PackageUrl <String>]`: Specifies a URL that refers to the location of the service package in the Blob service. The service package URL can be Shared Access Signature (SAS) URI from any storage account.         This is a write-only property and is not returned in GET calls.
  - `[RoleProfile <ICloudServiceRoleProfile>]`: Describes the role profile for the cloud service.
    - `[Role <ICloudServiceRoleProfileProperties[]>]`: List of roles for the cloud service.
      - `[Name <String>]`: Resource name.
      - `[SkuCapacity <Int64?>]`: Specifies the number of role instances in the cloud service.
      - `[SkuName <String>]`: The sku name. NOTE: If the new SKU is not supported on the hardware the cloud service is currently on, you need to delete and recreate the cloud service or move back to the old sku.
      - `[SkuTier <String>]`: Specifies the tier of the cloud service. Possible Values are <br /><br /> **Standard** <br /><br /> **Basic**
  - `[StartCloudService <Boolean?>]`: (Optional) Indicates whether to start the cloud service immediately after it is created. The default value is `true`.         If false, the service model is still deployed, but the code is not run immediately. Instead, the service is PoweredOff until you call Start, at which time the service will be started. A deployed service still incurs charges, even if it is poweredoff.
  - `[Tag <ICloudServiceTags>]`: Resource tags.
    - `[(Any) <String>]`: This indicates any property can be added to this object.
  - `[UpgradeMode <CloudServiceUpgradeMode?>]`: Update mode for the cloud service. Role instances are allocated to update domains when the service is deployed. Updates can be initiated manually in each update domain or initiated automatically in all update domains.         Possible Values are <br /><br />**Auto**<br /><br />**Manual** <br /><br />**Simultaneous**<br /><br />         If not specified, the default value is Auto. If set to Manual, PUT UpdateDomain must be called to apply the update. If set to Auto, the update is automatically applied to each update domain in sequence.

## RELATED LINKS

