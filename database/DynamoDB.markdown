
# DynamoDB Definition
- DynamoDB is a noSQL database.
- Fully managed database and supports both document and key-value data models.

# DynamoDB Basics

- Stored on SSD storage
- Spread accross 
- Geographically distinct data
- Uses B-tree primitived.

# Data Consistency

1- Eventual consistency reads (default)
- Consistency is usually reached within a second.

2- Strongly consistent reads
- Consistency read returns that reflects all writes that received a successful response prior to the read.
- The disadvantages are:
    - A strongly consistent read might not be available if there is a network delay or outage. In this case, DynamoDB may return a server error (HTTP 500).
    - Strongly consistent reads may have higher latency than eventually consistent reads.
    - Strongly consistent reads are not supported on global secondary indexes.
    - Strongly consistent reads use more throughput capacity than eventually consistent reads.
- Read operations (such as GetItem, Query, and Scan) provide a ConsistentRead parameter. If you set this parameter to true, DynamoDB uses strongly consistent reads during the operation.


# DynamoDB Pricing

[Price](https://aws.amazon.com/dynamodb/pricing/on-demand/)


# DynamoDB Streams
- DynamoDB Streams captures a time-ordered sequence of item-level modifications in any DynamoDB table and stores this information in a log for up to 24 hours. Applications can access this log and view the data items as they appeared before and after they were modified, in near-real time.
- Inserts, Update and Deletes.

# DynamoDB Accelerator (DAX)
Provides improvement to performance with response times in microseconds for millions of requests per second for read-heavy workloads.

DAX is a DynamoDB-compatible caching service that enables you to benefit from fast in-memory performance for demanding applications

![DAX](/images/DAX.png)

# DynamoDB  provisioned throughput capacity
When you create a new provisioned table in Amazon DynamoDB, you must specify its provisioned throughput capacity. This is the amount of read and write activity that the table can support. DynamoDB uses this information to reserve sufficient system resources to meet your throughput requirements.

# Transactions
- Two underlying reads and writes ( prepare/commit)
- Operate up to 25 items or 4MBytes of data

# On-Demand Capacity
- Pay-per-request pricing
- Balance cost and performance
- No char for read/write - only storage and backups
- Pay more per requests
- Can use for new product launches.
- Backup and Restore:
    - full backup at any time.
    - Zero impact on table performance
    - Consisent within seconds and retained until deleted.
- Point-in-Time-Recovery (PITR)
    - Protects against accidental writes or deletes
    - Retsore to any point in the last 35 days
    - Incremental backups
    - not enabled by default
    - Latest restorable time stamp: 5 minutes

# Global Tables
- Based on dynamoDB streams
- Globaly distributed applications
- multi-region redundancy for DR (disaster recover) and HA (high availability).
- Replication latency under one second.

# Security
- encrypted at rest using KMS
- IAM policies and roles
- Site-to-site VPN
- Direct connect (DX)
- VPC endpoints

# References
1) [DynamoDBStreams](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Streams.html)
2) [DynamoDB Accelerator - DAX](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/DAX.concepts.html)
