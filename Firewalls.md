# Firewalls
1. Security Groups
2. NACL (Network access control list)


> **Security Groups**
  - Virtual Firewall 1st level of defence 
  - An AWS security group acts as virtual firewall for you EC2 instances to control incoming & outgoing traffic.
  - Both inbound and outbound rules control the flow of traffic to and traffic from your instance, respectvely
  - work at EC2, RDS, RedShift
  - Default - allows all outbound traffic no inbound traffic
  - can attach upto 5 security groups to single EC2 instance with 100 rule (in/outbound) per sq
  - Can only specify ALLOW rules
  - Deny rules cannot be specified  


> **NACL (Network access control list)**
  - Stateless firewall  2nd level of network security
  - An a optional layer of security that acts as a firewall for controlling traffic in and out of subnets
  - Work at subnet level applied to all instance
  - Rule are evaluated in the order of rule number
  - Default NACL allows all inbound & outbound traffic


