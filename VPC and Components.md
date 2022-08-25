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
       
    -------------------------------------------

      ---
      ec2  10.10.0.0
      ---

      ---
      ec2  10.10.0.1
      ---
      "     " " "  3
      "     " " "  255
                                                    = 256 * 256 = 65536
      ---
      ec2  10.10.1.0
      ---

      ---
      ec2  10.10.2.1
      ---
      "     " " "  3
      "     " " 255  255
     
    -------------------------------------
    
    1. 10.10.0.0/16  = 32-16 = 16
                     = 2^16 = 65536 IPs
        
    2. 10.10.0.0/28  = 32-28 = 4
                     = 2^4 = 16 IPs
    
    3. 10.10.0.0/24  = 32-24 = 8
                     = 2^8 = 256IPs
                     
                     
                     
 2. **Subnets**
    - A subnets is logical subdivision of IP Network 
    - The practice of dividing a network into two or more network is called subnets
    - There are two subnets 
       - Public Subnets 
       - Private Subnets
       
       
     1. Public Subnet  
     
        - Has route for inaternet
        - instance with public IP can communucate to internet 
        - EX:- NAT , web servers, Load balancer
     
     2. Private subnet
     
        - No route to internet
        - instance receives private IPs
        - typically uses NAT for intstance to have internet access
        - EX:- Database, App server
     
 3. **Route Table**
    - Contains rules to route the traffic in/out of subnets/VPC
    - Main route table at VPC level
    - Custom route table at subnet level
    - Each route table contains default immutable local route for VPC
    - If no custom route table is defined then new subnets are associated with main route tbale
    - We can modify main route table 
    
  **Example**
  
   | Destination   | Target        |
   | ------------- | ------------- |
   | 10.0.0.0/16   | Local         |
   |  0.0.0.0/0    | igw-id        |
        
        
 4. **IGW (Internet Gateway)**
   - IGW which allowes you to communicate VPC to internet
   
 5. **VGW (Virtual Private Gateway)**  
   - VGW it allows you to coonect VPC to on prenises datacenter
   - CGW (Customer Gateway)
