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

 * Network foundations: [Amazon VPC](https://docs.aws.amazon.com/vpc/index.html), [AWS Transit Gateway](https://docs.aws.amazon.com/whitepapers/latest/aws-vpc-connectivity-options/aws-transit-gateway.html), [AWS PrivateLink](https://aws.amazon.com/privatelink/?privatelink-blogs.sort-by=item.additionalFields.createdDate&privatelink-blogs.sort-order=desc)
 * Hybrid connectivity: [AWS Direct Connect](https://aws.amazon.com/directconnect/?trk=0292198f-fe46-45b4-b46e-88ee1df3f1f4%E2%89%BBchannel=ps%E2%89%BBcampaign=acquisition%E2%89%BBmedium=ACQ-P%7CPS-GO%7CNon-Brand%7CDesktop%7CSU%7CNetworking%20&%20Content%20Delivery%7CSolution%7CUS%7CEN%7CDSA&ef_id=Cj0KCQiA64GRBhCZARIsAHOLriLpPB_paHeQsfKNjFTfMlJH___3OIXPWpp5QJQfuYlClWqNyKQHeUAaAmhlEALw_wcB:G:s&s_kwcid=AL!4422!3!579408327287!!!g!!), [AWS Site-to-Site VPN](https://docs.aws.amazon.com/vpn/latest/s2svpn/VPC_VPN.html), [AWS Client VPN](https://docs.aws.amazon.com/vpn/latest/clientvpn-admin/what-is.html), [AWS Cloud WAN](https://aws.amazon.com/cloud-wan/)
 * Edge networking: [Amazon CloudFront](https://aws.amazon.com/cloudfront/), [Amazon Route 53](https://aws.amazon.com/route53/), [AWS Global Accelerator](https://aws.amazon.com/global-accelerator/?blogs-global-accelerator.sort-by=item.additionalFields.createdDate&blogs-global-accelerator.sort-order=desc&aws-global-accelerator-wn.sort-by=item.additionalFields.postDateTime&aws-global-accelerator-wn.sort-order=desc)
 * Application networking: [AWS App Mesh](https://aws.amazon.com/app-mesh/?aws-app-mesh-blogs.sort-by=item.additionalFields.createdDate&aws-app-mesh-blogs.sort-order=desc&whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc), [Amazon API Gateway](https://aws.amazon.com/api-gateway/), [AWS Cloud Map](https://aws.amazon.com/cloud-map/)
 * Networking security: [AWS Shield](https://aws.amazon.com/shield/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc), [AWS WAF](https://aws.amazon.com/waf/), [AWS Network Firewall](https://aws.amazon.com/network-firewall/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc), [AWS Firewall Manager](https://aws.amazon.com/firewall-manager/)

**AWS Well-Architected Framework** is built around six pillars:
* Operational excellence
* Security
* Reliability
* Performance efficiency
* Cost optimization
* Sustainability

AWS Shared Responsibility Model -> AWS is responsible for the security **of the cloud** and you are responsible for the security **in the cloud**

* Amazon Virtual Private Cloud - provides a private location to launch AWS resources in an isolated virtual network.
  Amazon VPC supports services to monitor your network traffic, like [Amazon VPC Flow Logs](https://docs.aws.amazon.com/vpc/latest/userguide/flow-logs.html), [Amazon CloudWatch](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/cloudwatch_architecture.html), [VPC Traffic Mirroring](https://docs.aws.amazon.com/vpc/latest/mirroring/what-is-traffic-mirroring.html)
* AWS Transit Gateway -  is a service to manage and simplify the connections and peering for your Amazon VPCs.
* AWS PrivateLink -  helps to establish secure and private connectivity between Amazon VPCs, AWS services within your Region or inside another Amazon VPC, and your on premises network. 
* AWS Direct Connect - need to connect your data center to AWS,  to establish a private and dedicated connection.
* AWS Cloud WAN - need to connect cloud routing and software-defined wide area networks (SD-WANs), you can use to provide a central dashboard for making the connections between your offices, data centers, and Amazon VPCs. You can also use  **AWS Transit Gateway**
* AWS Client VPN - If you need to connect remote team access to AWS
* AWS Site-to-Site VPN - If you need to connect remote offices to AWS
* Amazon CloudFront -  delivers data, videos, applications, and application programming interfaces (APIs)  with lower latency and higher transfer speeds.
* AWS Global Accelerator -  optimizes your user traffic, from the user to your application.
  **AWS Shield Standard** and **AWS WAF** works for Cloudfront, Route53 and Global Accelerator.
* Amazon API Gateway -  creates, maintains, and secures APIs at any scale.
* AWS App Mesh -  connects containers and microservices with application-level networking.
* AWS Cloud Map -  discovers access to the most recent resources and services.
* AWS Shield - adds a safeguard to your applications against DDoS attacks.
* AWS WAF -  protects your web application from common web exploits.

  **IAM** is a web service that helps you securely control access to AWS resources for your users.
  You can configure IAM to control who can access your AWS resources, and what they can do with those resources.

  IAM uses?
  * Shared access to an AWS account. Grant other user permissions to administer resources.
  * Granular permission
  * AWS MFA. One MFA device per IAM user
  * Secure access to AWS resources for application that run on EC2
  * Identity federation
 
  IAM can't use?
  * Amazon EC2 SSH keys
  * Windows RDP certificates
    
AWS **Security Token Service**(**STS**) provides users with temporary security credentialsto your AWS resources.

Identity Federation - 
   ![image](https://github.com/deepStorage/AWS-SAA-C03/assets/103733093/e81ae017-cbb4-45ee-af38-f6c0b1f3cf26)
AWS PartnerCast - Windows on AWS Series: Integration of AWS-based and Microsoft-based Identity Systems - Technical

Managed AD vs  AD on EC2 Comparison:
![image](https://github.com/deepStorage/AWS-SAA-C03/assets/103733093/f242abc2-92da-415d-bea8-3bfa193a36a2)

When to choose:
![image](https://github.com/deepStorage/AWS-SAA-C03/assets/103733093/16fe3722-c503-40b1-82e3-34a8e881eb91)

**AWS Control Tower**   
_My Dk point_ - It is tool to automate the setup of multiple AWS accounts under an organisation with automatic security, IAM rules, policies and automatic deployment process defined.

AWS Control Tower can help you in the following ways:
* You can automate setup with just a few steps. You use established blueprints to configure your AWS environment with components such as a **multi-account structure**, identity and federated access management, and account provisioning workflows.
* You can apply security and compliance policies using established **guardrails**. In addition, you can detect and remediate non-compliant accounts and resources as your team provisions them.
* You get a visual summary of your AWS environment through a dashboard, from which you can view your accounts, guardrails, and compliance status, all in one place.

![image](https://github.com/deepStorage/AWS-SAA-C03/assets/103733093/84e4e3e8-454f-471c-8a9e-ca973d9e301a)


**How much does AWS Control Tower cost?**
* There is no additional charge to use AWS Control Tower.
* you will pay for services such as AWS Service Catalog, CloudTrail, AWS Config, Amazon CloudWatch, Amazon Simple Notification Service (Amazon SNS), Amazon Simple Storage Service (Amazon S3), and Amazon Virtual Private Cloud (Amazon VPC), based on your usage of these services

**Account Baseline means**
To baseline an account is to set up its blueprints and guardrails. The baselining process also sets up the centralized logging and security audit roles on the account, as part of deploying the blueprints. AWS Control Tower baselines are contained in the roles that you apply to every enrolled account.

**Account Service Catalog means**
**IT administrators can use AWS Service Catalog to create, manage, and distribute portfolios of approved products to end users.** These users then have access to the products that they need in a personalized portal. Therefore, you can enforce compliance with organizational business standards, manage product lifecycles, and help users find and launch products. In AWS Control Tower, your central cloud administrators and your end users can provision accounts in your landing zone using Account Factory, which is a product in AWS Service Catalog.

**What does AWS Control Tower do automatically?**
1) Turns on CloudTrail and AWS Config and facilitates centralized login to an Amazon S3 bucket, which is located in a log archive account
2) Preconfigures Amazon SNS topics that other services can subscribe to
3) Provides federated access to accounts using IAM Identity Center
4) Turns on guardrails to protect the resources that AWS Control Tower deploys and detects non-compliance across multiple accounts
5) Supports lifecycle events so that you can configure any additional custom automations as part of new account creation

**What types of guardrails does AWS Control Tower provide?**
  
  AWS Control Tower provides two types of guardrails: 
**Preventive guardrails** prevent policy violations through enforcement and are implemented using AWS CloudFormation and SCPs.
**Detective guardrails** detect policy violations and alert in the dashboard. Detective controls are implemented by using AWS Config rules.

**Use Cases For AWS Control Tower**
![image](https://github.com/deepStorage/AWS-SAA-C03/assets/103733093/475fb8a4-2539-41d1-a932-1729c955332f)

**Other Important points about Control Tower**
* AWS Control Tower cannot create an account if you are signed in as root user. You must log in as an IAM user
* In Region deny setting section, When you choose Enabled, AWS Control Tower applies a Region deny preventive guardrail to all registered organization units, or OUs, for that Region.
* To prohibit access to AWS services based on your AWS Control Tower Region configuration, you can choose Enabled.

![image](https://github.com/deepStorage/AWS-SAA-C03/assets/103733093/05f2639e-6d07-434f-81db-240a411b0d8d)

Enable AWS Control Tower command using AWS CLI:
aws controltower enable-control --control-identifier CONTROL_ARN --target-identifier OU_ARN

Check status command:
aws controltower get-control-operation --operation-identifier OP_ID



   

