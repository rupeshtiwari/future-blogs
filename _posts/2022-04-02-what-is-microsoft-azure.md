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
image: https://i.imgur.com/8mRbgqg.png
header:
  image: https://i.imgur.com/XMFI6bl.png
  teaser: https://i.imgur.com/8mRbgqg.png
  og_image: https://i.imgur.com/8mRbgqg.png
tags:
  - webdev
  - azure
  - tutorial
  - az 900
---

> Learn what is Azure? How Azure works? and what are the hardware and software components that helps Azure to work. In this article I will try to give you some notes about Azure Basics. This article is part of **Core Azure Concepts**

![](https://i.imgur.com/E80cISJ.gif)

## What is Azure?

Azure is a continually expanding set of cloud services that help your organization meet your current and future business challenges. [Learn More about What is Microsoft Azure here...](https://docs.microsoft.com/en-us/learn/modules/intro-to-azure-fundamentals/what-is-microsoft-azure)

## How Azure Works?

![](https://i.imgur.com/S2EB0iV.png){: .full}

Azure works with technology called **Virtualization**. Means separates the tight coupling between Hardware and its operating system.

![](https://i.imgur.com/n2HRQdJ.png){: .full}

It uses **Hypervisor** to abstract away the coupling between hardware & software using Virtualization technique.

![](https://i.imgur.com/xS7cXdH.png){: .full}

Azure has lots of Data Centers in many regions spread around the world. Azure uses virtualization in massive scale in all of its data-centers.

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

## What is Cloud computing?

It's the delivery of computing services over the internet, which is otherwise known as the cloud. These services include servers, storage, databases, networking, software, analytics, and intelligence. Cloud computing offers faster innovation, flexible resources, and economies of scale.

{: .notice--success}
🏆 **ProTip** \
\
Save your company money 💰 "You'll only need to pay for **the resources and computing time that you use**".

## Advantages of Cloud Computing

{: .notice--success}
🏆 **ProTip** \
\
Remember this word for advantages of Azure cloud computing **GRADES**

**G** = Geo-distribution
**R** = Reliability
**A** = Agility
**D** = Disaster Recovery
**E** = Elasticity
**S** = Scalability

For example in your company if you have IT team and Software Development team. And IT specialist deploys hardware and software developers create website. So you must try Azure and see:

- How Azure improves the site's availability and scalability.
- How cloud computing can make your hardware deployment processes faster.

## Cloud Service Models

- IaaS
- PaaS
- SaaS

![](https://i.imgur.com/mXfV7EH.png){: .full}

![](https://i.imgur.com/N2PeaDj.png){: .full}

{: .notice--success}
🏆 **ProTip** \
\
 In an IaaS environment, the cloud tenant is **NOT** responsible for routine hardware maintenance.

## Cloud Deployment Models

Public, Private and Hybrid

![](https://i.imgur.com/2aB3fq3.png){: .full}

## Azure Facts to remember

- Three cloud computing deployment models are public cloud, private cloud, and hybrid cloud.
- Cloud computing typically decreases your operating expenses.
- IaaS, PaaS, and SaaS are examples of cloud computing service models.
- Cloud computing resources are **NOT** usually limited to specific geographic regions.

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
