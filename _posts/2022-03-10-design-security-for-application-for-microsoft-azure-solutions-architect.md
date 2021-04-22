---
title: Design Security for Application for Microsoft Azure Solutions Architect
date: 2022-03-10 00:00 +0000
description:
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
toc_sticky: true
image: https://i.imgur.com/7I0NoBe.png
header:
  image: https://i.imgur.com/vce9zzl.png
  teaser: https://i.imgur.com/7I0NoBe.png
  og_image: https://i.imgur.com/7I0NoBe.png
tags:
  - azure
  - webdev
  - beginners
  - az304
---

> Are you wondering how your function app authenticate & authorize to read or write to Azure SQL table? Do you think how your web application will get programmatically permission to write to storage queue? How would you mange the secrets and credentials used by resourced in your Azure cloud? Are you tired managing credentials? Well in this article, I will explain everything about designing your Azure enterprise resources. Such that all of the applications & azure resources authenticate using credentials and other secretes. And they can communicate to each other seamlessly without you to do any extra work.

## Don't Do below with passwords

- Hard code in source code
- Place in config file
- Use environment variables.

## Do below to authenticate

- Resource-based authentication
- Use Azure Key Vault to store secretes

## Manually Managing Identities

- You create Service Principle in Azure AD
- Your application authenticate using certificate, secrete or password
- Your Resources under process has to store the certificate, secrete or password

## Using Managed Identities

Managed identities provide an `identity` for `applications` to use when `connecting` to `resources` that support `Azure Active Directory (Azure AD) authentication`. Applications may use the managed identity to obtain Azure AD tokens.

{: .notice--success}
🏆 **ProTip** \
\
Only resources that support **Azure Active Directory (Azure AD) authentication** & has a authorization form can allow to connect themselves to other resources using Managed Identities.

For example, an application may use a managed identity to access resources like [Azure Key Vault](https://docs.microsoft.com/en-us/azure/key-vault/general/overview) where developers can store credentials in a secure manner. You can request different token for Azure Storage Accounts. Or you can read secrete from Azure Key Vault and access to Azure blob storage if you have read permission.

{: .notice--success}
🏆 **ProTip** \
\
Managed Identities is **free of cost** 💰 no additional charges to use.

![](https://imgur.com/6kH5Py7.png){: .full}

There are two types of managed identities:

### 1. System-Assigned Identity

System-Assigned Identity is one-to-one relationship between identity and service. When you enable a system-assigned managed identity an identity is created in Azure AD that is tied to the lifecycle of that service instance. So when the resource is deleted, Azure automatically deletes the identity for you. For example, an application that runs on a single virtual machine.

{: .notice--success}
🏆 **ProTip** \
\
When you have VM you give system-assigned when you delete the VM your identity from Azure AD gets deleted.

### 2. User-assigned Identity

User-assigned is one-to-many relationship between identity and services. You can [create a user-assigned managed identity](https://docs.microsoft.com/en-us/azure/active-directory/managed-identities-azure-resources/how-to-manage-ua-identity-portal) and assign it to one or more instances of an Azure service. For example, a workload where multiple virtual machines need to access the same resource

{: .notice--success}
🏆 **ProTip** \
\
When you create user-assigned identity then you can use them in many Function Apps, many Virtual Machines, and as many resources as you want.

### Assigning System Managed Identity Roles

![](https://imgur.com/W6ULtIM.png){: .full}

## References

1. [Managed Identities Azure Resource](https://docs.microsoft.com/en-us/azure/active-directory/managed-identities-azure-resources/overview)


---

_Thanks for reading my article till end. I hope you learned something special today. If you enjoyed this article then please share to your friends and if you have suggestions or thoughts to share with me then please write in the comment box._

## Become full stack developer 💻

{: .notice--info}
I teach at [Fullstack Master](https://www.fullstackmaster.net). If you want to become **Software Developer** and grow your carrier as new **Software Engineer** or **Lead Developer/Architect**. Consider subscribing to our full stack development training programs. You will learn **Angular, RxJS, JavaScript, System Architecture** and much more with lots of **hands on coding**. We have All-Access Monthly membership plans and you will get unlimited access to all of our **video** courses, **slides**, **download source code** & **Monthly video calls**.

- Please subscribe to **[All-Access Membership PRO plan](https://www.fullstackmaster.net/pro)** to access _current_ and _future_ **angular, node.js** and related courses.
- Please subscribe to **[All-Access Membership ELITE plan](https://www.fullstackmaster.net/elite)** to get everything from PRO plan. Additionally, you will get access to monthly **live Q&A video call** with `Rupesh` and you can ask **_doubts/questions_** and get more help, tips and tricks.

{: .notice--warning}
Your bright future is waiting for you so visit today [FullstackMaster](www.fullstackmaster.net) and allow me to help you to board on your dream software company as a new **Software Developer, Architect or Lead Engineer** role.

<div class="notice--success">
<strong>💖 Say 👋 to me!</strong>
<br>Rupesh Tiwari
<br>Founder of <a href="https://www.fullstackmaster.net">Fullstack Master </a>
<br>Email: <a href="mailto:rupesh.tiwari.info@gmail.com?subject=Hi">rupesh.tiwari.info@gmail.com</a>
<br>Website: <a href="https://www.rupeshtiwari.com">RupeshTiwari.com </a>
</div>
![](https://imgur.com/a32nUcu.png)
