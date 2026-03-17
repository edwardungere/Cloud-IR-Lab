# VPC endpoint
- Establishes a private connection to specific AWS services through AWS PrivateLink
- Eliminates the need for public IP addresses and internet communication between these services and your VPC instances
- Creates a secure connection, nothing leaves the Amazon network
- VPC endpoints are virtual devices that enable communication between instances in a VPC and various services
- Does not compromise availability or restricts bandwidth

## Gateway endpoint

- Functions similarly to an internet gateway but is designed to route traffic within a VPC to a predefined prefix list.
- List contains IP ranges used by Amazon DynamoDB and S3
- Add a route in your subnet's route table that directs traffic to the Gateway endpoint, targeting the prefix list for S3 or Dynamo.
- Does not use AWS Private Link, no additional charges
## Interface endpoint
- A group of elastic network interfaces (ENI) created by the VPC in the subnet you specify
- Each ENI is assigned a private IP address and serves as the primary entry point for traffic directed to a supported service
- Managed by Amazon VPC, no direct control over them
- Incur costs per hour, along with additional charges for data processing
