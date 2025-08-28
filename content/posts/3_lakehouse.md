---
title: "Lakehouse: The Next Step in Data Warehousing"
date: 2023-08-09T21:56:35-05:00
draft: false 
tags:
    - "data engineering"
---

As we keep making strides in today's data-driven world, businesses need new ways to efficiently store large amounts of raw data while making good use of it. In response, Databricks presents a new data warehouse architecture called Lakehouse. This idea is intended to overtake the popular two-tier architecture of data lakes with data warehouses and set a new standard for data engineering for customers and businesses.


As a brief background, the journey of data repositories for companies starts with on-premise solutions. This obviously became more expensive over time so solutions such as data lakes and data warehouses have come along as efficient solutions. They have both come to work together in a two-tier architecture where raw unstructured data is either stored in data lakes or in on-premise servers and then ETLed into a data warehouse solution for customer use. This is because data lakes cannot match the SQL performance of data warehouses but are best for storing raw unstructured data, the life-blood of data scientists. However, the ETL pipeline between the two tiers becomes a point of weakness as it will require constant maintenance and could lead to stale data in the data warehouse if improperly maintained.


The Lakehouse architecture aims to combine the best of both worlds with directly-accessible storage at a low cost. The main hindrance is the fact that structuring your data in order to support direct queries loses the advantages of speed and the potential of finding unexpected analytical insights. 


Lakehouse's solution is to add a metadata layer on top of the object store as a layer of abstraction. This layer supports ACID (Atomicity, Consistency, Isolation, and Durability) transactions for consistent versioning of data. However, it is insufficient for reliable SQL performance. In order to mitigate this, the architecture utilizes various optimizations such as caching files, data layout optimizations, data structure indexing, and even using faster storage devices such as SSDs. This metadata can be as simple as a consistent transaction log that tracks all the files in a data lake. For example, the Delta Lake project utilizes the [Delta Lake transaction protocol](https://delta.io/blog/2023-07-07-delta-lake-transaction-log-protocol/), which specifies how to store files and record transactions. Metadata layers also open up opportunities for data quality and access governance features.


The most important feature of the Lakehouse is its compatibility with analytics tools used for business intelligence and machine learning. This includes support for Apache Spark’s DataFrame API, which allows accessing raw data in the object store, and the Tensorflow API. Additionally, the Lakehouse implementation should also ideally remain compatable with popular data file formats such as Apache Parquet.


Given the strengths of Lakehouse, it seems to be a good next step for data engineering teams. The next steps will involve supporting new data lake storage formats and exploring better optimizations for faster SQL querying.

To read more about Lakehouse, check out the paper by Databricks [here](https://www.cidrdb.org/cidr2021/papers/cidr2021_paper17.pdf) and their blogs.

