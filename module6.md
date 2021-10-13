# Module 6: Security
## Shared Responsibility Model
**Shared Responsibility Model:** Treat the environment as a collection of parts that build upon each other. In this model, the responsibility of the security of certain components belongs 100% to one entity (i.e. Amazon) while the responsibility to security of other components belongs 100% to another (i.e. the customer).
* AWS: Security of the Cloud, responsible for creating a secure architecture at all layers including: host operating system, virtualization layer, and the physical security of the data centers from which services operate. 
* The Customer: Security in the Cloud, responsible for implementing security best practises in everything they create and put into the AWS cloud.
** This can leveraging AWS's own services such as configuring security groups and managing user accounts. 

## User Permissions and Access
**AWS Identity and Access Management (IAM)**: enables you to manage access to AWS services and resources securely. Gives you the flexibility to configure access based on your company’s specific operational and security needs, by using a combination of IAM features such as:
  * IAM users, groups, and roles, 
  * IAM policies, 
  * Multi-factor authentication,

**Account Management Best Practises:**
* **AWS Account Root User**: has complete access to all the AWS services and resources in the account.
  *  **Do not** use the root user for everyday tasks.
  *  **Do** use the root user to create your first IAM user and assign it permissions to create other users.
  *  **Do** continue to create other IAM users, and access those identities for performing regular tasks throughout AWS. Only use root user when you need to perform a limited number of tasks that are only available to the root user (i.e. changing root user email address, changing AWS support plan).

* **IAM Users**: an identity that you create in AWS, with a name and credentials. It represents the person or application that interacts with AWS services and resources. By default, new IAM users in AWS have no permissions associated with them.
  *  **Do** create individual IAM users for each person who needs to access AWS, even if they are to have the same credentials.

* **IAM Policies**: a document that allows or denies permissions to AWS services and resources. Enables you to customize users’ levels of access to resources (i.e. allow users to access certain S3 buckets within your AWS account).
  *  **Do** follow the security principle of _least privilege_ when granting permissions, to prevent users or roles from having more permissions than needed to perform their tasks. 

## AWS Organizations:
**AWS Organizations**: AWS Service to install order and to enforce who is allowed to perform certain functions in what account.
* Consolidated billing -> bulk discounts!
* hierarchical groupings of your accounts to meet security, compliance, or budgetary needs.
* isolate workload.
* **Organizational Units, OUs**: Organizations can be grouped into OUs based of access needs.

**Organizations**: a central location to manage multiple AWS accounts

**Service Control Policies, SCPs**: AWS service to specify the maximum permissions for individual member accounts or OUs in the organization.
