---
title: What is Microsoft Azure & How it works?
date: 2022-04-02 00:00 +0000
description: Learn the core concepts of Azure, understand the benefits, explain cloud concepts and describe the core azure architecture components. Finally summarize the geographic distribution concepts.
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
image: https://i.imgur.com/t9bDcJf.png
header:
  image: https://i.imgur.com/XMFI6bl.png
  teaser: https://i.imgur.com/t9bDcJf.png
  og_image: https://i.imgur.com/t9bDcJf.png
tags:
  - webdev
  - azure
  - tutorial
  - az900
---

> Learn what is Azure? How Azure works? and what are the hardware and software components that helps Azure to work. In this article I will try to give you some notes about Azure Basics. 

![](https://i.imgur.com/E80cISJ.gif)

### What is Azure?

Azure is a continually expanding set of cloud services that help your organization meet your current and future business challenges. [Learn More about What is Microsoft Azure here...](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-fundamentals/what-is-microsoft-azure)

### How Azure Works?

![](https://i.imgur.com/S2EB0iV.png){: .full}

Azure works with technology called **Virtualization**. Means separates the tight coupling between Hardware and its operating system. 

![](https://i.imgur.com/n2HRQdJ.png){: .full}

It uses **Hypervisor** to abstract away the coupling between hardware & software using Virtualization technique. 

![](https://i.imgur.com/xS7cXdH.png){: .full}

Azure has lots of Data Centers in many regions spreaded around the world. Azure uses virtualization in massive scale in all of its data-centers. 

**Data-center** has **Rack** and Rack has servers. Each server includes Hypervisor. 

There is **Network Switch** which allows connectivity to all of the servers. 

![](https://i.imgur.com/2urDTsz.png){: .full}


**One server** in the rack runs special software called as **Fabric Controller**.

![](https://i.imgur.com/Y32nDX0.png){: .full}

Azure Fabric Controller is connected to **ORCHESTRATOR** software. An Orchestrator responds to user requests. 


{: .notice--success}
🏆 **ProTip** \
\
In-fact **Azure Orchestrator** manages everything that happens in Azure. Like it can package the Virtual Machine request coming from user and send to Azure Fabric Controller to create it. 

![](https://i.imgur.com/TfOkyJV.png){: .full}

The users can make requests using the **Orchestrators Web API**.

![](https://i.imgur.com/o3Ol9NR.png){: .full}

The **Web API** can be called using **Azure Portal** and many tools. 

![](https://i.imgur.com/tDjFTKJ.png)


**For example**, when a user makes a request to create a Virtual Machine (VM) from Azure portal. The Orchestrator packages everything needed and chooses the best server Rack. And then sends the package and request to the Fabric Controller. Once the Fabric Controller has created the Virtual Machine, the user can connect to it. 

![](https://i.imgur.com/E80cISJ.gif)

## Azure Portal 

The Azure portal is a web-based, unified console that provides an alternative to command-line tools.

[Learn More ...](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-fundamentals/what-is-microsoft-azure)

![](https://i.imgur.com/pd9pVmS.png)

## What is Azure Marketplace?

[Azure Marketplace](https://azuremarketplace.microsoft.com/) helps connect users with Microsoft partners, independent software vendors, and startups that are offering their solutions and services, which are optimized to run on Azure.

![](https://i.imgur.com/3Vabs2f.png)
