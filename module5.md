# Module 5: Storage & Databases

## Instance Stores & Amazon Elastic Block Store (Amazon EBS)
**Block-Level Storage**: a place to store files. Updates only changing bytes, making it efficient. Temporary storage. Behave like physical hard drives. An instance store provides temporary block-level storage for an Amazon EC2 instance. An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store.

**Amazon Elastic Block Store, EBS**: provides block-level storage volumes that you can use with Amazon EC2 instances. Local storage that is not ephemeral. create virtual hard drives, called EBS volumes, that attach to EC2 instances. These are separate drives from the local instance store volumes. Allow you to incrementally back-up your data via "snapshots".

## Amazon Simple Storage Service (Amazon S3):
**Amazon Simple Storage Service, or S3**: data store that allows you to store and retrieve an unlimited amount of data at any scale. Data is stored as objects,  in buckets. You can also version objects to protect them from accidental deletion. You can even create multiple buckets and store them across different classes or tiers of data. You can then create permissions to limit who can see or even access objects. And you can even stage data between different tiers. These tiers offer mechanisms for different storage use cases such as data that needs to be accessed frequently, versus audit data that needs to be retained for several years.

*  **S3 Standard**: comes with 11 nines of durability. That means an object stored in S3 Standard has a 99.999999999 percentage probability that it will remain intact after a period of one year. Data is stored such that AWS can sustain concurrent loss of data in two separate storage facilities bc data is stored in at least three facilities so multiple copies reside across locations. Can also use S3 for static website hosting (_static website_: collection of HTML files).

* **S3 Infrequent Access, S3-IA**: used for data that is accessed less frequently but requires rapid access when needed. Perfect to store backups, disaster recovery files, or any object that requires a long-term storage.

* **S3 One Zone-Infrequent Access (S3 One Zone-IA)**: Stores data in a single Availability Zone rather than minimum of 3. Has a lower storage price than S3 Standard-IA. Ideal storage class for low budget storage and your data is easily reproducible.

* **S3 Intelligent-Tiering**: Ideal for data with unknown or changing access patterns. Requires small monthly monitoring and automation fee per object. Amazon S3 monitors objects’ access patterns. If you haven’t accessed an object for 30 consecutive days, Amazon S3 automatically moves it to the infrequent access tier, S3 Standard-IA. If you access an object in the infrequent access tier, Amazon S3 automatically moves it to the frequent access tier, S3 Standard.

* **S3 Glacier**: Low-cost storage ideal for data archiving. Able to retrieve objects within a few minutes to few hours. For example, you might use this storage class to store archived customer records or older photos and video files. Optimized for archival data.

* **S3 Glacier Deep Archive**: Lowest-cost object storage class ideal for archiving, but slower at retrieving objects than S3 Glacier. Able to retrieve objects within 12 hours.  Optimized for archival data.


### Comparing Amazon EBS and Amazon S3
**Amazon Elastic Block Storage, (EBS):** sizes up to 16 tebibytes, unique ability to survive termination of Amazon EC2 instances, solid state. Ideal for applications such as:
* editing files (makes use of delta-updates unlike S3 treating each update as its own object)
* complex read, write, change functions
* attach to EC2 instances that reside in the same availability zone
* Stores data in a single availability zone
* Availability zone level resource
* do not need to automatically scale

**Amazon Simple Storage Service, (S3)**: unlimited storage, individual objects up to 5 kilobytes. specialize in write once/read many, 99.999 999 999% durable, web enabled. Ideal for uses such as:
* photo analysis (S3 optimzed for read-many applications, regional distribution means backup strategies are secure, different images have different URLs which can be accessed by S3 bc web enabled)
* when using complete objects or making occasional changes

## Amazon Elastic File System (Amazon EFS)
**Amazon Elastic File System, EFS**: Managed, scalable file system. File storage use cases. EFS grows and shrinks automatically, and enables to have multiple instances that can access the data. 
* Multiple read/write instances at the same time
* regional resource: any instance in the region can read/write to it
* linux file system
* automatic scaling
* regional service, stores data in and across multiple availability zones
* duplicate storage enables access to data concurrently from all Availability Zones in the region where a file system is located
* on-premise servers can access Amazon EFS using AWS Direct Connect

## Amazon Relational Database Service (Amazon RDS)
### Relational Database Service, RDS
Store data such that it related to other data (i.e. customer table and address table) and query with SQL.

### Amazon RDS
Database management tool. Can migrate data from Databases to AWS via _Lift and Shift_.

Customer ownership/control over:
* Data
* Schema
* Network

Additional features such as:
* Automated patching
* Backups
* Redundancy
* Failover
* Disaster recovery

Available on 6 database engines:
* MySQL
* PostgreSQL
* Oracle
* Microsoft SQL Server
* _Amazon Aurora_
* MariaDB

### Amazon Aurora
Amazon RDS Database Engine. Highlights include:
* Cost effective: 1/10th the price of commercial databases.
 * reduces cost by reducing unnecesary input/outpit (I/O) operations while ensuring DB reliability 
* 5x faster than standard MySQL databases
* 3x faster than standard PostgreSQL databases
* Comes in two forms:
 * MySQL
 * PostgreSQL
* Data replicated across facilities so you have 6 copies at any given time
* Can deploy up to 15 read replicas to offload reals and scale performace
* Continuous S3 backups ready to restore
* _Point in time_ recovery to recover data at a particular point in time.
* Ideal for:
 * High availability workloads 
 
## Amazon DynamoDB
**Amazon DynamoDB**: NoSQL non-relational serverless database with *DynamoDB tables* organized into *items* with *attributes*. DynamoDB manages the underlying storage and scalability for you. Has a millisecond response time. NoSQL makes it dodge performance and scaling issues that rigid schemas that SQL would entail. Need simpler queries for one table rather than multi-table complex SQL queries. Optimized for querying single tables very quickly and high scalability.
* Serverless: DynamoDB is serverless, which means that you do not have to provision, patch, or manage servers. You also do not have to install, maintain, or operate software.
* Automatic scaling: As the size of your database shrinks or grows, DynamoDB automatically scales to adjust for changes in capacity while maintaining consistent performance. This makes it a suitable choice for use cases that require high performance while scaling.

## Amazon Redshift
**Amazon Redshift**: This is data warehousing as a service. Data warehouses designed to store big data for historical analytics (as opposed to operational analysis). Optimized for looking at already set data. Massively scalable as _Redshift nodes_ can scale up to multiple petabytes. Optimized for *Business Intelligence, BI* use cases (i.e. big data solutions). 

**Amazon Redshift Spectrum**: can be used in cooperation with *Amazon Redshift* in order to run a single SQL query against exabytes of unstructured data running in data lakes.

## AWS Database Migration Service
**Amazon Database Migration Service, DMS,**: helps customers migrate existing databases onto AWS in a secure and easy fashion between a source and a target database. The source database remains fully operational during the migration, minimizing downtime to applications that rely on that database. The source and target databases don't have to be of the same type. Use cases include:

* **Homogenous Migrations**: Migration between databases of the same type. Can be from:
 *  MySQL: MySQL to Amazon RDS for MySQL,
 *  SQP Server: Microsoft SQL Server to Amazon RDS,
 *  Oracle: Oracle to Amazon RDS, 

* **Heterogenous Migrations**: Migrations between databases of different types. A two-step process:
 * Convert schema structures, data types, and database code using the _AWS Schema Conversion Tool_ to match that of the target database. 
 * Use DMS to migrate data from the source database to the target database. 

* **Development and test database migrations:** migration to develop and test against production data, without affection production users. 
 * use DMS to migrate copy of production database to dev or test environemnts, either one-off or continuously.

* **Database Consolidation:** consolidating several databases into one central database. 

* **Continuous database replication:** using DMS to perform continuous data replication, for disaster recovery or because of geographic separation. 

## Additional database services
**Amazon DocumentDB**: document database service that supports _MongoDB_ workloads, a document database program. Full content management system, ideal for  content management, catalogs, user profiles.

**Amazon Neptune**: graph database service. Can be used to build and run applications that work with highly connected datasets, such as recommendation engines, fraud detection, knowledge graphs, or other social network applications. 

**Amazon Quantum Ledger Database (Amazon QLDB)**: Immutable ledger database service. Can be used to review a complete history of all the changes that have been made to your application data. Ideal for supply chains, or tracking financial/banking records. Being immutable makes it audit friendly as any entry can never be removed from the audits, unlike other blockchain solutions. 

**Amazon Managed Blockchain**: service that you can use to create and manage blockchain networks with open-source frameworks. Blockchain is a distributed ledger system that lets multiple parties run transactions and share data without a central authority. 

**Amazon ElastiCache**: service that adds caching layers on top of your databases to help improve the read times of common requests from milliseconds to microseconds. It supports two types of data stores: _Redis_ and _Memcached_.

**Amazon DynamoDB Accelerator, DAX**: in-memory native caching layer for DynamoDB. Helps improve response times from single-digit milliseconds to microseconds.
