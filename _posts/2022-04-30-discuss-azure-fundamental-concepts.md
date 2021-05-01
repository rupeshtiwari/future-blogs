---
title: Discuss Azure Fundamental Concepts
date: 2022-04-30 00:00 +0000
description: Did you know your company can take advantage of using many Azure cloud computing which will help your company to reduce its overall computing costs? Did you know the benefits(availability, scalability, and geographic distribution) of cloud computing? Did you know what are the categories(IaaS, PaaS, SaaS) of cloud computing? And, can you differences between types(public, private, and hybrid) of cloud computing? In this article we will summaries all of these!
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
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

> Did you know your company can take **advantage** of using many Azure cloud computing which will help your company to reduce its overall computing costs? Did you know the **benefits**(availability, scalability, and geographic distribution) of cloud computing? Did you know what are the **categories**(IaaS, PaaS, SaaS) of cloud computing? And, can you differences between **types**(public, private, and hybrid) of cloud computing? In this article we will summaries all of these! This is 2nd article on "**Azure Fundamentals part 1: Describe core Azure concepts**".

## Describe the benefits of cloud computing

### What are some cloud computing advantages?

{: .notice--success}
🏆 **ProTip** \
\
Remember the sentence [**GASHED**](https://dictionary.cambridge.org/us/dictionary/english/gashed).
**G** = **G**eo-distribution
**A** = **A**gility
**S** = **S**calability
**H** = **H**igh availability
**E** = **E**lasticity
**D** = **D**isaster recovery

👇 Below are also called as cloud concepts:

- **Geo-distribution**: You can deploy apps and data to regional datacenters around the globe, thereby ensuring that your customers always have the best performance in their region.

- **Agility**: Deploy and configure cloud-based resources quickly as your app requirements change.

- **Scalability**: Apps in the cloud can scale _vertically_ and _horizontally_:

  - Scale vertically to increase compute capacity by adding RAM or CPUs to a virtual machine.
  - Scaling horizontally increases compute capacity by adding instances of resources, such as adding VMs to the configuration.

- **High availability**: Depending on the service-level agreement (SLA) that you choose, your cloud-based apps can provide a continuous user experience with no apparent downtime, even when things go wrong.

- **Elasticity**: You can configure cloud-based apps to take advantage of autoscaling, so your apps always have the resources they need. It can decrease resource if they are underused or increase if demand is high.

- **Disaster recovery**: By taking advantage of cloud-based backup services, data replication, and geo-distribution, you can deploy your apps with the confidence that comes from knowing that your data is safe in the event of disaster.

### Cloud computing is a consumption-based model

End users only pay for the resources that they use. Whatever they use is what they pay for.

A consumption-based model has many benefits, including:

- No upfront costs.
- No need to purchase and manage costly infrastructure that users might not use to its fullest.
- The ability to pay for additional resources when they are needed.
- The ability to stop paying for resources that are no longer needed.

### Capital expenses vs. operating expenses

There are two different types of expenses:

- **Capital Expenditure (CapEx)** requires significant up-front financial costs, as well as ongoing maintenance and support expenditures.

- **Operational Expenditure (OpEx)**: OpEx is a consumption-based model, so Your company is only responsible for the cost of the computing resources that it uses.

## Describe the different categories of cloud services

### What are cloud service models?

There are 3 Cloud Service Models:

- **Infrastructure-as-a-Service (IaaS)** the cloud provider will keep the hardware up-to-date, but operating system maintenance and network configuration is up to you as the cloud tenant.

- **Platform-as-a-Service (PaaS)** the cloud provider manages the virtual machines and networking resources, and the cloud tenant deploys their applications into the managed hosting environment.

- **Software-as-a-Service(SaaS)** the cloud provider manages all aspects of the application environment, such as virtual machines, networking resources, data storage, and applications. The cloud tenant only needs to provide their data to the application managed by the cloud provider.

The following illustration demonstrates the services that might run in each of the cloud service models.

![](https://imgur.com/Ia6D7IM.png){: .full}

The following chart illustrates the various levels of responsibility between a cloud provider and a cloud tenant.

![](https://imgur.com/tCJ0p7V.png){: .full}

### What is serverless computing?

It is a PaaS model. Normally used by developers to build applications faster. With serverless applications, the cloud service provider automatically provisions, scales, and manages the infrastructure required to run the code. Serverless architectures are highly scalable and event-driven, only using resources when a specific function or trigger occurs.

{: .notice--success}
🏆 **ProTip** \
\
The "serverless" name comes from the fact that the tasks associated with infrastructure provisioning and management are invisible to the developer. This approach enables developers to increase their focus on the business logic, and deliver more value to the core of the business.

## Describe the different types of cloud computing

### What are public, private, and hybrid clouds?

There are three deployment models:

- **Public cloud** is cloud resources, such as servers and storage, are owned and operated by a third-party cloud service provider, and delivered over the internet.

- **Private cloud** consists of computing resources used exclusively by users from one business or organization. A private cloud can be physically located at your organization's on-site (on-premises) datacenter, or it can be hosted by a third-party service provider.

- **Hybrid cloud** is a computing environment that combines a public cloud and a private cloud by allowing data and applications to be shared between them.

![](https://imgur.com/6DirYOj.png){: .full}

## References

- [Describe the different categories of cloud services](https://docs.microsoft.com/en-us/learn/modules/fundamental-azure-concepts/categories-of-cloud-services)
- [Describe the different types of cloud computing](https://docs.microsoft.com/en-us/learn/modules/fundamental-azure-concepts/types-of-cloud-computing)
