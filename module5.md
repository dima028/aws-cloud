# Module 5: Storage & Databases

## Instance Stores & Amazon Elastic Block Store (Amazon EBS)
**Block-Level Storage**: a place to store files. Updates only changing bytes, making it efficient. Temporary storage. Behave like physical hard drives. An instance store provides temporary block-level storage for an Amazon EC2 instance. An instance store is disk storage that is physically attached to the host computer for an EC2 instance, and therefore has the same lifespan as the instance. When the instance is terminated, you lose any data in the instance store.

**Amazon Elastic Block Store, EBS**: provides block-level storage volumes that you can use with Amazon EC2 instances. create virtual hard drives, called EBS volumes, that attach to EC2 instances. These are separate drives from the local instance store volumes. Allow you to incrementally back-up your data via "snapshots".

## Amazon Simple Storage Service (Amazon S3):
**Object Storage**:
