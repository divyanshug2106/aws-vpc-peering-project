# AWS VPC Peering — Setup Guide

## 1. Create VPCs

Create two VPCs using the AWS Management Console.

- VPC-1: `28.0.0.0/16`
- VPC-2: `28.200.0.0/16`

## 2. Create Subnets

In VPC-1, create:

- Public subnet: `28.0.1.0/24`
- Private subnet: `28.0.2.0/24`

In VPC-2, create a private subnet using a valid CIDR range contained within VPC-2.

## 3. Configure Internet Gateway

Create an Internet Gateway, attach it to VPC-1, and add a default route to the public route table.

## 4. Configure Route Tables

Associate the public route table with the public subnet and configure the default route to the Internet Gateway.

Associate the private route tables with their respective private subnets.

## 5. Create VPC Peering

Create a VPC Peering connection between VPC-1 and VPC-2. Accept the peering request and verify that its status is Active.

## 6. Add Peering Routes

In VPC-1's private route table, add a route to the VPC-2 CIDR using the peering connection.

In VPC-2's private route table, add a route to the VPC-1 CIDR using the same peering connection.

## 7. Launch EC2 Instances

Launch one public EC2 instance and one private EC2 instance in VPC-1. Launch another private EC2 instance in VPC-2.

Assign security groups that allow only the required traffic.

## 8. Validate Connectivity

Test internet access from the public EC2 instance.

Test communication between the private EC2 instances using their private IP addresses.

Record the actual test results and any troubleshooting performed.

## 9. Security Notes

- Restrict SSH access to trusted sources.
- Never upload private keys or AWS credentials.
- Use appropriate security group rules.
- Remove unused resources after the lab.

## Important CIDR Note

The `28.0.0.0/16` and `28.200.0.0/16` ranges are from the original lab configuration and are not RFC1918 private IPv4 ranges. For a new lab, use non-overlapping private ranges such as `10.0.0.0/16` and `10.1.0.0/16`.

Ensure that each subnet CIDR is a valid subset of its VPC CIDR.
