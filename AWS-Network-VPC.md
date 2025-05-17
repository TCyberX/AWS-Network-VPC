<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** Albert  
**Email:** tapcyberx@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC ( Virtual Private Cloud ) is a virtual network that you create and manage within AWS. It useful beacuse  it gives you a logically isolated section of the cloud where you can launch and control your resources securely.


### How I used Amazon VPC in this project

In today’s project, I used Amazon VPC to better understand how the networking layer of AWS works.

It helped me learn key concepts like subnets, route tables, internet gateways, and IP address management giving me a clearer picture of how cloud resources communicate securely within an environment.

This was a great hands-on way to explore the foundation of AWS infrastructure.



### One thing I didn't expect in this project was...

The “secret mission” in this project was absolutely incredible! I didn’t expect how powerful and efficient it would be to run PowerShell through the AWS CLI to quickly set up resources.



### This project took me...

This project took me around 5 hours, give or take. I spent extra time really focusing on understanding how networking works in the AWS environment things like VPCs, subnets, routing, and internet gateways.

---

## Virtual Private Clouds (VPCs)

A VPC (Virtual Private Cloud) is a virtual network that you create and manage within AWS. It gives you a logically isolated section of the cloud where you can launch and control your resources securely.

Think of it as your own custom data center in AWS you define key settings like IP address ranges, subnets, routing tables, and security groups. 

A default VPC is automatically created when you open a new AWS account. It’s provided by AWS to make it easier to get started quickly, so you can launch resources like EC2 instances or RDS databases without needing to build a VPC from scratch.

It comes with pre-configured subnets, route tables, internet gateways, and security settings, giving you a working network setup right out of the box.



To set up my VPC, I had to define an IPv4 CIDR block, which means a range of IP addresses that my VPC can allocate to the resources deployed into my VPC.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-networks-vpc_2facf927)

---

## Subnets

Subnets are like neighboorhood in your city. Some subnets might be public areas that all resources can access (public subnets) while others are private areas with limited access (private subnets).

There are already subnets existing in my account, one for every  Availability Zone in the Region that I've set up my VPC in. Since my region is  N.Virginia (US-east-1), which has six Availability Zones,  I have six default subnets already.

Once I created my subnet, I enabled auto-assign public IPv4 addresses.
This setting makes sure that any EC2 instance launched in the subnet automatically gets a public IP, so that it can communicate with the internet.

This is important when you’re working with public-facing resources, like web servers or apps, that need to send or receive traffic over the internet.

A subnet is only considered public if it’s connected to the internet specifically, if it has a route to an internet gateway through its route table.

Right now, my subnet is not a public subnet because it doesn’t have that route set up. Without internet access, it's treated as a private subnet, which is typically used for resources that don’t need direct exposure to the internet.



![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-networks-vpc_157c4219)

---

## Internet gateways

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

Attaching an internet gateway to your VPC allows resources within the VPC to send and receive traffic from the internet.

This means that EC2 instances with public IP addresses can now be accessed by users online making your applications or services publicly available. 

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

VPC resources could also be created with CloudShell, which is shell in your AWS Management Console.
CLI is a software that lets you create, delete and update AWS resources with commands instead of clicking through your console.

To set up a VPC or a subnet, you can use the command aws ec2 create-subnet --vpc-id [VPC-ID] --cidr-block [ADD-CIDR-BLOCK-HERE]. Make sure to avoid errors by including the range of your CIDR block from /25 to /32.


Compared to using the AWS Console, an advantage of using commands is that it’s faster and more efficient for repeating tasks or automating resource creation. You can quickly set up VPC components like subnets, route tables, and gateways using just a few CLI commands.

An advantage of using the Console is that it provides a visual interface, which makes it easier to understand how different components are connected especially helpful when learning or troubleshooting.

Overall, I preferred using CloudShell commands for their speed and automation potential, but the Console was great for double-checking configurations and seeing the full architecture at a glance.

![Image](http://learn.nextwork.org/delighted_indigo_timid_orc/uploads/aws-networks-vpc_9b2465411)

---

---
