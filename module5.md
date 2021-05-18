# Module 5: Storage & Databases

## Instance Stores & Amazon Elastic Block Store (Amazon EBS)
**Block-Level Storage**: a place to store files. Updates only changing bytes, making it efficient. Temporary storage. Behave like physical hard drives. An instance store provides temporary block-level storage for an Amazon EC2 instance. An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store.

**Amazon Elastic Block Store, EBS**: provides block-level storage volumes that you can use with Amazon EC2 instances. create virtual hard drives, called EBS volumes, that attach to EC2 instances. These are separate drives from the local instance store volumes. Allow you to incrementally back-up your data via "snapshots".

## Amazon Simple Storage Service (Amazon S3):
**Amazon Simple Storage Service, or S3**: data store that allows you to store and retrieve an unlimited amount of data at any scale. Data is stored as objects,  in buckets. You can also version objects to protect them from accidental deletion. You can even create multiple buckets and store them across different classes or tiers of data. You can then create permissions to limit who can see or even access objects. And you can even stage data between different tiers. These tiers offer mechanisms for different storage use cases such as data that needs to be accessed frequently, versus audit data that needs to be retained for several years.

*  **S3 Standard**: comes with 11 nines of durability. That means an object stored in S3 Standard has a 99.999999999 percentage probability that it will remain intact after a period of one year. Data is stored such that AWS can sustain concurrent loss of data in two separate storage facilities bc data is stored in at least three facilities so multiple copies reside across locations. Can also use S3 for static website hosting (_static website_: collection of HTML files).

* **S3 Infrequent Access, S3-IA**: used for data that is accessed less frequently but requires rapid access when needed. Perfect to store backups, disaster recovery files, or any object that requires a long-term storage.

* **S3 One Zone-Infrequent Access (S3 One Zone-IA)**:  

* **S3 Intelligent-Tiering**: 

* **S3 Glacier**: 

* **S3 Glacier Deep Archive**: 

