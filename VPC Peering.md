# Private Connectivity Options || Inter VPC communication - VPC peering
- Enables private communication between 2 VPC
- Can connect single VPC to multiple VPCs

**Limitaions :-** 
- CIDR should be non-overlapping
- Only one peering between given 2 VPCs
- Peering connection is not transitive. 

![VPC peering](https://user-images.githubusercontent.com/33689324/188149186-e91a6abf-f627-40f5-ab4e-a065bf854397.jpg)


# VPC End Point 
- Private connection between VPC & AWS services 
- Currently supports AWS S3 & Dynamo DB connection in same AWS region 
- Should add corresponding route in subnet route table 

**Benefits :-**
- NAT mot required
- Very low cost 
- Scales automatically

![VPC-End-point](https://user-images.githubusercontent.com/33689324/188149863-057868f3-30ea-4f4d-8099-b9247014eb6f.jpg)
