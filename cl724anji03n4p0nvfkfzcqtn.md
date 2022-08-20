## What is Azure Load Balancer?

An **Azure Load Balancer** is a server that routes the traffic to multiple servers / VMs, providing high availability for the application.

In other words, we can say it is a hardware or software device that will intercept all the traffic coming from the internet and decide which request goes to which server, i.e., VM1, VM2, VM3, etc...


![Load_Balancer_1.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660999252760/sxAT3s2R8.png align="left")





# How does the Load Balancer works?

Suppose that N users are accessing the same site simultaneously, and that site shows in the pop-up that the site is inaccessible or the session timed out.
It is due to the excess traffic reaching out there, and there is no load balancer. All the traffic is routed towards limited or dedicated servers only.
![Session_time_out.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660999332289/yRHUL6BDm.png align="left")
Here comes the concept of Load Balancer in this scenario. If we use the load balancer and the traffic first hits the LB (Load Balancer), it will eventually help to route/divide that traffic and send it to multiple servers. Again, LB decides which server receives which request depending on how busy the Servers / VMs are and can increase or decrease the VMs if we use the VM scale set in our infrastructure.

### Increasing servers
If a heavy traffic landing on the site results in the server being engaged up to more than 80% limit, then it's time for reinforcement. The load balancer can hit auto-scaling service and add or scale out another server to decrease the load by routing the traffic accordingly.

### Decreasing servers
Suppose we have seven servers / VMs, and the traffic is less, or the utilization of the servers is less or equal to 15% most of the time. That means we don't require a few servers right now. The Load balancer will automatically scale in (Turn off / eliminate) infrequent servers accordingly, which also helps reduce resource costs.


![Using Load Balancer.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660999451045/32UApioSx.png align="left")



# Types of Load Balancers in Azure

### Public Load Balancer
It helps to create outbound connections for virtual machines inside our virtual network, i.e., if you are connected to your virtual network, it will convert your private IP to public IP and allow you web access. It is used to balance the Internet traffic coming to your virtual machine.

### Private or Internal Load Balancer
It is used where only private IPs are required to access the frontend. This load balancer balances a load of traffic inside the Virtual Network.


![load-balancer.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1660999813053/d90-0IIyU.png align="left")

# Benefits

- Internal and external traffic coming to Azure virtual machines is quickly load balanced by it.
- It also increases availability by distributing resources within and across zones.
- It also helps in configuring the outbound connectivity for Azure virtual machines.
- It uses health probes to monitor the load-balanced resources.
- Engages port forwarding to access virtual machines in a virtual network by public IP address and port.
- It also provides Load balanced services across multiple ports and multiple IP addresses. 
- It also moves internal and external load balancer resources across Azure regions.
- Provides load balance TCP and UDP flow on all ports simultaneously using HA ports.





