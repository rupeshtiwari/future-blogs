---
title: What is Azure Virtual Machine Scale Sets
date: 2021-12-25 00:00 +0000
description:
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
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
  - tutorial
---

> Now a days distributed architecture is common. We deploy our services into many different servers to scale them up and meet our demand. However, managing all servers for **load-balancing, scaling, make application highly available** is super challenging on cloud. **Azure Virtual Machine Scale sets** is the great tool which does all of these automatically with **no extra cost** for you. Lets learn more about Scale sets in this article.

### Why Distributed Architecture?

- To provide **redundancy and improved performance**, applications are typically **distributed across multiple instances**.
- In order to give your customer faster speed and low latency you may need **load balancer** that **distributes requests** to one of the application **instances**.

## What is Azure Virtual Machine Scale Sets?

- Virtual Machine scale set let you **Create** and **Manage** a **group of load balanced VMs**.
- The number of VM instances can **automatically increase or decrease** in response to demand or a defined schedule.
- With virtual machine scale sets, you can build **large-scale services for areas such as compute, big data, and container workloads**.
- Scale sets provide **high availability to your applications**, and allow you to **centrally manage**, **configure**, and **update** a large number of VMs.
- **Consistent Configuration**: Virtual Machine scale sets are the objects that are used to run multiple instances of your application and maintain a consistent configuration across your environment.

{: .notice--info}
VMs in a scale set are identical, so you can create them from the same base operating system image.

### Why use Virtual Machine Scale Sets?

- **Maintenance Mode Support**: If you need to perform maintenance or update an application instance, your customers must be distributed to another available application instance.
- **Automatically increase VM instances**: To keep up with additional customer demand, you may need to increase the number of application instances that run your application.
  - Auto scale based on metrics.
  - Auto scale based on a defined schedule. Suppose starting next week you are going to have a heavy peak, for next 3 days. You can define a set schedule. For example, at 9 am on Jan 2nd 2021, increase the VM instance count to 50. And at 9PM on Jan 5th when your peak ends, bring the instance count back to your baseline configuration.
- **Easy to create and manage multiple VMs** : It maintains a consistent configuration (VM size, disk configuration) across your environment. All VM instances are created from the same base OS image and configuration. This approach lets you easily manage hundreds of VMs without additional configuration tasks or network management. For basic layer-4 traffic distribution it uses Azure Load Balancer. And for advanced layer-7 it uses Azure Application Gateway.
- **Provides high availability and application resiliency**: If one of these VM instances has a problem, customers continue to access your application through one of the other VM instances with minimal interruption.
- **Allows your application to automatically scale as resource demand changes**: Like it auto increase VM instances. It can also minimizes the number of unnecessary VM instances that run your application when demand is low, while customers continue to receive an acceptable level of performance
- **Works at large-scale** : Up to **1000** Azure VM, and custom VM images up to **600** VM.

## Scale set saves money 💰

The **management** and **automation** features, such as auto-scale and redundancy, incur **no additional charges** over the use of VMs. You only pay for the underlying compute resources such as the VM instances, load balancer, or Managed Disk storage.

## Benefits of Scale Set

| scenario                         | Manage VMs manually                                                                    |                                                                      Use VM Scale Set |
| :------------------------------- | :------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------: |
| Adding extra VM                  | Manually create, configure and ensure compliance                                       |                                       Automatically create from central configuration |
| Traffic Balancing & distribution | Manually                                                                               |         Automatically create and integrate Azure load balancer or Application Gateway |
| High availability and redundancy | Manually create Availability set or distribute and track VMs across Availability Zones | Automatic distribution of VM instances across Availability Zones or Availability Sets |
| Scaling of VMs                   | Manual monitoring and Azure Automation                                                 | Auto scale based on host metrics, in-guest metrics, Application Insights, or schedule |

## How to monitor scale sets

- Use [Azure Monitor for VMs](https://docs.microsoft.com/en-us/azure/azure-monitor/vm/vminsights-overview), to see metrics about VM CPU, memory, disk and network performance
- Enable monitoring [virtual machine scale set application](https://docs.microsoft.com/en-us/azure/azure-monitor/app/azure-vm-vmss-apps) with Application Insights to collect detailed information about your application including page views, application requests, and exceptions.
- Configure [availability test](https://docs.microsoft.com/en-us/azure/azure-monitor/app/monitor-web-app-availability) to check application availability to simulate user traffic.

{: .notice--success}
Learn more about [Azure Virtual Machine Scale Set](https://docs.microsoft.com/en-us/azure/virtual-machine-scale-sets/overview?context=/azure/virtual-machines/context/context)

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
