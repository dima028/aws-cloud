# Module 4: Networking

## Module 4 Introduction
**Amazon Virtual Private Cloud, Amazon VPC**: Enables you to provision a logically isolated section of AWS Cloud and launch AWS resources in virtual network. Can be public or private (with or withut access to the internet). Essentially your own private network in AWS. Allows you to define private IP range for AWS resources, and place EC2 instances and ELBs inside VPC. Within a VPC, resources can be organized into **subnets**.

## Connectivity to AWS
**Subnets**: groups of  IP addresses in your VPC that allow you to group resources together. Control whether a resource is publically or privately available. Used to control access to gateways. Can also control traffic permissions.

**Internet Gatewate, IGW**: "doorway" open to the public to enable public facing resources to be accessed. Attaching an IGW to a VPC makes the resource publicly accessible.

**Virtual Private Gateway**: private doorway, allows for a VPN connection between a private network. Attaching a virtual private gateway to a VPC makes the resource privately accessible.

**Virtual Private Network, VPN**: a private and encrypted connection to a resource, either private or public. Use an internet connection therefore still susceptible to the same bandwidth limitations of any other internet connection. This can be bypassed with AWS Direct Connect.

**AWS Direct Connect**: establishes a completely private and dedicated _physical_ fiber connection from data center to AWS. Must coordinate with a Direct Connect partner in order to establish the physical line and meet regulatory, compliance, and bandwidth needs. 

## Subnets and Network Access Control Lists
**Network hardening**:

**Packets**:

**Network ACL**:



## Global Networking
