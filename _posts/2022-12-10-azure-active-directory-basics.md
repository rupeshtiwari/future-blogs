---
title: Azure Active Directory Basics
date: 2022-12-10 00:00 +0000
description: Azure Active Directory helps you to secure your cloud by providing identity and access management and single sign on.
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
image: https://i.imgur.com/qxXxmBa.png
header:
  image: https://i.imgur.com/zipiW93.png
  teaser: https://i.imgur.com/qxXxmBa.png
  og_image: https://i.imgur.com/qxXxmBa.png
tags:
  - webdev
  - tutorial
  - beginners
  - cloud
---

> Securing your workload and datacenter over the cloud is very challenging. You want your resources to be protected by both machines and users. Azure Active directory helps you to achieve single sign on and provides you centralize identity and access management across your subscriptions. Let's learn more basic concepts about Azure Active Directory in this article.

Microsoft provides Azure AD for developers and Microsoft Identity platform to help both programmatic and operational support for single-sign on, Identity and access management.

## What is Azure Active Directory?

[Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/what-is-application-management) is an Identity and Access Management (IAM) system for the Microsoft cloud. A centralized identity system provides a single place to store user information that can then be used by all applications. These systems have come to be known as Identity and Access Management (IAM) systems. Azure AD performs the authentication using the tenant directory stored in the cloud. Making Azure AD aware of these apps, and how it should handle them, is known as application management. You manage applications on the Enterprise applications page located in the Manage section of the Azure Active Directory portal.

## How does Azure AD work with apps?

Azure AD sits in the middle and provides [identity management](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/what-is-application-management) for cloud and on-premises apps. You can integrate on-premises apps using App Proxy.
![](https://i.imgur.com/3w439fV.png){: .full}

## What is an Azure account?

To create or work with an Azure subscription, you must have an Azure account. An Azure account is simply an identity in Azure Active directory (Azure AD).

## How to take Microsoft Azure Subscription?

I want to create an Azure subscription & I do not have an Azure Account. THen if I have account in below directories then I am okay I can create subscriptions:

1.  Personal Microsoft Account
2.  School Organization
3.  Work Organization

I can create subscriptions in AZure using any account from the above-3 directories.

## Can Azure Active Directory work with Other Organizations?

To create or work with an Azure subscription, you must have an Azure account. An Azure account is simply an identity in Azure AD or in a directory, such as a work or school organization, that Azure AD trusts. If you don't belong to such an organization, you can always create a subscription by using your Microsoft Account, which is trusted by Azure AD. 
![](https://i.imgur.com/dkAgahS.png){: .full}

## Relationship between Azure Subscription & Azure Active Directory

Every Azure subscription has a trust relationship with an Azure AD instance. This means that it trusts that directory to authenticate users, services, and devices. Multiple subscriptions can trust the same directory, but a subscription trusts only one directory.
![](https://i.imgur.com/K6yDuoy.png){: .full}

![](https://i.imgur.com/RgpiTHu.png){: .full}

## Creating Groups inside Active Directory

As well as defining individual Azure account identities, also called users, you can define groups in Azure AD. Creating user groups is a good way to manage access to resources in a subscription by using role-based access control (RBAC).
![](https://i.imgur.com/Kfr6k69.png){: .full}

## Azure AD Subscription and Resource Group Relationship

So basically every subscription trust on azure active directory. The users and groups within directory can be assigned role based access control (RBAC) to access resources like storage, compute, network, database and more.

![](https://i.imgur.com/BzP0hcx.png){: .full}
