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

> for complex networks use **IPsec Site-to-Site**

> low latency, high bandwidth connection
>
> data transfer across subscriptions and regions
>
> 2 peering connections are required : A -> B | B -> A
>
> NOT TRANSITIVE :&nbsp;
> * A <-> B&nbsp;
> * B <-> C &nbsp;
> * A <-X-> C

#### ✔ _configuring with PowerShell_

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