# Create VPC

Name: **MyVPC** 

IPv4 CIDR Block: **10.0.0.0/16** 

Optional: Enable DNS hostnames

`aws ec2 create-vpc --instance-tenancy 'default' --cidr-block '10.0.0.0/16' --tag-specifications '{"resourceType":"vpc","tags":[{"key":"Name","value":"MyVPC"}]}'` 

# Create Subnets

## Public Subnet

Select: **MyVPC**

Name: **Public-1A**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.0.1/24**

Enable auto-assign public IPv4 addresses

## Private Subnet

Name: **Private-1A**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.0.2/24**

# Create private route table

Name: **Private-RT**

VPC: **MyVPC**

Subnet associations: **Private-1A**




