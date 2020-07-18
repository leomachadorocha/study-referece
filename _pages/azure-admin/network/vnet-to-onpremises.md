---
permalink: /azure-admin/network/vnet-onpremises-connectivity/
title: "Azure Administrator > Network > Connectivity between VNETs and on-premises network"
---
#### ✔ _configure Site-to-Site VPN with PowerShell_

```powershell
# create local gateway
$localgw = New-AzLocalNetworkGateway
-Name
-ResourceGroupName
-Location
-GatewayIpAddress
-AddressPrefix

# create the VPN GATEWAY
$gateway = Get-AzVirtualNetworkGateway
-Name
-ResourceGroupName

# create the connection
New-AzVirtualNetworkGatewayConnection
-Name
-ResourceGroupName
-Location
-VirtualNetworkGateway $gateway
-LocalNetworkGateway $localgw
-ConnectionType IPsec
-SharedKey "key12345678"
```

#### ✔ _troubleshooting on-premises connectivity_

> if answers to questions 1 and 2 are NO, probabily the problem is on the VM created

![](/study-reference/assets/images/network/1.14.png)

> if answer to question 3 is NO, probabily the problem is related to the connectivity itself

![](/study-reference/assets/images/network/1.15.png)

![](/study-reference/assets/images/network/1.16.png)
