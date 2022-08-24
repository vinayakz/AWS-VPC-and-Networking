# What is VPC ?
  - Virtual Private cloud enables you to launch resources into a virtual network that you have defined. VPC customers can **run code, store data, host websites, and do anything else they could do in an ordinary private cloud,** but the private cloud is hosted remotely by a public cloud provider.
  
## AWS Services Inside VPC and Outside VPC

![AWS-VPC](https://user-images.githubusercontent.com/33689324/186360767-ae6bbe3f-905b-480b-b124-18b06a5b25e2.jpg)

- **Service Inside VPC we can manage.**
- **Service Outside VPC AWS will manage.**

# VPC Components
  - CIDR
  - VPC
  - Subnets 
  - Route Tables

![vpc-Components](https://user-images.githubusercontent.com/33689324/186365169-d5400a02-925d-4e30-afd6-a072c3f37feb.jpg)

1. **CIDR (Classless Inter-Domain Routing)**
  - Also Known as supernetting 
  - Is a method of assigning internet protocol(IPs) 
  - Maximum VPC size prefix/16 (65536 IPs)
  - Minimum VPC size prefix/28 (16IPs)

**Example:-**
    
        8  8  8 8
        10.10.0.0/16 -> prefix
       
       - First two (10.10) is Network fix wecannot change this address
       - last two (0.0) Host we can change 
       - 16 is prefix
       - last two address  (0.0) 8 * 8
       - 8 * 8 = 16
       - 2^16 = 65536
       
  |                      |
  |                      |
  |                      |
  |                      |       
