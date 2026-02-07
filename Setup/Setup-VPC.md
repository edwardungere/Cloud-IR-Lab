# Create VPC

Name: **MyVPC** 

IPv4 CIDR Block: **10.0.0.0/16** 

Optional: Enable DNS hostnames

# Create Subnets

Name: **Public-1A**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.0.1/24**

Name: **Private-1A**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.0.2/24**

# Create private route table

Name: **Private-RT**

VPC: **MyVPC**

Subnet associations: **Private-1A**



