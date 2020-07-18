---
permalink: /azure-admin/network/connect-vnet-onpremises/
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