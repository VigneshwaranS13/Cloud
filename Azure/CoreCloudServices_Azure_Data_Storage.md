#### Types of data

1. Structured data.
2. Semi-Structured data.
3. Unstructured data

#### Azure SQL Database

Azure SQL Database is a relational database as a service (DaaS) based on the latest stable version of the Microsoft SQL Server database engine. SQL Database is a high-performance, reliable, fully managed, and secure database. You can use it to build data-driven applications and websites in the programming language of your choice without needing to manage infrastructure.
You can migrate your existing SQL Server databases with minimal downtime using the Azure Database Migration Service. The service uses the Microsoft Data Migration Assistant to generate assessment reports that provide recommendations to help guide you through required changes prior to performing a migration. Once you assess and perform any remediation required, you're ready to begin the migration process. The Azure Database Migration Service performs all of the required steps. You just change the connection string in your apps.

#### Azure Cosmos DB

Azure Cosmos DB is a globally distributed database service. It supports schema-less data that lets you build highly responsive and Always On applications to support constantly changing data. You can use this feature to store data that is updated and maintained by users around the world

#### Azure Blob storage

Azure Blob Storage is unstructured, meaning that there are no restrictions on the kinds of data it can hold. Blobs are highly scalable and apps work with blobs in much the same way as they would work with files on a disk, such as reading and writing data

#### Azure Data Lake Storage

Azure Data Lake Storage combines the scalability and cost benefits of object storage with the reliability and performance of the Big Data file system capabilities. The following illustration shows how Azure Data Lake stores all your business data and makes it available for analysis.

![Azure Data Lake](https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure/media/3-data_lake_store_concept.png)

#### Azure Files

Azure Files offers fully managed file shares in the cloud that are accessible via the industry standard Server Message Block (SMB) protocol. Azure file shares can be mounted concurrently by cloud or on-premises deployments of Windows, Linux, and macOS.
![Azure Files](https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure/media/3-azure_files.png)

#### Azure Queue

Azure Queue storage is a service for storing large numbers of messages that can be accessed from anywhere in the world.

Azure Queue Storage can be used to help build flexible applications and separate functions for better durability across large workloads. When application components are decoupled, they can scale independently. Queue storage provides asynchronous message queueing for communication between application components, whether they are running in the cloud, on the desktop, on-premises, or on mobile devices.

Typically, there are one or more sender components and one or more receiver components. Sender components add messages to the queue, while receiver components retrieve messages from the front of the queue for processing. The following illustration shows multiple sender applications adding messages to the Azure Queue and one receiver application retrieving the messages.

![Azure Queue](https://docs.microsoft.com/en-us/learn/modules/intro-to-data-in-azure/media/3-azure_queue.png)

You can use queue storage to:

Create a backlog of work and to pass messages between different Azure web servers.
Distribute load among different web servers/infrastructure and to manage bursts of traffic.
Build resilience against component failure when multiple users access your data at the same time.

#### Disk Storage

Disks come in many different sizes and performance levels, from solid-state drives (SSDs) to traditional spinning hard disk drives (HDDs), with varying performance abilities.

#### Storage tiers

Azure offers three storage tiers for blob object storage:

1. Hot storage tier: optimized for storing data that is accessed frequently.

2. Cool storage tier: optimized for data that are infrequently accessed and stored for at least 30 days.

3. Archive storage tier: for data that are rarely accessed and stored for at least 180 days with flexible latency requirements.

#### Encryption and replication

#### Encryption for storage services

1. Azure Storage Service Encryption (SSE) for data at rest helps you secure your data to meet the organization's security and regulatory compliance. It encrypts the data before storing it and decrypts the data before returning it. The encryption and decryption are transparent to the user.

2. Client-side encryption is where the data is already encrypted by the client libraries. Azure stores the data in the encrypted state at rest, which is then decrypted during retrieval.

#### Replication for storage availability

A replication type is set up when you create a storage account. The replication feature ensures that your data is durable and always available. Azure provides regional and geographic replications to protect your data against natural disasters and other local disasters like fire or flooding.