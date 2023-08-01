# Lecture Notes: Cloud Network Security

## Cloud Network Security

- **Why** (5 min)
  - Why would we use traditional network infrastructure in the cloud?
  - Why use a VPC when you have elastic IPs?

- **What** (10 min)
  - What network security components should we learn how to use on the cloud?
    - Security Groups
    - VPC
      - Private subnet
      - Public subnet
    - Internet gateway
    - NAT gateway
  - An **Amazon Virtual Private Cloud (Amazon VPC)** enables you to launch AWS resources into a virtual network that you've defined
    - Resembles a traditional LAN except with access to scalability of AWS
  - A **subnet** is a range of IP addresses in your VPC, much like a traditional LAN subnet.
    - Must fit within the scope of your VPC
      - Example: 192.168.0.0/16 as as VPC would support a 192.168.1.0/24 subnet.
    - A **public subnet** hosts public-facing services like a web site or file server.
      - An **internet gateway** is a gateway that you attach to your VPC to enable communication between resources in your VPC and the internet.
    - A **private subnet** does not allow access to resources from outside the VPC, and is instead meant for internal resources.
      - You can use a **network address translation (NAT) gateway** to enable instances in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating a connection with those instances.
      - NAT gateways will charge you.
      - A **route table** is a set of rules, called routes, that are used to determine where network traffic is directed.
  - **CIDR (Classless Inter-Domain Routing) Block** is an internet protocol address allocation and route aggregation methodology. AWS recommends referencing the CIDR article on Wikipedia.
