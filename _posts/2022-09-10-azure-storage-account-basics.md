---
title: Azure Storage Account Basics
date: 2022-09-10 00:00 +0000
description:
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
  - azure
---

## Azure Storage Account

Azure Storage Accounts are divided in 2 Major accounts: Standard and Premium.

![](https://i.imgur.com/dNZFT12.png){: .full}

Notice while creating storage account you have to choose standard or premium as per performance requirement. Premium are highly performance account with SSD disk and super fast access but costly option though.

![](https://i.imgur.com/D6lDVaH.png){: .full}

## Azure Standard Account

Azure Standard Account in old days used to be in 3 varieties (this is legacy now a days)

- General Purpose V1
- General Purpose V2 and
- Blob account

![](https://i.imgur.com/jzlsAH1.png){: .full}

Now a days in Standard Storage Account we have only one type **General Purpose V2**.

![](https://i.imgur.com/QJnAGdy.png){: .full}

### General Purpose v2 (GPv2) Storage Account

This is the newest storage account. This supports all of the storage services: **Blob, Azure Files, Queue, Page Blob and Disk, and Table**. It also supports blob tiering. You can select a default hot or cool tier.

## Blob Storage Account

![](https://i.imgur.com/SSkSAc4.png){: .full}

## Types of Blobs

There are importantly 2 types of blobs that you can imagine

- Block Blobs and
- Page Blobs

![](https://i.imgur.com/zG2dD8m.png){: .full}

{: .notice--success}
🏆 **Pro Tip** \
\
**Append Blobs** are basically block blobs optimized for append operations are heavily used for storing Log data.

### Block Blobs

- Ideal for storing Text and Binary Data.

  ![](https://i.imgur.com/gIebE45.png){: .full}

- A single block blob can contain up to **50,000** blocks of up to **100 MB** each, for a total size of **4.75 TB**

![](https://i.imgur.com/zg0lrp4.png){: .full}

- Append blobs are optimized for append operations (e.g. **logging**)

![](https://i.imgur.com/pCax9mp.png){: .full}

### Page Blobs

• Efficient for read/write operations
• Used by Azure VMs
• Up to **8 TB** in size

There are 3 major types of Azure Storage Accounts. Per domain or host you need to create one account. Some time based on features also you create accounts. Example: If you want to create sales.storage.com, pricing.storage.com then for each host name you need new storage account. Next if you want to create Azure premium storage account then it is separate account all together. Within Azure storage account you can have many tiers. However, if you want premium tier then you must create separate account all together called [Premium Storage account](https://azure.microsoft.com/en-us/blog/introducing-premium-storage-high-performance-storage-for-azure-virtual-machine-workloads/).
