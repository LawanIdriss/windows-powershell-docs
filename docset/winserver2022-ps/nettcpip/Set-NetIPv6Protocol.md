---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetIPv6Protocol.cdxml-help.xml
Module Name: NetTCPIP
ms.date: 12/20/2016
online version: https://docs.microsoft.com/powershell/module/nettcpip/set-netipv6protocol?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetIPv6Protocol
---

# Set-NetIPv6Protocol

## SYNOPSIS
Modifies the IPv6 protocol configuration.

## SYNTAX

```
Set-NetIPv6Protocol [-InputObject <CimInstance[]>] [-DefaultHopLimit <UInt32>]
 [-NeighborCacheLimitEntries <UInt32>] [-RouteCacheLimitEntries <UInt32>] [-ReassemblyLimitBytes <UInt32>]
 [-IcmpRedirects <IcmpRedirects>] [-SourceRoutingBehavior <SourceRoutingBehavior>]
 [-DhcpMediaSense <DhcpMediaSense>] [-MediaSenseEventLog <MediaSenseEventLog>] [-MldLevel <MldLevel>]
 [-MldVersion <MldVersion>] [-MulticastForwarding <MulticastForwarding>]
 [-GroupForwardedFragments <GroupForwardedFragments>] [-RandomizeIdentifiers <RandomizeIdentifiers>]
 [-AddressMaskReply <AddressMaskReply>] [-DeadGatewayDetection <DeadGatewayDetection>]
 [-UseTemporaryAddresses <UseTemporaryAddresses>] [-MaxTemporaryDadAttempts <UInt32>]
 [-MaxTemporaryValidLifetime <TimeSpan>] [-MaxTemporaryPreferredLifetime <TimeSpan>]
 [-TemporaryRegenerateTime <TimeSpan>] [-MaxTemporaryDesyncTime <TimeSpan>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetIPv6Protocol** cmdlet modifies the global IPv6 protocol configuration for a computer.
If you do not specify any parameters for the cmdlet, the cmdlet sets the default values for the IPv6 protocol configuration.

## EXAMPLES

### Example 1: Enable the DHCP Media Sense event log
```
PS C:\>Set-NetIPv6Protocol -MediaSenseEventLog Enabled
```

This command enables the DHCP Media Sense event log.

### Example 2: Increase the number of neighbors
```
PS C:\>Set-NetIPv6Protocol -NeighborCacheLimitEntries 1000
```

This command increases the size of the cache of on-link neighbors on the subnet that are no longer referenced to 1,000.
The default value is 256.

## PARAMETERS

### -AddressMaskReply
Specifies a value for address mask reply.
The cmdlet modifies the value for this setting.
Address mask reply specifies how the computer responds to ICMP address mask packets.
The acceptable values for this parameter are:

- Enabled.
The computer responds to ICMP address mask packets.
- Disabled.
The computer does not respond to ICMP address mask packets.

```yaml
Type: AddressMaskReply
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeadGatewayDetection
Specifies an array of values for dead gateway detection. The cmdlet gets IPv6 protocol
configurations that have these values.
Dead gateway detection is a feature that identifies gateways that are not operating properly and
switches the computer to a new default gateway if available.
The acceptable values for this parameter are:

- Enabled
- Disabled

```yaml
Type: DeadGatewayDetection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultHopLimit
Specifies a value for the default hop limit.
The cmdlet modifies the value for this setting.
This parameter sets the default value for the **CurrentHopLimit** property in the IP interface.
The current hop limit is the value that the IP interface writes in the hop limit field in all outbound IPv6 traffic.
When routers forward a packet, they decrement the hop limit by 1 and discard the packet when the hop limit is 0.
The default value is 128.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DhcpMediaSense
Specifies a value for Media Sense.
The cmdlet modifies the value for this setting.

Media Sense provides a mechanism for the network adapter to notify the protocol stack of media connect and disconnect events.
These events trigger the DHCP client to take an action, such as attempting to renew a DHCP lease or removing routes that are related to a disconnected network.
When Media Sense is enabled, the network parameters on the laptop of a roaming user are automatically and transparently updated without requiring a restart when the user moves from one location to another.
The acceptable values for this parameter are:

- Enabled
- Disabled

The default value is Enabled.

```yaml
Type: DhcpMediaSense
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupForwardedFragments
Specifies a value for group forwarded fragments.
The cmdlet modifies the value for this setting.
Group forwarded fragments specifies whether the IP interface collects fragments into groups before it forwards the fragments.
This parameter sets the **GroupForwardedFragments** property in the IP interface.
The acceptable values for this parameter are:

- Enabled.
The IP interface collects IPv6 protocol fragments into groups before it forwards the fragments.
- Disabled.
The IP interface does not collect IPv6 protocol fragments into groups before it forwards the fragments.

The default value is Disabled.

```yaml
Type: GroupForwardedFragments
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IcmpRedirects
Specifies a value for Internet Control Message Protocol (ICMP) redirect.
The cmdlet modifies the value for this setting.
ICMP redirect specifies whether to update the path cache in response to ICMP redirect packets.
This parameter sets the **IcmpRedirects** property in the IP interface.
The acceptable values for this parameter are:

- Enabled.
The IP interface updates the path cache in response to ICMP redirect packets.
- Disabled.
The IP interface does not update the path cache in response to ICMP redirect packets.

The default value is Enabled.

```yaml
Type: IcmpRedirects
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxTemporaryDadAttempts
Specifies a value for the maximum number of duplicate address detection attempts for temporary addresses.
The cmdlet modifies the value for this setting.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: MaxDadAttempts

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryDesyncTime
Specifies a value for the maximum time to desynchronize temporary address preferred lifetimes.
The cmdlet modifies the value for this setting.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: MaxRandomTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryPreferredLifetime
Specifies an array of values, as **TimeSpan** objects, for the maximum preferred lifetime over which to prefer a temporary address.
The cmdlet gets IPv6 protocol configurations that have these values.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: MaxPreferredLifetime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxTemporaryValidLifetime
Specifies a value, as a **TimeSpan** object, for the maximum lifetime over which a temporary address is valid.
The cmdlet modifies the value for this setting.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: MaxValidLifetime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaSenseEventLog
Specifies a value for Media Sense event log.
The cmdlet modifies the value for this setting.
The acceptable values for this parameter are:

- Enabled.
The IP interface logs DHCP Media Sense events in the event log for troubleshooting purposes.
- Disabled.
The IP interface does not log DHCP Media Sense events in the event log.

The default value is Disabled.

```yaml
Type: MediaSenseEventLog
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MldLevel
Specifies a value for the level of Multicast Listener Discovery (MLD) support.
The cmdlet modifies the value for this setting.
The acceptable values for this parameter are:

- All.
The computer can send and receive multicast packets.
- None.
The computer cannot send or receive multicast packets.
- SendOnly.
The computer can send but not receive multicast packets.

```yaml
Type: MldLevel
Parameter Sets: (All)
Aliases:
Accepted values: None, SendOnly, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MldVersion
Specifies a value for the maximum version of Multicast Listener Discovery that the host supports.
The cmdlet modifies the value for this setting.

```yaml
Type: MldVersion
Parameter Sets: (All)
Aliases:
Accepted values: Version1, Version2

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MulticastForwarding
Specifies a value for multicast forwarding.
The cmdlet modifies the value for this setting.
The acceptable values for this parameter are:

- Enabled.
The computer can forward multicast packets.
- Disabled.
The computer cannot forward multicast packets.

The default value is Disabled.

```yaml
Type: MulticastForwarding
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NeighborCacheLimitEntries
Specifies the maximum number of entries in the neighbor cache, which consists of all dynamic neighbors no longer referenced.
The cmdlet modifies the value for this setting.

The default value is 256.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: NeighborCacheLimit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RandomizeIdentifiers
Specifies a value for the randomization of identifiers.
The cmdlet modifies the value for this setting.
The acceptable values for this parameter are:

- Enabled.
The IP interface randomizes identifiers when it creates an IP address.
- Disabled.
The IP interface does not randomize identifiers when it creates an IP address.

The default value is Enabled.

```yaml
Type: RandomizeIdentifiers
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReassemblyLimitBytes
Specifies a value for the maximum size of the reassembly buffer.
The cmdlet modifies the value for this setting.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: ReassemblyLimit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RouteCacheLimitEntries
Specifies a value for the maximum number of route cache entries.
The cmdlet modifies the value for this setting.

The default value is 128.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: RouteCacheLimit

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRoutingBehavior
Specifies a value for source routing behavior.
The cmdlet modifies the value for this setting.
The acceptable values for this parameter are:

- DontForward.
The computer can receive but not forward source-routed packets.
- Drop.
The computer drops source-routed packets.

The default value is DontForward.

```yaml
Type: SourceRoutingBehavior
Parameter Sets: (All)
Aliases:
Accepted values: Forward, DontForward, Drop

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TemporaryRegenerateTime
Specifies a value, as a **TimeSpan** object, for the time prior to deprecating a temporary address when a new address is generated.

The cmdlet modifies the value for this setting.

```yaml
Type: TimeSpan
Parameter Sets: (All)
Aliases: RegenerateTime

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell&reg; calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTemporaryAddresses
Specifies a value for temporary addresses.
The cmdlet modifies the value for this setting.

- Always.
The computer always generates temporary addresses by using random numbers.
- Counter.
The computer generates temporary addresses by using the interface identifier.
You typically use this identifier for test purposes.
- Disabled.
The computer does not use temporary addresses.
- Enabled.
The computer uses temporary addresses.

```yaml
Type: UseTemporaryAddresses
Parameter Sets: (All)
Aliases:
Accepted values: Disabled, Enabled, Always

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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPv6Protocol
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-NetIPv6Protocol](./Get-NetIPv6Protocol.md)

[Set-NetIPv4Protocol](./Set-NetIPv4Protocol.md)

