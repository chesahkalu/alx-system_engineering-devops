# Firewall :page_with_curl: 0x13-firewall

## About this project :bulb:
In this project, I learned about firewalls and how to configure them using `UFW`(Uncomplicated Firewall) in a `Ubuntu` server.
A firewall is a network security device that monitors and controls incoming and outgoing network traffic based on a set of rules. 
The main purpose of a firewall is to prevent unauthorized access to or from a network.

`Computers` communicate with each other using `IP addresses`. `Softwares` and `services` running on computers use `port numbers` to identify 
specific applications and services to which they want to send or receive data. 

A firewall can be configured to allow or block traffic based on IP addresses and port numbers. For example, a firewall can be configured
to allow web traffic from specific IP addresses and block all other traffic. Similarly, a firewall can be configured to block all incoming 
traffic to a specific port, such as port 25, to prevent unauthorized access to email servers.

Firewalls can be configured based on `outgoing` and `incoming` traffic. Commonly, firewalls are configured to allow all outgoing traffic enabling
the computer to communicate with other computers. However, firewalls are configured to allow only specific incoming traffic. This is done to
prevent unauthorized access to the computer. Eg. A firewall can be configured to allow incoming traffic to port 80 (HTTP) and port 443 (HTTPS)
to allow web traffic to the computer.

The two types of fire wall `network based` and `host based`; network based are installed on the network like routers and host based are installed on 
the host machine.

`WARNING:`Be very careful with firewall rules! For instance, if you ever deny port 22/TCP and log out of your server, you will not be able to reconnect
to your server via SSH, and we will not be able to recover it. When you install UFW, port 22 is blocked by default, so you should unblock it immediately 
before logging out of your server.

## Tasks files description: :books:

* [0-block_all_incoming_traffic_but](./0-block_all_incoming_traffic_but): Bash
  script that installs a `ufw` firewall to block all incoming traffic except for
  ports `22`, `443` and `80` on a web server.

* [100-port_forwarding](./100-port_forwarding): `ufw` configuration file that
  configures a firewall to redirect port `8080/TCP` to port `80/TCP`.i

