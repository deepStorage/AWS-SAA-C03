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
