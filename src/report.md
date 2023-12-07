# Report

## **Part 1. ipcalc tool**
- ***Start a virtual machine (hereafter -- ws1)***
  - ![ws1](img/1-install.png)

<br><br>

- ***1.1 Networks and Masks***
    - network address of 192.167.38.54/13
      - ![1.1.1](img/1.1-1.png)
        > `192.167.38.54`
    - conversion of the mask 255.255.255.0 to prefix and binary, /15 to normal and binary, 11111111.11111111.11111111.11110000 to normal and prefix
      - ![1.1.2.1](img/1.1-2.1.png)
        > `prefix is /24`<br>`binary is 11111111.11111111.11111111. 000000000`
      - ![1.1.2.2](img/1.1-2.2.png)
        > `normal is 255.254.0.0`<br>`binary is 11111111.11111110.00000000. 00000000`
      - 11111111.11111111.11111111.11110000
        > `normal is 255.255.255.240`<br>`prefix is /28`
    - minimum and maximum host in 12.167.38.4 network with masks: /8, 11111111.11111111.00000000.00000000, 255.255.254.0 and /4
      - ![1.1.3.1](img/1.1-3.3.1.png)
        > `/8: min is 12.0.0.1, max is 12.255.255.254`<br>`/4: min is 0.0.0.1, max is 15.255.255.254`
      - ![1.1.3.2](img/1.1-3.3.2.png)
        > `11111111.11111111.00000000.00000000: min is 12.167.0.1, max is 12.167.255.254`<br>`255.255.254.0: min is 12.167.38.1, max is 12.167.39.254`

<br><br>

- ***1.2 localhost***
    - Define and write in the report whether an application running on localhost can be accessed with the following IPs: 194.34.23.100, 127.0.0.2, 127.1.0.1, 128.0.0.1
      - `localhost is 127.*.*.* -> only 127.0.0.2 and 127.1.0.1 is accessible` 

<br><br>

- ***1.3 Network ranges and segments***
    - which of the listed IPs can be used as public and which only as private: 10.0.0.45, 134.43.0.2, 192.168.4.2, 172.20.250.4, 172.0.2.1, 192.172.0.1, 172.68.0.2, 172.16.255.255, 10.10.10.10, 192.169.168.1
      - `public : 134.43.0.2, 172.0.2.1, 192.172.0.1, 192.169.168.1`
      - `private: 10.0.0.45, 10.10.10.10, 192.168.4.2, 172.20.250.4, 172.68.0.2, 172.16.255.255`
    - which of the listed gateway IP addresses are possible for 10.10.0.0/18 network: 10.0.0.1, 10.10.0.2, 10.10.10.10, 10.10.100.1, 10.10.1.255
      - `10.10.0.2, 10.10.10.10, 10.10.100.1, 10.10.1.255`

<br><br>

## **Part 2. Static routing between two machines**
- ***Start two virtual machines (hereafter -- ws1 and ws2)***
  - ![2.0-1](img/2.0-1.png)

<br><br>

- ***View existing network interfaces with the ip a command***
  - ws1
    - ![2.0-2](img/2.0-2.png)
  - ws2
    - ![2.0-3](img/2.0-3.png)

<br><br>

- ***Describe the network interface corresponding to the internal network on both machines and set the following addresses and masks: ws1 - 192.168.100.10, mask \*/16 \*, ws2 - 172.24.116.8, mask /12***
  - ws1
    - ![2.0-4](img/2.0-4.png)
  - ws2
    - ![2.0-5](img/2.0-5.png)

<br><br>

- ***Run the netplan apply command to restart the network service***
  - ws1
    - ![2.0-6](img/2.0-6.png)
  - ws2
    - ![2.0-7](img/2.0-7.png)

<br><br>

- ***2.1 Adding a static route manually***
  - ws1
    - ![2.1-1](img/2.1-1.png)
    - ![2.1-3](img/2.1-3.png)    
  - ws2
    - ![2.1-2](img/2.1-2.png)
    - ![2.1-4](img/2.1-4.png)

<br><br>

- ***2.2 Adding a static route with saving***
  - ws1
    - ![2.2-1](img/2.2-1.png)
    - ![2.2-3](img/2.2-3.png)    
  - ws2
    - ![2.2-2](img/2.2-2.png)
    - ![2.2-4](img/2.2-4.png)

<br><br>

## **Part 3. iperf3 utility**
- ***3.1 Connection speed***
  - `8 Mbps is 1 MB/s`
  - `100 MB/s is 800000 Kbps`
  - `1 Gbps is 1000 Mbps`

<br><br>

- ***3.2 iperf3 utility***
  - ![3.2-1](img/3.2-1.png)
  - ![3.2-2](img/3.2-2.png)
  - `connection speed is 3.25 Gbits/sec`

<br><br>

## **Part 4. Network firewall**
- ***4.1 iptables utility***
  - ws1
    - ![4.1-1](img/4.1-1.png)
    - ![4.1-3](img/4.1-3.png)
  - ws2
    - ![4.1-2](img/4.1-2.png)
    - ![4.1-4](img/4.1-4.png)
  - `strategy difference: first is to DROP connection, second is to ACCEPT` 

<br><br>

- ***4.2 nmap utility***
  - ![4.2-1](img/4.2-1.png)

<br><br>

## **Part 5. Static network routing**
- ***Start five virtual machines (3 workstations (ws11, ws21, ws22) and 2 routers (r1, r2))***
  - ![5.0](img/5.0.png)

<br><br>

- ***5.1 Configuration of machine addresses***
  - ws11
    - ![5.1-1](img/5.1-1.png)
    - ![5.1-6](img/5.1-6.png)
  - ws21
    - ![5.1-2](img/5.1-2.png)
    - ![5.1-7](img/5.1-7.png)
  - ws22
    - ![5.1-3](img/5.1-3.png)
    - ![5.1-8](img/5.1-8.png)
  - r1
    - ![5.1-4](img/5.1-4.png)
    - ![5.1-9](img/5.1-9.png)
  - r2
    - ![5.1-5](img/5.1-5.png)
    - ![5.1-10](img/5.1-10.png)
  - ping ws22 from ws21
    - ![5.1-11](img/5.1-11.png)
  - ping r1 from ws11
    - ![5.1-12](img/5.1-12.png)

<br><br>

- ***5.2 Enabling IP forwarding***
  - r1
    - ![5.2-1](img/5.2-1.png)
    - ![5.2-3](img/5.2-3.png)
    - ![5.2-5](img/5.2-5.png)
  - r2
    - ![5.2-2](img/5.2-2.png)
    - ![5.2-4](img/5.2-4.png)
    - ![5.2-6](img/5.2-6.png)

<br><br>

- ***5.3 Default route configuration***
  - ws11
    - ![5.3-1](img/5.3-1.png)
    - ![5.3-4](img/5.3-4.png)
  - ws21
    - ![5.3-2](img/5.3-2.png)
    - ![5.3-5](img/5.3-5.png)
  - ws22
    - ![5.3-3](img/5.3-3.png)
    - ![5.3-6](img/5.3-6.png)
  - ping r2 from ws11
    - ![5.3-7](img/5.3-7.png)
    - ![5.3-8](img/5.3-8.png)

<br><br>

- ***5.4 Adding static routes***
  - r1
    - ![5.4-1](img/5.4-1.png)
    - ![5.4-3](img/5.4-3.png)
  - r2
    - ![5.4-2](img/5.4-2.png)
    - ![5.4-4](img/5.4-4.png)
  - ws11
    - ![5.4-5](img/5.4-5.png)
    - `for 10.10.0.0/18 had been selected different route for blocking packet transition to the other addresses going to 0.0.0.0/0`

<br><br>

- ***5.5 Making a router list***
  - r1
    - ![5.5-1](img/5.5-1.png)
  - ws11
    - ![5.5-2](img/5.5-2.png)
  - `traceroute using UDP packets, it sends TTL=1 packet and checks address of the gate, next it sends TTL=2, TTL=3... until it reach the end. Every time it sends 3 packets and measures time for each one, when traceroute gets error reaching a port it stops`

<br><br>

- ***5.6 Using ICMP protocol in routing***
  - r1
    - ![5.6-1](img/5.6-1.png)
  - ws11
    - ![5.6-2](img/5.6-2.png)

<br><br>

## **Part 6. Dynamic IP configuration using DHCP**
  - ***6.1 specify the default router address, DNS-server and internal network address***
    - ![6.0-1](img/6.0-1.png)

  <br><br>

  - ***6.2***
    - ![6.2-1](img/6.2-1.png)
      > *write nameserver 8.8.8.8. in a resolv.conf file*
    - ![6.2-2](img/6.2-2.png)
    - ![6.2-3](img/6.2-3.png)
    - ![6.2-4](img/6.2-4.png)
      > *Specify MAC address at ws11 by adding to etc/netplan/00-installer-config.yaml*
    - ![6.2-5](img/6.2-5.png)
    - ![6.2-6](img/6.2-6.png)
      > *Сonfigure r1 the same way as r2*
    - ![6.2-7](img/6.2-7.png)
    - ![6.2-8](img/6.2-8.png)
    - ![6.2-9](img/6.2-9.png)
    - ![6.2-10](img/6.2-10.png)
      > *Request ip address update from ws21*
    - `we erased old IP with dhclient -r, then got new one with dhclient`

<br><br>

## **Part 7. NAT**
  - ![7.0-1](img/7.0-1.png)
    > *change the line Listen 80 to Listen 0.0.0.0:80on ws22*
  - ![7.0-2](img/7.0-2.png)
    > *change the line Listen 80 to Listen 0.0.0.0:80on r1*
  - ![7.0-3](img/7.0-3.png)
    > *start apache on ws22*
  - ![7.0-4](img/7.0-4.png)
    > *start apache on r1*

  <br><br>

  - ***7.1-7.3***
    - ![7.1-1](img/7.1-1.png)
      > *delete rules in the filter table - iptables -F<br>delete rules in the "NAT" table - iptables -F -t nat<br>drop all routed packets - iptables --policy FORWARD DROP*
    - ![7.2](img/7.2.png)
    - ![7.2-1](img/7.2-1.png)
      > *Check connection between ws22 and r1 with the ping command*
  
  <br><br>

  - ***7.4 allow routing of all ICMP protocol packets***
    - ![7.4-1](img/7.4-1.png)
    - ![7.4-2](img/7.4-2.png)
    - ![7.4-3](img/7.4-3.png)

  <br><br>

  - ***7.5-7.6***
    - ![7.5-1](img/7.5-1.png)
    - ![7.5-2](img/7.5-2.png)
    - ![7.5-3](img/7.5-3.png)
    - ![7.5-4](img/7.5-4.png)

  <br><br>

## **Part 8. Introduction to SSH Tunnels**
  - ![8.0-1](img/8.0-1.png)
    > *starting firewall*
  - ![8.0-2](img/8.0-2.png)
    > *starting apache server with Listen localhost:80*
  - ![8.0-3](img/8.0-3.png)
    > *local TCP forwarding*
  - ![8.0-4](img/8.0-4.png)
    > *remote TCP forwarding*

  <br><br>