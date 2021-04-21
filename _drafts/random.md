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

- This drive assignment causes all other attached storage drive assignments to increment by one letter.
- For example, if your on-premises installation uses a data disk that is assigned to drive D for application installations, the assignment for this drive increments to drive E after you migrate the VM to Azure.
- To prevent this automatic assignment, and to ensure that Azure assigns the next free drive letter to its temporary volume, set the storage area network (SAN) policy to **OnlineAll**:

## ARR

**Application Request Routing (ARR)** is a feature where when a client (or browser) request to any Azure based website, a cookie will be created and stick to the first time request received web site instance.

## PIP

A virtual machine running in Azure can now be associated with a direct and publicly accessible IP address that sticks to the VM for its lifetime.

## NSG

A **network security group (NSG)** contains a list of security rules that allow or deny network traffic to resources connected to Azure Virtual Networks (VNet). NSGs can be associated to subnets or individual network interfaces (NIC) attached to VMs.

## NIC
A [Network Interface (NIC)](https://docs.microsoft.com/en-us/azure/virtual-network/virtual-network-network-interface) enables an Azure Virtual Machine to communicate with internet, Azure, and on-premises resources. When creating a virtual machine using the Azure portal, the portal creates one network interface with default settings for you. 

## RBAC

**Role-based access control (RBAC)** is a policy-neutral access-control mechanism defined around roles and privileges. The components of RBAC such as role-permissions, user-role and role-role relationships make it simple to perform user assignments.

## CMDB
 Configuration Management Database 

## Rack

A Rack has servers (Virtual Machines) in a data-center.

 ## SKU
 Stock Keeping Unit (SKU) Learn more about [SKU types in Azure](https://docs.microsoft.com/en-us/rest/api/compute/resourceskus/list)
 
