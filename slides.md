---
theme: seriph
background: https://images.unsplash.com/photo-1523961131990-5ea7c61b2107?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80
class: 'text-center'
highlighter: 'shiki'
download: true
---

# Basic Network

### PMC Training, CODIUM

### Feb 2021

---
layout: section
---

# IP

<!-- Let's start with IP -->

---
layout: two-cols
---

# What is IP?

<img src="/assets/ip/house-address.jpg" class="h-400px mx-auto">
<div class="text-xs italic text-center">Street address</div>

::right::

<div class="container flex flex-col justify-center h-full">
<img src="/assets/ip/ip-address.png" class="h-250px mx-auto">
&nbsp;<br>
<div class="text-xs italic text-center">IP address</div>
</div>

<!-- Basically, IP addresses are just like a name of each computer (a.k.a. device in the network). -->

---

# IP Protocols

<br>

![ip-structure](/assets/ip/ip-structure.png)

<!--
There are two IP protocols in use currently.

The first one is "IPv4" which stands for "Internet Protocol version 4".  
There are 4 sections in an address, each of them can be 0 to 255.  
That means you can create "a name for devices" for about 256^4, roughly, which is 4.3 billion addresses.

You might feel that 4 billions are a huge number, but it's still not enough to serve the amount of devices in the whole world.  

That's why IPv6 was born.

"IPv6" is actually "IP version 6". This new protocol can serve up to 2^128 addresses, roughly!  
Sadly, IPv6 hasn't over taken IPv4 yet.  
Therefore, we're gonna focus on IPv4 at the moment.
-->

---

# Public IP vs Private IP

[Read more](https://www.avast.com/c-ip-address-public-vs-private)

![public-private-ip](/assets/ip/public-private-ip.jpg)

<!--
There are two types of IP addresses you'll need to know which is "Public IP" and "Private IP".

As you can see on the left side, there are 5 devices connected to the router.  
Each of them can talk to each other because they're all in the same network.  
They can also access to the internet via the router as well.

At the router, there is a public IP, 82.129.70.11.  
This is the actual outgoing IP of any data that comes from devices in this network.  
We can say that the public IP is the one that the rest of the world would recognizes, not the private one.

You should notice that anybody outside the network cannot connect to one of the device in the network with their private IP.

Private IPs can also be duplicated in multiple networks since it's only used in a single network. Public IPs can't.
-->

---

# Private IPs

<br>

![private-table](/assets/ip/private-table.png)

<!--
These are all available private IPs.  
You may have heard some of them before.  
These IPs cannot be used to create a connection through the internet, always.
-->

---

# Ports

<br>

<img src="/assets/ip/port.jpg" class="mx-auto">

<!--
Next one is "Ports".

There are a few things you'll need to know about ports.

Port is basically a virtual interface which is used for communicate between two devices.  
We might familiar with the server ports but actually every device has ports.  
For example, port 80 or 443 in the server which is used for accessing the website.  
But in our machine, there is also port in used as well in order to talk with port 80 on the server.  
In this diagram it is port 5000.
-->

---

# Well-known Ports

<br>

| **Port** | **Service** |
| ---- | ---- |
| 80 | HTTP |
| 443 | HTTPS |
| 21 | FTP |
| 22 | SSH, SFTP [^1] (default) |
| 22222 | SSH, SFTP (after server hardened) |
| 5432 | PostgreSQL (database) |

[^1]: SFTP = Secure File Transfer Protocol (basically is FTP via SSH)

---
layout: section
---

# Firewall

<!-- Let's move to Firewall -->

---

![what-is-firewall](/assets/firewall/what-is-firewall.jpg)

<!-- Firewall is a network security system which can filter incoming and outgoing traffic. -->

---

# Firewall Rules

Note that these are only "incoming rules"

![firewall-rules](/assets/firewall/firewall-rules.png)

<!--
In order to activate the firewall, we'll need to setup a rule of traffic that we'll allow or deny. It's called "Firewall Rules".

This is an example of firewall rules from CloudHM which we're familiar with.

In the first 5 records, we allow some machines to connect with our port number 22, 5432, 22222.  
And the last one is 0.0.0.0/0 which allow any machines to connect with port number 80, 443.

There is also "outgoing rules" but normally our VMs are allowed for any outgoing connection.  
It may not be in the on-premise server.

Firewall plays a huge role in network security. Therefore, it is a best practice to always setup a firewall in order to prevent unwanted traffic from an attacker.
-->
