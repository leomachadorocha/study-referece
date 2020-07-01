---
permalink: /azure-admin/identities/create-users/
title: "Azure Administrator > Identities > Create and manage users"
---
#### ✔ _kind of users_

> Azure Active Directory          = cloud users
>
> Windows Server AD               = synchronized users
>
> External Azure Active Directory = users from other tenants
>
> Microsoft Account               = are the Guest Users

![](/assets/images/identities/2.1.png)

&nbsp;
#### ✔ _create users with CLI_

```bash
az ad user create
--display_name "John Doe"
--password "p4ssw0rd"
--user-principal-name "john.doe@contoso.com"
--force-change-password-next-login true \
--mail-nickname "Johnny D."
```
&nbsp;
#### ✔ _create users with PowerShell_

```powershell
# Create a password object
$PasswordProfile = New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile

# Assign the password
$PasswordProfile.Password = "p4ssw0rd"

# Create the new user
New-AzureADUser -AccountEnabled $True
-DisplayName "John Doe"
-PasswordProfile $PasswordProfile
-UserPrincipalName "john.doe@contoso.com"
-MailNickName "Johnny D."
```
&nbsp;
#### ✔ _perform bulk user updates_

![](/assets/images/identities/2.3.png)

![](/assets/images/identities/2.2.png)

&nbsp;
#### ✔ _manage guest accounts_

> same as B2B collaboration users

> can invite  to:
>
> * directory
>
> * group
>
> * application

```powershell
# Send an invitation email
New-AzureADMSInvitation
```
