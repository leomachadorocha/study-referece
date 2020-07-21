---
permalink: /azure-admin/network/nic/
title: "Azure Administrator > Network > NIC"
---

>
> OBS: in the Portal, we can not create a NIC with a Public IP Address associate with it
>
#### ✔ _configure NIC with PowerShell_

```powershell
# get information
Get-AzNetworkInterface [-Name]

# create NIC with PUBLIC IP ADDRESS (PIP)
$vnet = Get-AzVirtualNetwork
-Name
-ResourceGroupName

$subnet = Get-AzVirtualNetworkSubnetConfig
-Name
-VirtualNetwork $vnet

$PIP = Get-AzPublicIPAddress
-Name "myPIP"
-ResourceGroupName

$IPConfig1 = New-AzNetworkInterfaceIpConfig
-Name "IPConfig-1"
-Subnet $subnet
-PublicIpAddress $PIP
-Primary

$NIC = New-AzNetworkInterface
-Name "myNIC"
-ResourceGroupName
-Location
-IpConfiguration $IPConfig1
```