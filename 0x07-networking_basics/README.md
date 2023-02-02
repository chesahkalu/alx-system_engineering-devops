# Networking basics :page_with_curl: 0x07-networking_basics
## About thiss project :
In this project i learnt and practiced;
* OSI model
  * What is it?
  * How many layers does it have?
  * How is it organized?
* LAN
  * What is it?
  * What is its typical usage?
  * What is its typical geographical size?
* WAN
  * What is it?
  * What is its typical usage?
  * What is its typical geographical size?
* What is the Internet?
* IP addresses
  * What are they?
  * What are the two types of IP addresses?
  * What is `localhost`?
  * What is a subnet?
  * Why was IPv6 created?
* TCP/UDP
  * What are the 2 mainly used data transfer protocols for IP?
  * What is the main difference between TCP and UDP?
* TCP/UDP Ports
  * What is a port?
  * What are ports are used for SSH, HTTP, and HTTPS?
* What tools/protocols are often used to check if a device is connected to a network?
## Task files description:
* [0-OSI_model](./0-OSI_model): Text file answering the following questions:
  * What is the OSI model?
    1. Set of specifications that network hardware manufacturers must respect
    2. The OSI model is a conceptual model that characterizes the communication
    functions of a telecommunication system without regard to their underlying
    internal structure and technology.
    3. The OSI model is a model that characterizes the communication functions
    of a telecommunication system with a strong regard for their underlying
    internal structure and technology.
  * How is the OSI model organized?
    1. Alphabetically
    2. From the lowest to the highest level
    3. Randomly

  * [1-types_of_network](./1-types_of_network): Text file answering the following questions:
  * What type of network are Holberton iMacs connected to?
    1. Internet
    2. WAN
    3. LAN
  * What type of network could connect an office in one building to another
  office in a building a few streets away?
    1. Internet
    2. WAN
    3. LAN
  * What network do you use when you browse www.holbertonschool.com from your
  smartphone (not connected to the Wifi)?
    1. Internet
    2. WAN
    3. LAN

  * [2-MAC_and_IP_address](./2-MAC_and_IP_address): Text file answering the following questions:
  * What is a MAC address?
    1. The name of a network interface
    2. The unique identifier of a network interface
    3. A network interface
  * What is an IP address?
    1. Is to devices connected to a network what postal address is to houses
    2. The unique identifier of a network interface
    3. Is a number that network devices use to connect to networks

  * [3-UDP_and_TCP](./3-UDP_and_TCP): Text file answering the following questions
  (boxes refer to an image provided by Holberton School):
  * Which statement is correct for the TCP box:
    1. It is a protocol that is transferring data in a slow way but surely
    2. It is a protocol that is transferring data in a fast way and might loss
    data along in the process
  * Which statement is correct for the UDP box:
    1. It is a protocol that is transferring data in a slow way but surely
    2. It is a protocol that is transferring data in a fast way and might loss
    data along in the process
  * Which statement is correct for the TCP worker:
    1. Have you received boxes x, y, z?
    2. May I increase the rate at which I am sending you boxes?

  * [4-TCP_and_UDP_ports](4-TCP_and_UDP_ports): A Bash script that displays listening ports with the requirements:
   * Only shows listening sockets
   * Shows the PID and name of the program to which each socket belongs
```
sylvain@ubuntu$ sudo ./4-TCP_and_UDP_ports
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 *:sunrpc                *:*                     LISTEN      518/rpcbind
tcp        0      0 *:ssh                   *:*                     LISTEN      1240/sshd
tcp        0      0 *:32938                 *:*                     LISTEN      547/rpc.statd
tcp6       0      0 [::]:sunrpc             [::]:*                  LISTEN      518/rpcbind
tcp6       0      0 [::]:ssh                [::]:*                  LISTEN      1240/sshd
tcp6       0      0 [::]:33737              [::]:*                  LISTEN      547/rpc.statd
udp        0      0 *:sunrpc                *:*                                 518/rpcbind
udp        0      0 *:691                   *:*                                 518/rpcbind
udp        0      0 localhost:723           *:*                                 547/rpc.statd
udp        0      0 *:60129                 *:*                                 547/rpc.statd
udp        0      0 *:3845                  *:*                                 562/dhclient
udp        0      0 *:bootpc                *:*                                 562/dhclient
udp6       0      0 [::]:47444              [::]:*                              547/rpc.statd
udp6       0      0 [::]:sunrpc             [::]:*                              518/rpcbind
udp6       0      0 [::]:50038              [::]:*                              562/dhclient
udp6       0      0 [::]:691                [::]:*                              518/rpcbind
Active UNIX domain sockets (only servers)
Proto RefCnt Flags       Type       State         I-Node   PID/Program name    Path
unix  2      [ ACC ]     STREAM     LISTENING     7724     518/rpcbind         /run/rpcbind.sock
unix  2      [ ACC ]     STREAM     LISTENING     6525     1/init              @/com/ubuntu/upstart
unix  2      [ ACC ]     STREAM     LISTENING     8559     835/dbus-daemon     /var/run/dbus/system_bus_socket
unix  2      [ ACC ]     STREAM     LISTENING     9190     1087/acpid          /var/run/acpid.socket
unix  2      [ ACC ]     SEQPACKET  LISTENING     7156     378/systemd-udevd   /run/udev/control
sylvain@ubuntu$
```
  * [5-is_the_host_on_the_network](5-is_the_host_on_the_network) - a Bash script that pings an IP address passed as an argument. Requirements:
   * Accepts a string as an argument
   * Displays `Usage: 5-is_the_host_on_the_network {IP_ADDRESS}` if no argument passed
   * Pings the IP 5 times
```
sylvain@ubuntu$ ./5-is_the_host_on_the_network 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=63 time=12.9 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=63 time=13.6 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=63 time=7.83 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=63 time=11.3 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=63 time=7.57 ms

--- 8.8.8.8 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4006ms
rtt min/avg/max/mdev = 7.570/10.682/13.679/2.546 ms
sylvain@ubuntu$
sylvain@ubuntu$ ./5-is_the_host_on_the_network
Usage: 5-is_the_host_on_the_network {IP_ADDRESS}
sylvain@ubuntu$
```
