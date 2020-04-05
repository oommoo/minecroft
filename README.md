Minecroft

A simplified way to create and manage minecraft servers and databases for the bancrofts.

# Overview

Some time ago, my employment with an ISP allowed placement of a physical server in our networking lab as a means of generating some real world traffic.  We had setup several other services, such as open source package repositories, usenet feeds, and chat servers.  I added a small minecraft server for the enjoyment of my family and friends.  After switching jobs, and the corresponding loss of lab access, some other facility for hosting a minecraft server would be required.


# AWS

The simplest infrastructure deployment was use an AWS EC2 instance. We were able to host ten to twenty folks in a t3.meduim (2 vCPU, 4 GiB memory, 24 CPU credits / hour). For convenience, we treat the EIP as an independent infrastructure entity.

VPC : mc-east-farm, vpc-0113b01e137cc7023

Subnet: subnet-0429e15831382aa10
	cidr, 10.64.128.0/24
	route table, rtb-08bd81fd5b5b3a940

EIP :
	network interface, eni-07f1f21c6880d3ee9
	subnet, subnet-0429e15831382aa10
	availability zone, us-east-2b
	association, eipassoc-00a97bb89d2e89a4f

Instance: i-05bb7f163e43161e3
	  ip: 10.64.128.172
	  eip:  eipassoc-00a97bb89d2e89a4f

# gandi 

Some of the information needs to be deployed onto the gandi infrastructure.  The primary mechanism for this will be git.
