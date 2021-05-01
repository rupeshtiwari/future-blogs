---
title: Describe core Azure architecture components
date: 2022-05-07 00:00 +0000
description:
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: false
image: https://i.imgur.com/8mRbgqg.png
header:
  image: https://i.imgur.com/XMFI6bl.png
  teaser: https://i.imgur.com/8mRbgqg.png
  og_image: https://i.imgur.com/8mRbgqg.png
tags:
  - webdev
  - azure
  - tutorial
  - az-900
---

>  This is 3rd article on "**Azure Fundamentals part 1: Describe core Azure concepts**".

## Azure resources structure organization

Azure organizes structure for resources in four levels: management groups, subscriptions, resource groups, and resources.

👇 The top-down hierarchy of organization for these levels.

![](https://imgur.com/jEoLDBr.png){: .full}

- **Resources**: Resources are `instances of services` that you create, like virtual machines(VMs), storage accounts, web apps, virtual networks or SQL databases. An Azure resource is a manageable item that's available through Azure.
- **Resource groups**: Resources are combined into resource groups, which act as a `logical container` into which Azure resources like web apps, databases, and storage accounts are deployed and managed.
- **Subscriptions**: A subscription `groups together user accounts and the resources` that have been created by those user accounts. For each subscription, there are limits or quotas on the amount of resources that you can create and use. Organizations can use subscriptions to manage costs and the resources that are created by users, teams, or projects.
- **Management groups**: These groups help you `manage access, policy, and compliance` for multiple subscriptions. All subscriptions in a management group automatically inherit the conditions applied to the management group.

## Azure subscriptions and management groups

In order to start with Azure you must create at-least one subscription with Azure.

### Azure subscriptions

Using Azure requires an Azure subscription. A subscription provides you with **authenticated and authorized** access to Azure products and services. It also allows you to **provision** resources. An Azure subscription is a **logical unit** of Azure services that links to an Azure account, which is an identity in Azure Active Directory (Azure AD) or in a directory that Azure AD trusts.

![](https://imgur.com/EfIRY0g.png){: .full}

There are two types of subscription boundaries that you can use:

- **Billing boundary**: You can create multiple subscriptions for different types of `billing requirements`. Azure generates separate billing reports and invoices for each subscription so that you can organize and manage costs.

- **Access control boundary**: Azure applies `access-management policies` at the subscription level, and you can create separate subscriptions to reflect different organizational structures. An example within a business, you have different departments to which you apply distinct Azure subscription `policies`.

### Create additional Azure subscriptions

You might want to create additional subscriptions for **resource** or **billing** management purposes. For example, you might choose to create additional subscriptions to separate:

- **Environments:** Set up separate environments for `development` and `testing`, `security`, or to isolate data for `compliance` reasons. This design is particularly useful because resource `access control` occurs at the subscription level.

- **Organizational structures:** You could limit a team to `lower-cost` resources, while allowing the IT department a full range. This design allows you to `manage and control access` to the resources that users provision within each subscription.

- **Billing:** Because costs are first aggregated at the subscription level, you might want to create subscriptions to manage and track costs based on your needs. For instance, you might want to create one subscription for your `production` workloads and another subscription for your `development` and `testing` workloads.

- **Subscription limits:** Subscriptions are bound to some hard limitations. For example, the maximum number of Azure `ExpressRoute` circuits per subscription is `10`. If there's a need to go over those limits in particular scenarios, you might need additional subscriptions.

### Customize billing to meet your needs

If you have multiple subscriptions, you can organize them into **invoice sections**. Each invoice section is a line item on the invoice that shows the charges incurred that month. For example, you might need a single invoice for your organization but want to organize charges by department, team, or project.

Depending on your needs, you can set up multiple invoices within the same billing account. To do this, create additional **billing profiles**. Each billing profile has its own monthly invoice and payment method.

The following diagram shows an overview of how billing is structured.

![](https://imgur.com/TceedRv.png){: .full}


### Azure management groups

You organize subscriptions into containers called management groups and apply your **governance conditions** to the management groups. All subscriptions within a management group automatically inherit the conditions applied to the management group and must trust the same Azure AD tenant.

For example, you can apply policies to a management group that limits the regions available for VM creation. This policy would be applied to all management groups, subscriptions, and resources under that management group by only allowing VMs to be created in that region.

### Hierarchy of management groups and subscriptions

The following diagram shows an example of creating a hierarchy for governance by using management groups.

![](https://imgur.com/8rz4kAp.png){: .full}