# Create VPC

Name: **MyVPC** 

IPv4 CIDR Block: **10.0.0.0/16** 

Optional: Enable DNS hostnames

# Create Subnets

### Public Subnet

Select: **MyVPC**

Name: **Private-1A**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.1.0/24**

### Private Subnets

Name: **Private-1B**

Availability Zone: **us-east-1b**

IPv4 CIDR Block: **10.0.2.0/24**

# Create private route table

Name: **Private-RT**

VPC: **MyVPC**

Subnet associations: **Private-1B**, **Private-2B**




