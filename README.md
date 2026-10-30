AWS VPC Peering Implementation – Private Network Connectivity

1. Introduction

This project focuses on connecting two isolated Amazon Virtual Private Clouds (VPCs) using AWS VPC Peering. The objective is to enable communication between private EC2 instances without exposing application servers directly to the public internet.

A Bastion Host is deployed in the public subnet to provide a controlled administrative access point.

2. Project Objectives

- Create two independent VPC networks.
- Configure public and private subnets.
- Establish a VPC Peering connection.
- Configure routing for communication between VPCs.
- Apply security groups to control network traffic.
- Deploy EC2 instances in the required subnets.
- Understand secure access to private cloud resources.

3. AWS Infrastructure Design

The environment consists of the following components:

| Component | Configuration |
|---|---|
| AWS Region | Asia Pacific (Mumbai) |
| VPC 1 | 10.10.0.0/16 |
| VPC 2 | 10.20.0.0/16 |
| Public subnet | 10.10.1.0/24 |
| Private subnet 1 | 10.10.2.0/24 |
| Private subnet 2 | 10.20.1.0/24 |
| Compute service | Amazon EC2 |
| Network connection | VPC Peering |

4. Services and Technologies

- Amazon Virtual Private Cloud (VPC)
- Amazon EC2
- VPC Peering
- Internet Gateway
- Route Tables
- Security Groups
- Amazon Linux 2023

5. Network Components

VPC 1
The first VPC contains a public subnet and a private subnet. The public subnet hosts the Bastion Host, while the private subnet contains the first application instance.

VPC 2
The second VPC contains a private subnet with another application instance. It does not require a direct internet gateway.

astion Host
The Bastion Host acts as an entry point for administrative SSH connections to private instances.

VPC Peering
A peering connection links the two VPC networks and allows private IP communication when the appropriate routes and security rules are configured.

6. Routing and Security

Custom route tables are configured to direct traffic between the two VPC CIDR ranges through the peering connection.

Security groups control incoming connections:
- SSH access is restricted to approved sources.
- ICMP traffic is configured for private connectivity testing.
- Application instances do not receive public IPv4 addresses.

7. Implementation Procedure

1. Create two VPCs with non-overlapping CIDR ranges.
2. Create the required subnets.
3. Attach an Internet Gateway to the first VPC.
4. Configure custom route tables and subnet associations.
5. Launch the Bastion and application EC2 instances.
6. Create and accept the VPC Peering connection.
7. Add routes to both private route tables and the Bastion subnet route table.
8. Configure the required security group rules.
9. Perform connectivity verification where completed.

8. Project Results

The AWS networking resources were created and configured according to the planned architecture.

**Verification status:** Record the actual results of SSH and ICMP connectivity tests here. Do not report successful communication unless it has been tested.

9. Skills Acquired

- AWS network architecture and configuration.
- VPC and subnet management.
- CIDR addressing and IP planning.
- Route table configuration.
- VPC Peering concepts.
- Security group configuration.
- EC# AWS-VPC-connectivity
This project focuses on connecting two isolated Amazon Virtual Private Clouds (VPCs) using AWS VPC Peering. The objective is to enable communication between private EC2 instances without exposing application servers directly to the public internet.
