# SDN-Access-Control-Mininet


# Student Details

Name: Patnaikuni Sai Dheeraj
SRN: PES2UG24CS341



# Description

This project implements access control in Software Defined Networking using the Ryu controller and Mininet.

The controller filters traffic based on MAC addresses. Only selected hosts are allowed to communicate, while others are blocked.



# Objective

* To understand SDN architecture
* To implement access control using a controller
* To simulate a network using Mininet



# Topology

The topology consists of:

* 1 switch (s1)
* 3 hosts (h1, h2, h3)

All hosts are connected to a single switch.

MAC addresses:

* h1 → 00:00:00:00:00:01
* h2 → 00:00:00:00:00:02
* h3 → 00:00:00:00:00:03



## Access Control Logic

Whitelist:

* h1
* h2

Blocked:

* h3

Behavior:

* h1 can communicate with h2
* h2 can communicate with h1
* h3 is blocked from communicating with other hosts



# How to Run

Activate environment:

```bash
source ryu-env/bin/activate
```

Run controller:

```bash
ryu-manager access_control.py
```

Run Mininet:

```bash
sudo mn --topo single,3 --mac --controller=remote,ip=127.0.0.1,port=6633
```



# Results

Allowed:

```bash
h1 ping h2
h2 ping h1
```

Blocked:

```bash
h3 ping h1
h3 ping h2
```

The controller logs show blocked MAC address:
BLOCKED: 00:00:00:00:00:03



# Files

* access_control.py
* README.md
* screenshots folder



