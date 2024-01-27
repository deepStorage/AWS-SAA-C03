# AWS-SAA-C03
Created to read about AWS Services
# Private IPv4 addresses
A private IPv4 address is an IP address that's not reachable over the Internet. You can use private IPv4 addresses for **communication between instances in the same VPC**. We allocate private IPv4 addresses to instances using DHCP. 
Each instance has a default network interface (eth0) that is assigned the **primary private** IPv4 address. You can also specify additional private IPv4 addresses, known as **secondary private** IPv4 addresses.
Secondary private IP addresses can be reassigned from one instance to another.

A private IPv4 address, regardless of whether it is a primary or secondary address, remains associated with the network interface when the instance is stopped and started, or hibernated and started,
 and is released when the instance is terminated.

# Public IPv4 addresses
A public IP address is an IPv4 address that's reachable from the Internet. When you launch an instance in a **default VPC**, we assign it a public IP address by default.

If you **require a persistent public IP address** that can be associated to and from instances as you require, use an **Elastic IP address** instead.

If you use **dynamic DNS** to map an existing DNS name to a new instance's public IP address, it might take up to 24 hours for the IP address to propagate through the Internet.As a result, **new instances might not receive traffic while terminated instances continue to receive requests**. -->  To solve this problem, use an **Elastic IP** address. 

When New IP address assigned by AWS:
* We release your instance's public IP address when it is stopped, hibernated, or terminated. Your stopped or hibernated instance receives a new public IP address when it is started.
* We release your instance's public IP address when you associate an Elastic IP address with it. When you disassociate the Elastic IP address from your instance, it receives a new public IP address.

When New IP address not assigned by AWS:
* If the public IP address of your instance in a VPC has been released, it will not receive a new one if there is more than one network interface attached to your instance.
* If your instance's public IP address is released while it has a secondary private IP address that is associated with an Elastic IP address, the instance does not receive a new public IP address.

# Elastic IP addresses (IPv4)

An Elastic IP address is a public IPv4 address that you can allocate to your account. You can associate it to and disassociate it from instances as you require

# Elastic network interfaces / Network interface
An elastic network interface is a logical networking component in a VPC that represents a virtual network card. It can include the following attributes:

* A primary private IPv4 address from the IPv4 address range of your VPC
* A primary IPv6 address from the IPv6 address range of your VPC
* One or more secondary private IPv4 addresses from the IPv4 address range of your VPC
* One Elastic IP address (IPv4) per private IPv4 address
* One public IPv4 address
* One or more IPv6 addresses
* One or more security groups
* A MAC address
* A source/destination check flag
* A description

**Source/destination checking**
You can enable or disable source/destination checks, which ensure that the instance is either the source or the destination of any traffic that it receives. Source/destination checks are **enabled** by default. 
You must **disable** source/destination checks if the instance runs services such as network address translation, routing, or firewalls.

# AWS Networking Services

Network foundations: Amazon VPC(opens in a new tab), AWS Transit Gateway(opens in a new tab), AWS PrivateLink(opens in a new tab)

Hybrid connectivity: AWS Direct Connect(opens in a new tab), AWS Site-to-Site VPN(opens in a new tab), AWS Client VPN(opens in a new tab), AWS Cloud WAN(opens in a new tab)

Edge networking: Amazon CloudFront(opens in a new tab), Amazon Route 53(opens in a new tab), AWS Global Accelerator(opens in a new tab)

Application networking: AWS App Mesh(opens in a new tab), Amazon API Gateway(opens in a new tab), AWS Cloud Map(opens in a new tab)

Networking security: AWS Shield(opens in a new tab), AWS WAF(opens in a new tab), AWS Network Firewall(opens in a new tab), AWS Firewall Manager
