VMS on Aws called EC2 servers
EC2 == Elastic Compute Version 2.

Elastic ==> can increase/decrease size 
Compute ==> machine 


### Why we even need to deploy , can't people all around world access code deployed locally on my machine? 
we don't have a public ip , there are limited no of ips 
No everyone has public ip 
For that we rent aws server and it has public ip and anyone can access it 

### Why can't you host localy for global access
1 No public ip on local machines 
- Most people have a private IP behind a router or firewall.
- The router translates your private IP to a shared public IP via NAT (Network Address Translation).
- The shared public IP is typically not designed to route incoming traffic to your machine.

2 Dynamic IP addresses 
- Even if you have a public IP, most ISPs assign dynamic IPs, which change periodically. This makes it difficult to provide a consistent address for people to access your application.

3 Performance and Availabilty 
- Your local machine likely doesn’t have the resources (CPU, RAM, bandwidth) to handle thousands or millions of requests.
What happens if you turn off your computer? The app becomes inaccessible.

### WHy deploy on AWS or other cloud providers? 
1 Public Ip address
- When you rent a server (like AWS EC2), you get a dedicated public IP address. This IP allows anyone on the internet to connect to your server.

2 Available 24/7

3 Renting a server on AWS is often cheaper than building and maintaining your own infrastructure for hosting.

4 AWS provides you with a virtual machine (EC2 instance) or a container (ECS task) with a public IP.

5 You can reserve a static IP (Elastic IP) to prevent the IP from changing when restarting your server.



# Creating a new EC2 Instance 

1 Select machines and whatever 
2 key-pair name and download temp file to access the was server 

3 Network  settings 

- Allow SSH from anywhere (0.0.0.0) default ticked 
SSH Secure Shell , is protocol use to communicate my machine and aws server . SO ssh port 22 is open 

- Allow http traffic from anywhere 

- Allow https traffic from anywhere 

Allow traffic from https and http 
default port http --> 80
default https --> 443

In my application say i do app.listen(3000) and deploy on AWS . AWS asks for port to open and i select 3000 . 
Whenever anyone go to https://aws_domain_name_orIP:3000 they can access my code 
But this is not good practise , nobody writes port in url 
SO we do app.listen(80) and it will open on 80 port and everyone can access my application via https://aww_domain_name_orIP which is same as https://aws_domain_name_orIP:80

lauch the instance and your server is running 

### How to SSH into my AWS EC2 Instance?
move .pem file  to your desired folder 
open terminal in that folder 
use command --> ssh -i <certificate_file_name>.pem  <username@ip>