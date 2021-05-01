# Module 4: Networking

## Module 4 Introduction
**Amazon Virtual Private Cloud, Amazon VPC**: Enables you to provision a logically isolated section of AWS Cloud and launch AWS resources in virtual network. Can be public or private (with or withut access to the internet). Essentially your own private network in AWS. Allows you to define private IP range for AWS resources, and place EC2 instances and ELBs inside VPC. Within a VPC, resources can be organized into **subnets**.

## Connectivity to AWS
**Subnets**: groups of  IP addresses in your VPC that allow you to group resources together. Control whether a resource is publically or privately available. Used to control access to gateways. Can also control traffic permissions.

**Internet Gatewate, IGW**: "doorway" open to the public to enable public facing resources to be accessed. Attaching an IGW to a VPC makes the resource publicly accessible.

**Virtual Private Gateway**: private doorway, allows for a VPN connection between a VPC and private network. Attaching a virtual private gateway to a VPC makes the resource privately accessible.

**Virtual Private Network, VPN**: a private and encrypted connection to a resource, either private or public. Use an internet connection therefore still susceptible to the same bandwidth limitations of any other internet connection. This can be bypassed with AWS Direct Connect.

**AWS Direct Connect**: establishes a completely private and dedicated _physical_ fiber connection from data center to AWS. Must coordinate with a Direct Connect partner in order to establish the physical line and meet regulatory, compliance, and bandwidth needs. 

## Subnets and Network Access Control Lists
**Network hardening**: the elimination of potential vulnerabilities by adhering to the _"Golden Rules"_ of security.

**Packets**: messages from the internet. Every packet that crosses the subnet boundaries gets checked against a network access control list (network ACL), to ensure the packet has permissions to enter/leave the subnet, based on who sent it and how it's trying to communicate.

**Network Access Control List, NACL**: _Passport control officers_, to monitor the entry and exit of all incoming and outgoing messages/packets to or from the subnet. Subnet level of network security. _Stateless_ meaning that it has no memory of who has come in or out so it checks all packets non-discriminatorily, hence checking incoming _and_ outoging traffic. Default is _deny all_, however for AWS Accounts, the default Network ACL is configured to _allow all_.

**Security Groups**: Instance level of network security. Prevent all incoming traffic from entering the EC2 instance. Can be modified to accept specific traffic types (i.e. HTTPS, OS, Administration Requests, etc.). _Building doorman_ in the sense that it only checks incoming traffic, not outgoing. This is because it is _stateful_ in that it has a memory as to who has come in, therefore if you have incoming permissions you have outgoing permissions so there is no need to check outgoing traffic. Default is _deny all incoming_.

## Global Networking
**Domain Name System, DNS**: "a translation service". Translates website names into Internet Protocol (IP) addresses. Involves Customer DNS Resolver communicating with company DNS server for IP address. _Eg. Route 53._ 

_More about Route 53: DNS Web Service. Used to route end users. Can also direct traffic to different endpoints using several different routing policies, such as latency-based routing, geolocation DNS, geoproximity, and weighted round robin. Can also be used to register, purchase, and manage domain names._

**Amazon Cloudfront**: a content delivery service. Works with Route 53 to deliver content to the user. Route 53 responds to customer request with IP address while Cloudfront responds by sending customer request to nearest edge location and connecting to the Application Load Balancer to process requests by availbale EC2 instances.
