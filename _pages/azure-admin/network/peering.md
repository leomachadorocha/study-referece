---
permalink: /azure-admin/network/peering/
title: "Azure Administrator > Network > Peering"
---
> **VNET PEERING** : vnet's in SAME regions
>
> **GLOBAL VNET PEERING** : vnet's in DIFFERENT regions
>
> **CROSS-TENANT VNET PEERING** : must configure in CLI, PowerShell or ARM templates (not Portal)

![](/study-reference/assets/images/network/1.1.png)

> for complex networks use **IPsec Site-to-Site**

> low latency, high bandwidth connection
>
> data transfer across subscriptions and regions
>
> 2 peering connections are required : A -> B || B -> A
>
> NOT TRANSITIVE : A <-> B || B <-> C || A <-X-> C

#### ✔ _VNET peering_