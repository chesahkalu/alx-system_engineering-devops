# 0x09. Web infrastructure design

## About this projecrt:
In this project I Learnt about :
- Networking Basics
- DNS
- Databases
- Web servers
- Application servers
- DNS Record Types
- Fire walls
- Single Point Of Failure
- Monitoring
- Load Balancer
- HTTP and HTTPS
- LAMP stack
- Protocols, Packets, TCP/UP/IP
- Sub-Domain
- High Availabilty
- Ports 

At the end of this project I was able to explain, without the help of Google:
- You must be able to draw a diagram covering the web stack you built with the sysadmin/devops track projects
- You must be able to explain what each component is doing
- You must be able to explain system redundancy
- Know all the mentioned acronyms: LAMP, SPOF, QPS

## Task File Descriptions:
- Each file contains a link to an image hosted on Imgur. 
- The images are designs of a webserver infrastructure on different levels.
- Also in each file are text explaining some specifics and issues about each desgigns.

## [0-simple_web_stack](0-simple_web_stack)
On a whiteboard, design a one server web infrastructure that hosts the website that is reachable via `www.foobar.com.` Start your explanation by having a user wanting to access your website. <br />
You must use:
* 1 physical server
* 1 web server (Nginx)
* 1 application server
* 1 application files (your code base)
* 1 database (MySQL)
* 1 domain name `foobar.com` configured with a `www` record that points to your server IP `8.8.8.8`
You must be able to explain some specifics about this infrastructure:
* What is a server
* What is the role of the domain name
* What type of DNS record www is in www.foobar.com
* What is the role of the web server
* What is the role of the application server
* What is the role of the database
* What is the server using to communicate with the computer of the user requesting the website
You must be able to explain what the issues are with this infrastructure:
* SPOF
* Downtime when maintenance needed (like deploying new code web server needs to be restarted) Cannot scale if too much incoming traffic
### THE DESIGN : :beginner:
![My Image](assets/simple_web_stack.jpeg)
#### Specifics : :eight_pointed_black_star:
- User inputs the `**domain name**` www.foobar.com  into the computer browser.
`**The Domain name**`; www.Fobar.com, is a user friendly name used to link the IP address of the website.
The IP address is a series of numbers which are hard to memorize. eg. 127.345.456.4
The purpose of the domain name is to have a human user friendly representation of the website address.

- For the users computer to map the correct IP address to the domain name, the `**DNS**` system is used. 
`**The Domain Name System(DNS)**` is a system that uses different process and resources to find the correct 
IP address of the domain name being queried. In the DNS system,  www.foobar.com is a conical(alias) name record 
and subdomain of the main root domain name; foobar.com .The root domain name has an A record of 8.8.8.8, which is the IP Address.
Hence, the Cononical Name(name) www.foobar.com , points to the root domain name foobar.com which then points to the IP address 8.8.8.8.

- The IP address 8.8.8.8 is the address of the `**server**`(Nginx) storing the data details of the website www.foobar.com.
`**A server**` is a powerful computer, connected to the internet that provides different functions and services to the end users computers.
In these case, the server 8.8.8.8 is storing the webpage data and other webpage details of www.foobaar.com which the user is requesting to visit.

- The end user's computer brower using `**HTTP**` sends a request to the server for a response with the details of the www.foobar.com website.
`**Hyper Text Transfer protocols(HTTP)**` is a software both on the users computer browser and the end server computer which determines and controls
how the text files and other details of the webpage will be transferred between the two computers.

- `**The Web Server**` provides a static experience of responding and sending back to the client user the pre-stored text and data files of the webpage.
The files stored in HTML, CSS and JAVA script format will be sent back to end users computer browser and displayed as it was stored and designed.

- `**An application server**`  is a software used to provide additional services such as a dynamic web service, where the end user can also upload data
to the website while including so many other additional functions.
Here the application server can update, adjust, moderate, and install different datas and services on the website and computer systems to create a dynamic usage for
both end users of the website.

- The application server would make use of a `**database**`
`**A Database**` is a system that stores different forms of data. It allows the management, creation, updating, and retrieval of data. The Database also gives 
structure to organization business information. With the Data base, a **code base** and the application server, data of both client user and organization user
can be manipulated to create different forms of services.
#### Design Issues and faults: :triangular_flag_on_post:
- `**Single point of failure (SPOF)**`: Failure or malfunction of the server can lead to an entire failure of the system. To avoid this
a second server will be needed as a redundancy.

- `**Downtime**` : A single server can also cause downtime during maintenance, because users can’t access a server if it is offline during maintenance, restart, and update.

- `**scalability**` : Also a single server can affect scalability and downtime during high traffic, this can be resolved by adding a second server to share the traffic loads.










### [1-distributed_web_infrastructure](1-distributed_web_infrastructure)
On a whiteboard, design a three servers web infrastructure that host the website `www.foobar.com`. <br />
You must add to [0-simple_web_stack](0-simple_web_stack):
* 2 physical servers
* 1 web server (Nginx)
* 1 application server
* 1 load-balancer (HAproxy)
* 1 application files (your code base)
* 1 database (MySQL)
You must be able to explain some specifics about this infrastructure:
* For every additional element, why you are adding it
* What distribution algorithm your load balancer is configured with and how it works
* Is your load-balancer enabling an Active-Active or Active-Passive setup, explain the difference between both
* How a database Primary-Replica (Master-Slave) cluster works
* What is the difference between the Primary node and the Replica node in regard to the application
You must be able to explain what the issues are with this infrastructure:
* Where are SPOF
* Security issues (no firewall, no HTTPS)
* No monitoring

### [2-secured_and_monitored_web_infrastructure](2-secured_and_monitored_web_infrastructure)
On a whiteboard, design a three servers web infrastructure that host the website `www.foobar.com`, it must be secured, serve encrypted traffic and be monitored. <br />
You must add to [1-distributed_web_infrastructure](1-distributed_web_infrastructure):
* 3 firewalls
* 1 SSL certificate to serve `www.foobar.com` over HTTPS
* 3 monitoring clients (data collector for Sumologic or other monitoring services)
You must be able to explain some specifics about this infrastructure:
* For every additional element, why you are adding it
* What are firewalls for
* Why is the traffic served over HTTPS
* What monitoring is used for
* How the monitoring tool is collecting data
* Explain what to do if you want to monitor your web server QPS
You must be able to explain what the issues are with this infrastructure:
* Why terminating SSL at the load balancer level is an issue
* Why having only one MySQL server capable of accepting writes is an issue
* Why having servers with all the same components (database, web server and application server) might be a problem

### [3-scale_up](3-scale_up)
You must add to [2-secured_and_monitored_web_infrastructure](2-secured_and_monitored_web_infrastructure):
* 1 physical server
* 1 load-balancer (HAproxy) configured as cluster with the other one
* Split components (web server, application server, database) with their own server
You must be able to explain some specifics about this infrastructure:
* For every additional element, why you are adding it

