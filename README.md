# terraform-project
AWS infrastructure with terraform automation.
AWS Infrastructure Setup with Application Load Balancer

Overview

This repository contains Terraform scripts for deploying an AWS infrastructure that includes an Application Load Balancer (ALB) spanning three Availability Zones (AZs), along with automated EC2 instance provisioning and Apache web server configuration. The setup ensures each server displays its name when accessed, with automated DNS registration in a private Route 53 zone.

Architecture

Components

Virtual Private Cloud (VPC):

A dedicated VPC for the infrastructure.

Three public subnets (one per AZ) for the Load Balancer.

Three private subnets (one per AZ) for EC2 instances.

Security Groups:

ALB Security Group allowing HTTP (80) access from anywhere.

EC2 Security Group allowing HTTP (80) from the ALB and SSH (22) for management.

EC2 Instances:

Three EC2 instances (server1, server2, interview) spread across three AZs.

Automated installation of Apache web server using Terraform user data.

Custom homepage for each server displaying its name dynamically.

Application Load Balancer (ALB):

Spanning across three public subnets.

Target groups for each server.

Path-based routing for different server contexts:

/server1 → server1

/server2 → server2

/interview → interview

Route 53 Private DNS:

Private hosted zone: dvstech.com.

Automatic registration of EC2 instances with custom domain names:

server1.dvstech.com

server2.dvstech.com

interview.dvstech.com

Deployment Steps

Prerequisites

AWS Account with necessary IAM permissions

Terraform installed on local machine

AWS CLI configured with credentials
