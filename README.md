# AWS-SAA-C03
Created to read about AWS Services
# Private IPv4 addresses**
A private IPv4 address is an IP address that's not reachable over the Internet. You can use private IPv4 addresses for communication between instances in the same VPC. We allocate private IPv4 addresses to instances using DHCP. 
Each instance has a default network interface (eth0) that is assigned the **primary private** IPv4 address. You can also specify additional private IPv4 addresses, known as **secondary private** IPv4 addresses.
Secondary private IP addresses can be reassigned from one instance to another.

A private IPv4 address, regardless of whether it is a primary or secondary address, remains associated with the network interface when the instance is stopped and started, or hibernated and started,
 and is released when the instance is terminated.

