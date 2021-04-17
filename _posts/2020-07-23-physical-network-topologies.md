---
layout: post
title:  "Physical Network Topologies"
description: How physical network topologies are setup.
date:   2020-07-23 00:00:00 -0500
categories: [Networking]
---
A Network topology is the way a network is organized, including the physical or logical characterization of how nodes are set up to connect to each other.

# Bus Topology
The first type of network topology is called a bus, in which all the nodes are connected together using a single cable. In a bus topology every node on the network can see every packet that’s sent on the cable. Each computer can respond to data sent to it and ignore data sent to other computers on the network.
This option is not secure because every node on the network can see every packet. Another downside is that if the cable in a bus network breaks, the entire network is disabled. 
These reasons lead to this topology not being used often today.

![A bus topology.](/images/network-topologies/bus-topology.jpg)
*A bus topology.*

# Star Topology
A star topology, commonly used in LANs, have all nodes individually connected to a central connection point, like a hub or a switch.
If a cable in a star network breaks, only the node connected to that cable is disabled. The other nodes can continue to operate without interruption.
Star topology is commonly used as of today. 

![A star topology.](/images/network-topologies/star-topology.jpg)
*A star topology.*

# Ring Topology
In a ring topology, packets are sent around the circle from computer to computer. All packets travel through a ring in the same direction. A failure or break in any cable or device, breaks the loop and will take down the entire circle.
Ring topology was common years ago, but today is rarely used in business networks.

![A ring topology.](/images/network-topologies/ring-topology.jpg)
*A ring topology.*

# Mesh Topology
A mesh topology has multiple connections between each of the nodes on the network.
The advantage of a mesh topology is that if one connection breaks, the network can use another route.
Mesh topologies aren’t very common in a LAN cause of the number of connections that is necessary to set it up. You can calculate the number of connections in a mesh network using the following formula: N(N-1)/2, where N is the number of nodes. 

![A mesh topology.](/images/network-topologies/mesh-topology.jpg)
*A mesh topology.*

# Hybrid Topology
Hybrid topology is a combination of two or more different topologies. But this type of network is not very common due to fault detection. Installation is also very difficult.

![A hybrid topology.](/images/network-topologies/hybrid-topology.jpg)
*A hybrid topology.*