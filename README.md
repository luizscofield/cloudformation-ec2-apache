# CloudFormation Template for Amazon Linux EC2 with Apache Httpd

This repository contains a CloudFormation Template that launches a EC2 instance, with Apache Httpd installed, in us-east-1 Region (N. Virginia).

## Parameters

* SSHKey: name of a existing KeyPair to enable SSH access to the instance.
* AvaiabilityZone: availability Zone where the instance will be launched. The default is us-east-1a.
    - Allows only values that match the actual us-east-1 availability zones.
* EC2Name: Name Tag for the EC2 instance. Default is EC2Instance.
* EC2AMI: AMI used to launch the instance. By default it is the latest Amazon Linux 2.
* EBSVolumeSize: Size of the EBS volume used by the instance. Default is 8GB.
* SGCidrBlockSSH: CIDR IP Block allowed to access the instance using SSH. Default is any IP.
* SGCidrBlockHTTP: CIDR IP Block allowed to make HTTP requests to the instance. Default is any IP.

## Resources created

* EC2 Instance
* EBS volume
* Security Group for SSH access
* Security Group for HTTP access

## Details

The template contains a user-data script for the EC2 that installs the HTTP server and creates a index.html file.