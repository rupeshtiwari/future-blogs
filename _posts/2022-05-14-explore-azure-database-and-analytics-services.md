---
title: Explore Azure Database and Analytics Services
date: 2022-05-14 00:00 +0000
description:
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: false
image: https://i.imgur.com/OTHb1vM.png
header:
  image: https://i.imgur.com/XMFI6bl.png
  teaser: https://i.imgur.com/OTHb1vM.png
  og_image: https://i.imgur.com/OTHb1vM.png
tags:
  - webdev
  - azure
  - tutorial
  - az-900
---

> This is the 1st article on "**Azure Fundamentals Part 2: Describe core Azure services**".

![](https://i.imgur.com/PkGHO9t.png){: .full}

Do you want to migrate to Azure and are you using variety of databases technologies? Then you must read this article to learn all the different types data workloads in Azure. Understand the different database options that are available in Azure.

Azure database services are globally distributed, and Azure supports many of the industry standard databases and APIs.

## Learning objectives

After completing this module, you'll be able to describe the benefits and usage of:

- Azure Cosmos DB
- Azure SQL Database
- Azure SQL Managed Instance
- Azure Database for MySQL
- Azure Database for PostgreSQL
- Azure Synapse Analytics
- Azure HDInsight
- Azure Databricks
- Azure Data Lake Analytics

## Prerequisites

- You should be familiar with basic computing concepts and terminology.
- You should be familiar with basic database concepts and terminology.

![](https://i.imgur.com/6VSKg4J.png){: .full}

## Azure Cosmos DB

If you want your data to be accessed via many API's and you have developers with different skill sets. Then I would recommend using Azure Cosmos DB.

![](https://i.imgur.com/UC5N0r6.png){: .full}

Azure Cosmos DB is a globally distributed, multi-model database service. You can take advantage of fast, single-digit-millisecond data access by using any one of several popular APIs. Azure Cosmos DB provides comprehensive service level agreements for throughput, latency, availability, and consistency guarantees.

Azure Cosmos DB supports schema-less data, which lets you build highly responsive and "Always On" applications to support constantly changing data. You can use this feature to store data that's updated and maintained by users around the world.

![](https://i.imgur.com/LzWLt9M.png){: .full}

Azure Cosmos DB is flexible. At the lowest level, Azure Cosmos DB stores data in atom-record-sequence (ARS) format. The data is then abstracted and projected as an API, which you specify when you're creating your database. Your choices include SQL, MongoDB, Cassandra, Tables, and Gremlin. This level of flexibility means that as you migrate your company's databases to Azure Cosmos DB, your developers can stick with the API that they're the most comfortable with.

## Azure SQL Database

Azure SQL Database is a relational database based on the latest stable version of the Microsoft SQL Server database engine.

![](https://i.imgur.com/7se8XDr.png){: .full}

Azure SQL Database is a platform as a service (PaaS) database engine. It handles most of the database management functions, such as upgrading, patching, backups, and monitoring, without user involvement. SQL Database provides 99.99 percent availability. SQL Database is a fully managed service that has built-in high availability, backups, and other common maintenance operations.

You can use both relational data and non-relational structures, such as graphs, JSON, spatial, and XML.

{: .notice--success}
🏆 **ProTip** \
\
The newest capabilities of SQL Server are released first to **SQL Database**, and then to SQL Server itself.

### Migration

You can migrate your existing SQL Server databases with minimal downtime by using the Azure Database Migration Service. The Microsoft Data Migration Assistant can generate assessment reports that provide recommendations to help guide you through required changes prior to performing a migration.

### Exercise - Create a SQL database

In your company suppose you want Azure SQL Database for part of your migration.

#### Task 1: Create the database

Learn here [how to create Azure SQL DB in Azure](https://docs.microsoft.com/en-us/learn/modules/azure-database-fundamentals/exercise-create-sql-database)

![](https://imgur.com/rjno2oM.gif){: .full}

#### Task 2: Test the database

In this task, you configure the server and run a SQL query.

![](https://imgur.com/VpgneZv.gif){: .full}