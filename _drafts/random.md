---
title: Configuring Azure Storage Account
description: Big picture of Azure storage
---

# In Azure Storage Account

# Feature

Feature is capability of a service. Like **Metrics Explorer** is a feature of **Azure Monitor** Service.

# Service

File, Blob, Queues, Azure Monitor

# Resource

Container  
Service  
Object  

# Log Analytics Workspace

Log Analytics Workspace is actually a **Azure Data Lake**.


# VM Scale Set
![](https://imgur.com/uGhua33.png)
- VM scale set is an Azure service allows you to run  
- It contains multiple VMs with the same image and contents. 
- It has instances, which are the VMs. 
- You can create more VMs by scaling it up from Azure Portal or Enable auto scale.

## SAN
SAN: [storage area network (SAN) ](https://docs.microsoft.com/en-US/azure/migrate/prepare-for-migration#configure-san-policy)
By default, Azure VMs are assigned drive D to use as temporary storage
-   This drive assignment causes all other attached storage drive assignments to increment by one letter.
-   For example, if your on-premises installation uses a data disk that is assigned to drive D for application installations, the assignment for this drive increments to drive E after you migrate the VM to Azure.
-   To prevent this automatic assignment, and to ensure that Azure assigns the next free drive letter to its temporary volume, set the storage area network (SAN) policy to **OnlineAll**:


## What is Rack?

## What is domain? update domain ? fault domain ?