# Module 3: Global Infrastructure & Reliability

## Module 3 Introduction
**High Availability** & **Fault Tolerance** achieved via AWS *"Regions"* to accomplish AWS global infrastructure & maintain reliability.

## AWS Global Infrastructure
### AWS Regions
- AWS Regions built closest to hwere traffic demands. 
- Each region has multiple dta centers to support customer needs.
- Regions conected via High Speed Fiber network managed by AWS
- each customer can choose which region to operate out of
- regions are isolated from one anoher for security and compliance to prevent information sharing across regions

### How to pick Regions?
#### Factors that influence region selection:
1. **Compliance**: does data HAVE to live within a particular country/continent?
2. **Proximity**: proximity of company or customer base to the region
3. **Feature Availability**: availability of features in a given region. Features are rolled out to a small subset of regions, before being made available in all regions.
4. **Pricing**: local tax structure may influence region pricing. 

#### Disasterproofed Regions?
**Region**: Geographically isolated area where you can access services needed to run your enterprise. Contain multiple availability zones, that allow you to keep application logically unified but physically separate.

**Availability Zone, AZ**: A data center or group of data centers, with redundant power, networking, and connectivity. Often built tens of miles apart for high availability and disasterproofing while balancing low latency. EC2 instances are run in different availability zones with up to single digit latency. 

In the event of a disaster, only some capacity is reduced. Best practise is to run EC2 instances across at least 2 AZs in a region, for disasterproofing.

## Edge Locations
**Content Delivery Networks, CDNs**: A locally copied or cached copy of data, in local regions.

**CDN Amazon CloudFront:** A service to help deliver data, services, video, applications, APIs to customers around the world with low latency and high transfer speed, no help accelerate communication.

**Edge Locations**: Separate from regions. Run CDN Amazon CloudFront and a DNS known as Amazon Route 53 to get content closer to customers, no matter where they are in the world.

**AWS Outpost**: fully operational mini-region inside your own data center. Owned and operated by AWS but isolated within your own building.

## How to Provision AWS Resources
AWS Resources are accessible by API:

**Application Programming Interface, API**: an interface with pre-determined ways to interact with AWS services. 

There are a couple of ways to make API calls and utilize AWS services, with varying levels of visual ease of use, sophistication/flexibility, and management. The following three means to provision AWS resources outline tools in which the user must provision and manage the resources themselves:

1. **AWS Management Console**: Browser-based console to visually manage AWS resources. Sandbox environment for testing out environments. Not good for automation.
2. **AWS Command Line Interface, CLI**: allows you to make calls using terminal. Enables user schedulability/automation. For scripting interactions with AWS using the terminal.
3. **AWS Software Development Kits, SDKs**: allow you to interact with AWS resources through various programming languages. Allows you to avoid manual resource creation.

Management tools to help you provision and manage AWS resources are also available, outlined below:

1. **AWS Elastic Beanstalk**: service that helps you provision Amazon EC2-based environments. You provide code and desired configuration settings and Beanstalk builds out environment and deploys resources necessary to manage: capacity, load balancing, automatic scaling, and application health monitoring. Environment configurations can be saved and easily deployed again if needed. Enables yoou the visibility and control of all resources, without having to manually manage and provision all resources separately. Focus is business application over infrastructure. 
2. **AWS CloudFormation**: infrastructure-as-code tool. Allows user to define wide variety of AWS resources using JSON or YAML text-based documents called CloudFormation templates. CloudFormation manages all the calls to the backend AWS APIs for you. Totally automated process: it determines the right operations to perform when managing your stack and rolls back changes automatically if it detects errors.
