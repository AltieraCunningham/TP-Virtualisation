# TP1 : Remise dans le bain

## I. Most simplest LAN

### Mac addresses
```telnet
node1> show ip

NAME        : node1[1]  
IP/MASK     : 10.1.1.1/24  
[snip]
MAC         : 00:50:79:66:68:01  
[snip]
```

```telnet
node2> show ip

NAME        : node2[1]  
IP/MASK     : 10.1.1.2/24  
[snip]
MAC         : 00:50:79:66:68:00  
[snip]
```

### Static IPs

Setting IPs
```telnet
node1> ip 10.1.1.1/24     
Checking for duplicate address...  
node1 : 10.1.1.1 255.255.255.0
```

```telnet
node2> ip 10.1.1.2/24     
Checking for duplicate address...  
node2 : 10.1.1.2 255.255.255.0
```

Checking IPs with `show ip`
```telnet
node1> show ip  
  
NAME        : node1[1]  
IP/MASK     : 10.1.1.1/24  
[snip]
```

```telnet
node2> show ip     
  
NAME        : node2[1]  
IP/MASK     : 10.1.1.2/24  
[snip]
```

Checking IPs with `ping [target]`
```telnet
node1> ping 10.1.1.2  
  
84 bytes from 10.1.1.2 icmp_seq=1 ttl=64 time=0.728 ms  
84 bytes from 10.1.1.2 icmp_seq=2 ttl=64 time=0.895 ms  
84 bytes from 10.1.1.2 icmp_seq=3 ttl=64 time=0.957 ms  
84 bytes from 10.1.1.2 icmp_seq=4 ttl=64 time=0.672 ms
```

```telnet
node2> ping 10.1.1.1  
  
84 bytes from 10.1.1.1 icmp_seq=1 ttl=64 time=1.238 ms  
84 bytes from 10.1.1.1 icmp_seq=2 ttl=64 time=0.555 ms  
84 bytes from 10.1.1.1 icmp_seq=3 ttl=64 time=0.950 ms  
84 bytes from 10.1.1.1 icmp_seq=4 ttl=64 time=0.748 ms
```

### Ping 

ICMP

### ARP

```telnet
node1> arp    
  
00:50:79:66:68:00  10.1.1.2 expires in 116 seconds
```

```telnet
node2> arp  
  
00:50:79:66:68:01  10.1.1.1 expires in 110 seconds
```

## II. Ajoutons un switch

### Mac Addresses

```telnet
node1> show ip  
  
NAME        : node1[1]  
[snip]
MAC         : 00:50:79:66:68:01  
[snip]
```

```telnet
node2> show ip  
  
NAME        : node2[1]  
[snip]
MAC         : 00:50:79:66:68:00  
[snip]
```

```telnet
node3> show ip  
  
NAME        : node3[1]
[snip]
MAC         : 00:50:79:66:68:02  
[snip]
```

### IPs 

Setting IPs
```telnet
node1> ip 10.1.1.1/24     
Checking for duplicate address...  
node1 : 10.1.1.1 255.255.255.0
```

```telnet
node2> ip 10.1.1.2/24     
Checking for duplicate address...  
node2 : 10.1.1.2 255.255.255.0
```

```telnet
node3> ip 10.1.1.3/24
Checking for duplicate address...
node3 : 10.1.1.3 255.255.255.0
```

Checking IPs
```telnet
node1> show ip  
  
NAME        : node1[1]  
IP/MASK     : 10.1.1.1/24  
[snip]   
```

```telnet
node2> show ip  
  
NAME        : node2[1]  
IP/MASK     : 10.1.1.2/24  
[snip]  
```

```telnet
node3> show ip  
  
NAME        : node3[1]  
IP/MASK     : 10.1.1.3/24  
[snip]   
```

### Pings

```telnet
node1> ping 10.1.1.2     
  
84 bytes from 10.1.1.2 icmp_seq=1 ttl=64 time=0.481 ms  
84 bytes from 10.1.1.2 icmp_seq=2 ttl=64 time=0.714 ms  
84 bytes from 10.1.1.2 icmp_seq=3 ttl=64 time=0.922 ms  
84 bytes from 10.1.1.2 icmp_seq=4 ttl=64 time=0.883 ms  
84 bytes from 10.1.1.2 icmp_seq=5 ttl=64 time=0.438 ms  
  
node1> ping 10.1.1.3  
  
84 bytes from 10.1.1.3 icmp_seq=1 ttl=64 time=0.740 ms  
84 bytes from 10.1.1.3 icmp_seq=2 ttl=64 time=0.964 ms  
84 bytes from 10.1.1.3 icmp_seq=3 ttl=64 time=0.759 ms  
84 bytes from 10.1.1.3 icmp_seq=4 ttl=64 time=0.679 ms  
84 bytes from 10.1.1.3 icmp_seq=5 ttl=64 time=0.639 ms
```

```telnet
node2> ping 10.1.1.1  
  
84 bytes from 10.1.1.1 icmp_seq=1 ttl=64 time=1.384 ms  
84 bytes from 10.1.1.1 icmp_seq=2 ttl=64 time=0.628 ms  
84 bytes from 10.1.1.1 icmp_seq=3 ttl=64 time=0.769 ms  
84 bytes from 10.1.1.1 icmp_seq=4 ttl=64 time=1.636 ms  
84 bytes from 10.1.1.1 icmp_seq=5 ttl=64 time=0.841 ms  
  
node2> ping 10.1.1.3  
  
84 bytes from 10.1.1.3 icmp_seq=1 ttl=64 time=0.928 ms  
84 bytes from 10.1.1.3 icmp_seq=2 ttl=64 time=1.928 ms  
84 bytes from 10.1.1.3 icmp_seq=3 ttl=64 time=1.159 ms  
84 bytes from 10.1.1.3 icmp_seq=4 ttl=64 time=1.006 ms  
84 bytes from 10.1.1.3 icmp_seq=5 ttl=64 time=1.137 ms
```

```telnet
node3> ping 10.1.1.1  
  
84 bytes from 10.1.1.1 icmp_seq=1 ttl=64 time=1.173 ms  
84 bytes from 10.1.1.1 icmp_seq=2 ttl=64 time=1.433 ms  
84 bytes from 10.1.1.1 icmp_seq=3 ttl=64 time=0.728 ms  
84 bytes from 10.1.1.1 icmp_seq=4 ttl=64 time=0.980 ms  
84 bytes from 10.1.1.1 icmp_seq=5 ttl=64 time=0.997 ms  
  
node3> ping 10.1.1.2  
  
84 bytes from 10.1.1.2 icmp_seq=1 ttl=64 time=1.683 ms  
84 bytes from 10.1.1.2 icmp_seq=2 ttl=64 time=1.533 ms  
84 bytes from 10.1.1.2 icmp_seq=3 ttl=64 time=1.726 ms  
84 bytes from 10.1.1.2 icmp_seq=4 ttl=64 time=1.106 ms  
84 bytes from 10.1.1.2 icmp_seq=5 ttl=64 time=0.965 ms
```

## III. Serveur DHCP

### Legit
Install the server
```shell
dnf update
dnf install dhcp-server
```

DHCP config
```conf  
option domain-name     "tp1.efrei";
  
default-lease-time 600;
  
max-lease-time 7200;

authoritative;

subnet 10.1.1.0 netmask 255.255.255.0 {
    range dynamic-bootp 10.1.1.10 10.1.1.50;
    option broadcast-address 10.1.1.255;
}
```

```shell
systemctl enable --now dhcpd

firewall-cmd --add-service=dhcp
firewall-cmd --runtime-to-permanent

```



### Get DHCP IPs
```telnet
node1> ip dhcp           
DORA  
node1> show ip IP 10.1.1.10/24  
  
NAME        : node1[1]  
IP/MASK     : 10.1.1.10/24  
[snip]
```

```telnet
node2> ip dhcp  
DDORA  
node2> show ip IP 10.1.1.11/24  
  
NAME        : node2[1]  
IP/MASK     : 10.1.1.11/24  
[snip]
```

```telnet
node3> ip dhcp  
DDORA  
node3> show ip IP 10.1.1.12/24  
  
NAME        : node3[1]  
IP/MASK     : 10.1.1.12/24  
[snip]
```


## DHCP spoofing

### Dnsmasq config
dnsmasq config 
```bash
dhcp-range=10.1.1.210,10.1.1.250,12h
```

### Dnsmasq testing

```telnet
node1> ip dhcp
DORA IP 10.1.1.245/24 GW 10.1.1.13
```

```telnet
node2> ip dhcp
DORA IP 10.1.1.247/24 GW 10.1.1.13
```

```telnet
node3> ip dhcp
DORA IP 10.1.1.246/24 GW 10.1.1.13
```

### RACE

```telnet
node1> ip dhcp  
DORA IP 10.1.1.245/24 GW 10.1.1.13  
  
node1> ip dhcp  
DORA IP 10.1.1.245/24 GW 10.1.1.13  
  
node1> ip dhcp  
DORA IP 10.1.1.11/24 GW 10.1.1.13  
  
node1> ip dhcp  
DORA IP 10.1.1.11/24 GW 10.1.1.13  
  
node1> ip dhcp  
DORA IP 10.1.1.245/24 GW 10.1.1.13
```

```telnet
node2> ip dhcp  
DORA IP 10.1.1.247/24 GW 10.1.1.13  
  
node2> ip dhcp  
DORA IP 10.1.1.12/24 GW 10.1.1.13  
  
node2> ip dhcp  
DORA IP 10.1.1.247/24 GW 10.1.1.13  
  
node2> ip dhcp  
DORA IP 10.1.1.247/24 GW 10.1.1.13
```

```telnet
node3> ip dhcp  
DORA IP 10.1.1.246/24 GW 10.1.1.13  
  
node3>    
node3> ip dhcp  
DORA IP 10.1.1.246/24 GW 10.1.1.13  
  
node3> ip dhcp  
DORA IP 10.1.1.246/24 GW 10.1.1.13  
  
node3> ip dhcp  
DORA IP 10.1.1.10/24 GW 10.1.1.13  
  
node3> ip dhcp  
DORA IP 10.1.1.246/24 GW 10.1.1.13
```

```telnet
PC1> ip dhcp  
DDORA IP 10.1.1.248/24 GW 10.1.1.13  
  
PC1> ip dhcp  
DORA IP 10.1.1.248/24 GW 10.1.1.13  
  
PC1> ip dhcp  
DORA IP 10.1.1.248/24 GW 10.1.1.13
```