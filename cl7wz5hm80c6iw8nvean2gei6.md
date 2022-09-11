## Azure Network Security Group

# **What is Network Security Group (NSG)?**

A Network Security group filters out network traffic between Azure resources in Azure virtual Networks.

It is a type of firewall. It is stacked with a bulk of features that secures the Azure resource to a great extent.

A Network security group contains set security rules that provide the permissions to inbound / outbound traffic to hit Azure resources after passing through them.

### **Security Rules:**

Here are some rules for NSG with their properties.


- Name : A unique name within the network security group.
- Priority : A number between 100 and 4096. Rules are processed in priority order, with lower numbers processed before higher numbers because lower numbers have higher priority. Once traffic matches a rule, processing stops. As a result, any rules with lower priorities (higher numbers) that have the same attributes as rules with higher priorities aren't processed.
- Source or Destination : If you specify an address for an Azure resource, select the private IP address assigned to the resource. Network security groups are processed after Azure translates a public IP address to a private IP address for inbound traffic and before Azure translates a private IP address to a public IP address for outbound traffic.
- Protocol : TCP, UDP, ICMP, ESP, AH, or Any. The ESP and AH protocols are not currently available via the Azure Portal but can be used via ARM templates.
- Port Range : You can specify an individual or range of ports. For example, you could specify 80 or 10000-10005. Specifying ranges enables you to create fewer security rules. You can't specify multiple ports or port ranges in the same security rule in network security groups created through the classic deployment model.

The important thing here comes is that the security rules are analyzed and applied with these five necessary pieces of information.
(Source, Source port, Destination, Destination port, Protocol.)
We cannot create two security rules with the same priority.


### Default security rules:

When we create the NSG, we have the following default rules created by Azure.


![Screenshot 2022-09-11 at 11.52.22.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662877400624/tJtaM-VQG.png align="left")


# **How do NSG works?**

We can use NSG at Subnet or NIC, or both.


**Subnet (Recommended)** - These NSGs can restrict the traffic flow to all the servers/VMs is residing within that Subnet.

**Network Interface Card (NIC)** - If the NSGs are allocated to the NIC, all the traffic that flows through that NIC is under control by that NIC.



![NSG.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662878636238/jqFFhwenB.png align="left")

### Inbound 
The traffic coming from the internet is firstly hit to NSG connected with Subnet, then that traffic, after filtering out, goes to the NSG linked with the Network Interface (if any), then it reaches the resource or VM. 


### Outbound
The traffic coming from the resource is firstly hit to NSG connected with Network Interface (NIC), then that traffic, after filtering out, goes to the NSG linked with the Subnet (if any), then it reaches the resource or VM.














