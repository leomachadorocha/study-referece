---
permalink: /azure-admin/network/peering/
title: "Azure Administrator > Network > Peering"
---
#### ✔ _peering_

> **VNET PEERING** : VNETs in SAME region
>
> **GLOBAL VNET PEERING** : VNETs in DIFFERENT regions
>
> **CROSS-TENANT VNET PEERING** : must configure in CLI, PowerShell or ARM templates (not Portal)

![](/study-reference/assets/images/network/1.1.png)

![](/study-reference/assets/images/network/1.2.png)

![](/study-reference/assets/images/network/1.3.png)

![](/study-reference/assets/images/network/1.4.png)

![](/study-reference/assets/images/network/1.5.png)

> for complex networks use **IPsec Site-to-Site**

> low latency, high bandwidth connection
>
> data transfer across subscriptions and regions
>
> 2 peering connections are required :
> * A -> B
> * B -> A
>
> NOT TRANSITIVE :
> * A <-> B&nbsp;
> * B <-> C &nbsp;
> * A <-X-> C
>
> no VNET GATEWAY is necessary

#### ✔ _configuring Peering with PowerShell_

```powershell
# get information about the VNETs
Get-AzVirtualNetwork
-Name <VNET-NAME)
-ResourceGroup <RG-NAME>

# create the peer
Add-AzVirtualNetworkPeering
-Name <PEER-NAME>
...
```

#### ✔ _VNET-to-VNET Connection_

> 1 - create the "Gateway subnet" in both VNETs

![](/study-reference/assets/images/network/1.8.png)

![](/study-reference/assets/images/network/1.9.png)

![](/study-reference/assets/images/network/1.10.png)

![](/study-reference/assets/images/network/1.11.png)

> 2 - create the VIRTUAL NETWORK GATEWAY in both VNETs

![](/study-reference/assets/images/network/1.12.png)

> 3 - create 2 VPN CONNECTIONS between the two Gateways

![](/study-reference/assets/images/network/1.13.png)

#### ✔ _create the Gateway with PowerShell_

```powershell
# create the gateway
Add-AzVirtualNetworkGateway
-Name <GATEWAY-NAME>
...
```

#### ✔ _verify connectivity between VNETs_

![](/study-reference/assets/images/network/1.6.png)

![](/study-reference/assets/images/network/1.7.png)