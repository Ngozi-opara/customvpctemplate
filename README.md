# AWS CloudFormation Template: Custom VPC and EC2 Instance

This repository contains a CloudFormation template written in YAML that automates the creation of a custom Virtual Private Cloud (VPC) with a single public subnet and launches an EC2 instance within it.

## Features

- **Custom VPC**: The template creates a VPC with a customizable CIDR block.
- **Public Subnet**: Includes a public subnet with internet access enabled.
- **EC2 Instance**: Launches an Amazon EC2 instance with a user-defined instance type and key pair.
- **Security Group**: Configures a security group to allow HTTP, HTTPS, and SSH access.
- **Route Table**: Includes a route table that directs traffic to an Internet Gateway.

## How to Use

1. **Prerequisites**:
   - An active AWS account.
   - A key pair created in the region where you plan to deploy this stack. Refer to the [AWS Documentation on Key Pairs](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html) for guidance.
   - Familiarity with basic AWS services like EC2, VPC, and CloudFormation.

2. **Steps to Deploy**:
   - Open the AWS Management Console.
   - Navigate to the **CloudFormation** service.
   - Click **Create Stack** and upload the YAML template.
   - Specify the required parameters:
     - **InstanceType**: Choose the type of EC2 instance (default is `t2.micro`).
     - **VpcCIDR**: Define the CIDR block for the VPC (default is `10.0.0.0/16`).
     - **SubnetCIDR**: Define the CIDR block for the public subnet (default is `10.0.1.0/24`).
   - Review the settings and deploy.

3. **Outputs**:
   - The stack will provide the following outputs:
     - **VPC ID**: The ID of the created VPC.
     - **Subnet ID**: The ID of the public subnet.
     - **EC2 Instance ID**: The ID of the launched EC2 instance.

## Troubleshooting

If you encounter errors during stack creation, check the **CloudFormation Events tab** for details. Common issues include:
- **Invalid Key Pair**: Ensure the key pair name matches one in your AWS account.
- **Incorrect AMI ID**: Verify that the AMI ID is valid for your selected region. Learn how to find an AMI ID in the [AWS Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/finding-an-ami.html).

## Helpful Resources

- [Understanding VPCs and Subnets](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)
- [Introduction to CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)
- [Networking and Security Best Practices](https://aws.amazon.com/architecture/security/)
- [AWS CLI Commands for EC2](https://docs.aws.amazon.com/cli/latest/reference/ec2/index.html)
