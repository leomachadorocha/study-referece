---
permalink: /azure-admin/identities/mfa/
title: "Azure Administrator > Identities > Multi-factor authentication (103)"
---
#### ✔ _configuring MFA (recomended method)_

> the recomended way is from Conditional Access Policy
>
> works only for MFA on the cloud

![](/study-reference/assets/images/identities/6.1.png)

#### ✔ _configuring MFA (traditional method)_

> the traditional way is enable by changing the user state
>
> works only for MFA on the cloud AND MFA servers
>
> it overrides the Conditional Access Policy

![](/study-reference/assets/images/identities/6.2.png)

![](/study-reference/assets/images/identities/6.3.png)

#### ✔ _configuring with PowerShell_

```powershell
# enables MFA for an individual user
Set-MsolUser 
-UserPrincipalName $user
-StrongAuthenticationRequirements $sta
```