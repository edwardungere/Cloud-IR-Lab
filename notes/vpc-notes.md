AWS creates default vpc's in every region and a default public subnet in every AZ

- virtual private cloud [vpc]
- logically isolated cloud within AWS
- stays within one region, does not span across regions, does span every availability zone [AZ] within a region
- multiple can stay within a region
- each vpc has a block of addresses

by default, all subnets within a vpc can talk to each other,
they cannot if: 
- They are in different VPCs (without VPC Peering / Transit Gateway)
- NACLs explicitly deny traffic
- Security Groups block inbound traffic

each vpc has one virtual router, managed by AWS. route tables are configured and attached to vpcs

other definitions
- peering: direct connection between two vpc's
- vpc endpoint: private ip connection to public AWS resources
- NAT instance vs NAT gateway: allows private instances internet access managed by you vs AWS
- virtual private gateway [vgw] & customer gateway: allow for VPN connection from private network over the internet
- direct connect: private connection to on-premise without internet connection
- network ACL: subnet-level firewall
- security group: instance-level firewall
