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

## VPN

Virtual Private Network (VPN). In Azure VPN is a type of Virtual Network Gateway.

## VIP

Virtual IP address. VIP is an IP address that doesn't correspond to an actual physical network interface.

## BGP

“Border Gateway Protocol (BGP)" is a standardized exterior gateway protocol designed to exchange routing and reachability information between autonomous systems (AS) on the Internet.

## IKE

Internet Key Exchange

## IPV

Internet Protocol Version (IPV). **IPv6** is more advanced and has better features compared to **IPv4**.

## LNG

The Local Network Gateway (LNG) typically refers to your on-premises location. [Learn...](https://docs.microsoft.com/en-us/azure/vpn-gateway/vpn-gateway-create-site-to-site-rm-powershell)

## CIDR

Classless Inter-Domain Routing (CIDR).

## Azure Fundamentals Certification (AZ 900)

**Azure Fundamentals** certification needs 6 part to be finished.

1. Part 1: Describe core Azure concepts
   1. Introduction to Azure fundamentals
   2. Discuss Azure fundamental concepts
   3. Describe core Azure architecture components
2. Part 2: Describe core Azure services
3. Part 3: Describe core solutions and management tools on Azure
4. Part 4: Describe general security and network security features
5. Part 5: Describe identity, governance, privacy, and compliance features
6. Part 6: Describe Azure cost management and service level agreements

## Part 1: Describe core Azure concepts

You will learn below things:

- Understand the **benefits of cloud computing** in Azure and how it can save you time and money
- Explain **cloud concepts** such as high availability, scalability, elasticity, agility, and disaster recovery
- Describe **core Azure architecture components** such as subscriptions, management groups, resources and resource groups
- Summarize **geographic distribution concepts** such as Azure regions, region pairs, and availability zones

### 1. Introduction to Azure fundamentals

**benefits of cloud computing**

You will learn like:

☑️ What is **cloud computing**

☑️ What is **Azure**

☑️ How to get started with Azure's subscriptions and **accounts**.

1. [What is Azure](http://www.rupeshtiwari.com/what-is-microsoft-azure/)
2. [Azure Services](http://www.rupeshtiwari.com/tour-of-azure-services/)
3. [Azure accounts](http://www.rupeshtiwari.com/getting-started-with-azure-accounts/)

### 2. Discuss Azure fundamental concepts

Upon completion of this module, you'll be able to:

- Identify the **benefits** and considerations of using **cloud services**.
- Describe the differences between **categories** of **cloud services**.
- Describe the differences between **types of cloud computing**.
