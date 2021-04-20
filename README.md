<!-- 
OSI all layers
TCP/IP all layers and its functions, protocols in all layers
TCP/IP vs OSI
HTTP vs HTTPS
subnetting
networking topologies, when where
types of networks
DNS
MAC address
IPV4 IPV6
what is protocol
port numbers of important protocol

Routers, switch, hub, servers, workstations
proxy servers
firewalls -->


# OSI Model

![picture alt](images/computer-network-osi-model-layers.png "Title is optional")<br><br>

* OSI is layered model for consist of 7 layers
* It describes how data is send from one computer to other
* each layer has diffrant function
* while sending each layer get data from upper layer and give data to lower layer
* while sending each layer get data from lower layer and give data to upper layer
* OSI is only refrance model and not practically used.
* 7 Layers of OSI Model
  * Application
  * Session
  * Presentation
  * Transport
  * Network
  * Data Link
  * Physical



![picture alt](images/The-7-Layers-of-OSI.png "Title is optional")


<br><br>

# Physical Layer

* Lowest Layer in hierachy
* deal with physical transmition of data bits .
* while sending it converts 0 & 1 into electrical signal
* while reciving converts electrical signal into 0, 1.

![picture alt](images/physicallayer.jpg "Title is optional")

## Functions

### Bit Syncronization: 
provide clock timing. Determining the boundary (start and end) of signal bit i.e. time window for a bit.
<br><br>
  
### Bit Rate control
if sender is fast and reciver is slow physical layer manges the data tranmition rate i.e. bit transmission per second. 
<br><br>

### Topology
physical layer defines way of diffrant devices arranged in netwok
<br><br>

### Transmition modes 
it defines mode of data flow between two connected device

    Simplex: one way communication. only one sender can send and other only recive ie. Brodcasting, eg FM radio

    Half duplex: both user can send but at a time one sends and other recives two user cannot send data at a time. e.g Walkie-talkie 

    Full duplex: both can send and recive at a time. e.g phone call

[Simplex, Half duplex & full Duplex](https://www.geeksforgeeks.org/difference-between-simplex-half-duplex-and-full-duplex-transmission-modes/)


___Devices works on physical layer:  Hub, Repeater, Modem, Cables___

<br><br>

# Data Link Layer

* Responsible for node to node delivery of data.
* It is responsible for error-free data transmission 
* Transmit data using mac address
* receive packet from Network layer 
* packet further divided into frames depending on the frame size of NIC(Network Interface Card)
* The Receiver’s MAC address is obtained by placing an ARP(Address Resolution Protocol) request and destination host will reply with its MAC address
  
* Two sublayers
    * Logical Link control
    * Media acsess control 

![picture alt](images/data'/[link.jfif "Title is optional")


## Functions of Data Link Layer

### Framing
Its convert data packet into data frame and add meaningfull header to ensure transmission of data to meaningfull reciever

### Physical Addressing 
Adds physical address of sender and reciever to the headder of each frame

### Error Control
bits added at end to detect error. Diffrent Error Correction & Detection algo used to control Error. and retransmit damaged packet

[Error corrections & Detection: see only parity checking, CRC, LRC & Hamming code](https://www.electronicshub.org/error-correction-and-detection-codes)

[Error Control Protocols- stop & wait Arq, Go back N ARQ, & Selective Repeat ARQ](https://www.tutorialspoint.com/error-control-in-data-link-layer)

### Flow Control
Data transmission rate must be constant on both side else data get corrupted
flow control manage the amount of data can send before reciving acknoledgement

[Flow Control Protocols: Stop & wait, Sliding Window](https://www.tutorialspoint.com/flow-control-in-data-link-layer)


### Access control: 
When a single communication channel is shared by multiple devices, MAC sub-layer of data link layer helps to determine which device has control over the channel at a given time

[Access Control Protocols: see in beolow image](https://www.geeksforgeeks.org/multiple-access-protocols-in-computer-network)

![picture alt](images/accPro.jpg "Title is optional")

___Devices works on physical layer:  Switch & Bridge___

# Network Layer

* Network layer works transmission of data from one host to another which located in diffrent network.
* Chooses shortest path from available paths for transmission
* It adds sender's & reciever's IP address in the header of packet

## Functions of network Layers

### Routing
Determine the which route(shortest route) should be taken from source to destination. 

[Routing Algo](https://www.tutorialspoint.com/what-is-a-routing-algorithm-in-computer-network) 


[DVR, RIP, IGP, EGP, OSPF, EIGRP](https://www.guru99.com/routing-protocol-types.html)

### Logical Addressing
To uniquely identify each device network layer use logical addressing i.e IP address. The sender & receiver’s IP address are placed in the header of packet

### Internetworking: 
This is the main role of the network layer that it provides the logical connection between different types of networks.

### Fragmentation: 
The fragmentation is a process of breaking the packets into the smallest individual data units that travel through different networks.

### Forwording
Forwarding is simply defined as the action applied by each router when a packet arrives at one of its interfaces. When a router receives a packet from one of its attached networks, it needs to forward the packet to another attached network (unicast routing) or to some attached networks


## Services By Network Layer

### Guaranteed delivery: 
guarantees that the packet will arrive at its destination.

### Guaranteed delivery with bounded delay:
packet will be delivered within a specified host-to-host delay bound.

### In-Order packets: 
ensures that the packet arrives at the destination in the order in which they are sent.

### Guaranteed max jitter: 
ensures that the amount of time taken between two successive transmissions at the sender is equal to the time between their receipt at the destination.

### Security services: 
The network layer provides security by using a session key between the source and destination host. The network layer in the source host encrypts the payloads of datagrams being sent to the destination host. The network layer in the destination host would then decrypt the payload. In such a way, the network layer maintains the data integrity and source authentication services.

___Device works on Network Layer: Router___

# Transport Layer


* Heart of OSI :blush:
* Data in transport layer referred as Segment.
* Responsible for end to end delevery of complete message
* at sender side take formated data from upper layer and perform Segmentation
* Adds Port no to to header & forword to network layer
* implement flow and error control to ensure proper data transmission.
* At receiver’s side Transport Layer reads the port number from its header and forwards the Data which it has received to the respective application. It also performs sequencing and reassembling of the segmented data.
  
## Functions of Transport Layer

### Segmentation & Reassembly:
Take Message from session Layer and breaks into segment. add header to segments. and at reciver side reassemble theese segments.

### Service Point Addressing:
To delever message to correct process transport layer adds port no(Or Service Point Address) to header

### Connection Control: 
It includes 2 types:

Connectionless Transport Layer : Each segment is considered as an independent packet and delivered to the transport layer at the destination machine.

Connection Oriented Transport Layer : Before delivering packets, connection is made with transport layer at the destination machine.

### Flow Control: 
In this layer, flow control is performed end to end.

### Error Control: 
Error Control is performed end to end in this layer to ensure that the complete message arrives at the receiving transport layer without any error. Error Correction is done through retransmission

## Services by Transport Layer:
 
### Connection Oriented Service: 
It is a three-phase process which include
– Connection Establishment
– Data Transfer
– Termination / disconnection
In this type of transmission, the receiving device sends an acknowledgement, back to the source after a packet or group of packet is received. This type of transmission is reliable and secure.

### Connection less service: 
It is a one-phase process and includes Data Transfer. In this type of transmission, the receiver does not acknowledge receipt of a packet. This approach allows for much faster communication between devices. Connection-oriented service is more reliable than connectionless Service.


## What is Port Numer:
* Port number is the part of the addressing information used to identify the senders and receivers of messages in computer networking.  
* server identify the process by port no and send message to that process
* diffrant protocol has diffrant set of port no's

* Ports are represented by 16-bit numbers. 
* 0 to 1023 are restricted port numbers are as they are used by well-known protocol services. 
* 1024 to 49151 are registered port numbers means it can be registered to specific protocols by software corporations 
*  49152 to 65536 are used as private ports means they can be used by anybody.

[Why Error & flow control done at Trnsport layer while it is already in done DLL](https://gateoverflow.in/170085/error-control-layers-computer-networks-transport-layer-layers)

[What is Socket](https://www.tutorialspoint.com/unix_sockets/what_is_socket.htm)

[TCP & UDP](https://www.javatpoint.com/computer-network-transport-layer-protocols)


