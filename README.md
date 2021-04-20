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

![picture alt](images/datalink.jfif "Title is optional")

## Functions of Data Link Layer

### Framing
Its convert data packet into data frame and add meaningfull header to ensure transmission of data to meaningfull reciever

### Physical Addressing 
Adds physical address of sender and reciever to the headder of each frame

### Error Control
bits added at end to detect error. Diffrent Error Correction & Detection algo used to control Error. and retransmit damaged packet

[Error corrections & Detection: see only parity checking, CRC, LRC & Hamming code](https://www.electronicshub.org/error-correction-and-detection-codes/#:~:text=This%20code%20uses%20a%20number,any%20number%20of%20data%20bits.)

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

[Routing Algorithm](https://www.tutorialspoint.com/what-is-a-routing-algorithm-in-computer-network#:~:text=A%20routing%20algorithm%20is%20a,in%20directing%20Internet%20traffic%20efficiently.&text=Routing%20algorithm%20mathematically%20computes%20the,packet%20can%20be%20routed%20through) 

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