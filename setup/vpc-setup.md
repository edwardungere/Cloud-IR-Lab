# Create VPC

Name: **MyVPC** 

IPv4 CIDR Block: **10.0.0.0/16** 

Optional: Enable DNS hostnames

# Create private subnets

Select: **MyVPC**

Name: **Private-1A**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.1.0/24**

Name: **Private-1B**

Availability Zone: **us-east-1b**

IPv4 CIDR Block: **10.0.2.0/24**

# Create private route table

Name: **Private-RT**

VPC: **MyVPC**

Subnet associations: **Private-1A**, **Private-1B**




