# AWS VPC Peering Project

## Project Overview

This project demonstrates how to connect two Amazon Virtual Private Clouds (VPCs) using VPC Peering. The infrastructure was configured manually through the AWS Management Console.

## Objectives

- Create two VPCs.
- Configure public and private subnets.
- Attach an Internet Gateway to VPC-1.
- Configure route tables.
- Establish a VPC Peering connection.
- Launch EC2 instances.
- Configure security groups.
- Test connectivity between network resources.

## AWS Services Used

- Amazon VPC
- Amazon EC2
- VPC Peering
- Internet Gateway
- Route Tables
- Subnets
- Security Groups

## Network Configuration

### VPC-1
- CIDR: `28.0.0.0/16`
- Public subnet: `28.0.1.0/24`
- Private subnet: `28.0.2.0/24`
- Internet Gateway attached
- One public EC2 instance
- One private EC2 instance

### VPC-2
- CIDR: `28.200.0.0/16`
- Private EC2 instance
- Connected to VPC-1 through VPC Peering

## Implementation

1. Created two VPCs.
2. Created the required subnets.
3. Attached an Internet Gateway to VPC-1.
4. Configured route tables for public and private subnets.
5. Created and accepted the VPC Peering connection.
6. Added routes for the remote VPC CIDRs.
7. Launched EC2 instances in the required subnets.
8. Configured security groups for network traffic.

## Testing

The following connectivity tests are intended:

- Public EC2 internet connectivity.
- Communication between public and private EC2 instances.
- Communication between private EC2 instances across the VPC Peering connection.

Actual test results will be documented after verification.

## Security Notes

- Restrict SSH access to trusted IP addresses.
- Never upload private keys or AWS credentials.
- Allow only required network traffic.
- Delete unused resources to avoid unnecessary AWS charges.

## Learning Outcomes

This project provides practical experience with AWS networking, EC2, subnet configuration, route tables, security groups, and VPC Peering.



## Architecture Diagram

![AWS VPC Peering Architecture](architechure-diagram-aws-vpc-peering-project.jpeg)




