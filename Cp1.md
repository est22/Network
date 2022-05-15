#  Chapter 1. Computer Networks and the Internet


 **Contents**
  - [1.1 What Is the Internet?](#11-what-is-the-internet)
    - [1.1.1 A Nuts-and-Bolts Description](#111-a-nuts-and-bolts-description)
    - [1.1.2 A Services Description](#112-a-services-description)
    - [1.1.3 What Is a Protocol?](#113-what-is-a-protocol)
  - [1.2 The Network Edge](#12-the-network-edge)
    - [1.2.1 Access Networks](#121-access-networks)
    - [1.2.2 Physical Media](#122-physical-media)
  - [1.3 The Network Core](#13-the-network-core)
    - [1.3.1 Packet Switching](#131-packet-switching)
    - [1.3.2 Circuit Switching](#132-circuit-switching)
    - [1.3.3 A Network of Networks](#133-a-network-of-networks)
  - [1.4 Delay, Loss, and Throughput in Packet-Switched Networks](#14-delay-loss-and-throughput-in-packet-switched-networks)
    - [1.4.1 Overview of Delay in Packet-Switched Networks](#141-overview-of-delay-in-packet-switched-networks)
    - [1.4.2 Queuing Delay and Packet Loss](#142-queuing-delay-and-packet-loss)
    - [1.4.3 End-to-End Delay](#143-end-to-end-delay)
    - [1.4.4 Throughput in Computer Networks](#144-throughput-in-computer-networks)
  - [1.5 Protocol Layers and Their Service Models](#15-protocol-layers-and-their-service-models)
    - [1.5.1 Layered Architecture](#151-layered-architecture)
    - [1.5.2 Encapsulation](#152-encapsulation)
  - [1.6 Networks Under Attack](#16-networks-under-attack)
  - [1.7 History of Computer Networking and the Internet](#17-history-of-computer-networking-and-the-internet)
    - [1.7.1 The Development of Packet Switching: 1961–1972](#171-the-development-of-packet-switching-19611972)
    - [1.7.2 Proprietary Networks and Internetworking: 1972–1980](#172-proprietary-networks-and-internetworking-19721980)
    - [1.7.3 A Proliferation of Networks: 1980–1990](#173-a-proliferation-of-networks-19801990)
    - [1.7.4 The Internet Explosion: The 1990s](#174-the-internet-explosion-the-1990s)
    - [1.7.5 The New Millennium](#175-the-new-millennium)
  - [1.8 Summary](#18-summary)

***
> ## 1.1 What Is the Internet? 
>### 1.1.1 A Nuts-and-Bolts Description 
nontraditional Internet “things” -> In Internet jargon, all of these devices are called **hosts** or **end systems**.

![image](https://user-images.githubusercontent.com/60957334/168458453-3789f0bb-fa9d-4e3f-8dfe-fbe6abd2a7c9.png)


End systems are connected together by a network of **communication links** and **packet switches**. (many types of communication links, which are made up of
different types of physical media, including coaxial cable, copper wire, optical fiber, and radio spectrum.)

Different links can transmit data at different rates, with the **transmission rate** of a link measured in bits/second.


> Packet and Packet-switch


**packets** : the jargon of computer networks; The resulting packages of information (sent thru the network to the destination and the end system, and reassembled into the original data)

**packet switch**: takes a *packet* arriving on one of its incoming *communication links* and forwards that packet on one of its outgoing communication links. Packet switches come in many shapes and flavors, but the two most prominent types in today’s Internet are **routers** and **link-layer switches**. 

> ISP (Internet Service Providers)
>
End systems access the Internet through **Internet Service Providers (ISPs**) 

*residential ISPs (local cable or telephone companies); corporate ISPs; university ISPs(public places);  cellular data ISPs*

> what ISP does? - network/internet access

Each ISP is in itself a network of packet switches and communication links.

ISPs provide a variety of types of **network access** to the end systems, including residential broadband access such as cable modem or DSL, high-speed local area network access, and mobile wireless access. ISPs also provide ­**Internet access** to content providers, connecting Web sites and video servers directly to the Internet. 


> TCP/IP (Transmission Control Protocol / Internet Protocol)

The Internet’s principal protocols are collectively known as **TCP/IP**.

End systems, packet switches, and other pieces of the Internet run **protocols** that control the sending and receiving of information within the Internet. The **Transmission Control Protocol (TCP)** and the **Internet Protocol (IP)** are two of the most important protocols in the Internet.



>### 1.1.2 A Services Description 
Internet =  *an infrastructure that provides
services to applications*.


-> **distributed applications**, since they involve multiple end systems that exchange data with each other

> how does one program running instruct the Internet to deliver data to another program(end system to another end system)? - socket

End systems attached to the Internet provide a **socket interface** that specifies how a program running on one end system asks the Internet infrastructure to deliver data to a specific destination program running on another end system. 


>### 1.1.3 What Is a Protocol?
 in our human protocol, there are specific messages we send, and specific actions.


>A **protocol** defines the format and the order of messages exchanged between two or more communicating entities, as well as the actions taken on the transmission and/or receipt of a message or other event.

Different protocols are used to accomplish different communication tasks. As you read through this book, you will learn that some protocols are simple and straightforward, while others are complex and intellectually deep. Mastering the field of computer networking is equivalent to understanding the what, why, and how of networking protocols.
***
>## 1.2 The Network Edge 
>### 1.2.1 Access Networks 
Home Access: DSL, Cable, FTTH, Dial-Up, and Satellite

Today, the two most prevalent types of broadband residential access are **digital subscriber line (DSL)** and cable. 
![df](https://user-images.githubusercontent.com/60957334/168459120-9e9da3a7-dd21-421a-9809-6cd8fdf7a1d5.png)

>### 1.2.2 Physical Media 
***
>## 1.3 The Network Core 
>### 1.3.1 Packet Switching

In a network application, end systems exchange **messages** with each other. the source breaks long msgs into smaller chunks of data known as **packets**. 

Between source and destination, each packet travels through communication links and **packet switches** (for which there are two predominant types, routers and link-layer switches). 

Packets are transmitted over each communication link at a rate equal to the full transmission rate of the link. So, if a source end system or a packet switch is sending a packet of *L* bits over a link with transmission rate *R* bits/sec, then the time to transmit the packet is *L / R* seconds.

> Store-and-Forward Transmission
>
Most packet switches use store-and-forward transmission at the inputs to the links. Store-and-forward transmission means that ***the packet switch must receive the entire packet before it can begin to transmit*** the first bit of the packet onto the outbound link. 
![df](https://user-images.githubusercontent.com/60957334/168459361-a6f1fb8c-af12-4fe5-b0e4-fbb03aec162b.png)


>Queuing Delays and Packet Loss

![df](https://user-images.githubusercontent.com/60957334/168459433-ac88e7ae-7606-4674-98a0-3291a1b87b0b.png)
Each packet switch has multiple links attached to it. For each attached link, the packet switch has an **output buffer** (also called an output queue), which stores packets that the router is about to send into that link. ***The output buffers play a key role in packet switching.*** If an arriving packet needs to be transmitted onto a link but finds the link busy with the transmission of another packet, the arriving packet must wait in the output buffer. Thus, in addition to the store-and-forward delays, packets suffer output buffer queuing delays. These delays are variable and depend on the level of congestion in the network.
Since *the amount of buffer space is finite*, an arriving packet may find that the buffer is completely full with other packets waiting for transmission. In this case, ***packet loss*** will occur—either the arriving packet or one of the already-queued packets will be dropped.

>Forwarding Tables and Routing Protocols

But how does the router determine which link it should forward the packet onto? 

 When a packet arrives at a router in the network, the router examines a portion of the packet’s destination address and forwards the packet to an adjacent router. More specifically, each router has a forwarding table that maps destination addresses (or portions of the destination addresses) to that router’s outbound links. When a packet arrives at a router, the router examines the address and searches its forwarding table, using this destination address, to find the appropriate outbound link. The router then directs the packet to this outbound link.

>### 1.3.2 Circuit Switching 

There are two fundamental approaches to moving data through a network of links and switches: **circuit switching** and **packet switching**. 


> Packet switching vs Circuit switching - resto with walk-in vs resto with a booking call

Generally speaking, people who do not like to hassle with ­restaurant reservations prefer packet switching to circuit switching.

In circuit-switched networks, the resources needed along a path (buffers, link transmission rate) to provide for communication between the end systems are reserved for the duration of the communication
session between the end systems. In packet-switched networks, these resources are not reserved; a session’s messages use the resources on demand and, as a consequence, may have to wait (that is,
queue) for access to a communication link.

![s](https://user-images.githubusercontent.com/60957334/168459607-25418a41-e5ff-42df-badb-3f219c0ec8e1.png)

Traditional telephone networks are examples of circuit-switched networks. In the jargon of telephony, this
connection is called a circuit.

>### 1.3.3 A Network of Networks 

Since the access ISP pays the global transit ISP, the access ISP is said to be a **customer** and the global transit ISP is said to be a **provider**.
![d](https://user-images.githubusercontent.com/60957334/168459983-0cb9ed9a-898d-4850-8eb9-bb436bf37ad4.png)


*** 
>## 1.4 Delay, Loss, and Throughput in Packet-Switched Networks 
>### 1.4.1 Overview of Delay in Packet-Switched Networks

The most important of these delays are the **nodal processing delay, queuing
delay, transmission delay,** and **propagation delay**; together, these delays accumulate to give a **total nodal delay**. 



>### 1.4.2 Queuing Delay and Packet Loss 
>> Queuing Delay

Unlike the other three delays (namely, dproc, dtrans, and dprop), the queuing delay can vary from packet to packet.

>When is the queuing delay large and when is it insignificant? 

The answer to this question depends on the rate at which traffic arrives at the queue, the transmission rate of the link, and the nature of the arriving traffic, that is, whether the traffic arrives periodically or arrives in bursts. 

>> Packet Loss

Because the queue capacity is finite, packet delays do not really approach infinity as the traffic intensity approaches 1. Instead, a packet can arrive to find a full queue. With **no place** to store such a packet, a router will **drop** that packet; that is, the packet will be **lost**. 

The fraction of lost packets increases as the traffic intensity increases. Therefore, performance at a node is often measured not only in terms of *delay*, but also in terms of the probability of *packet loss*. As we’ll discuss in the subsequent chapters, a lost packet may be *retransmitted* on an end-to-end basis in order to ensure that all data are eventually transferred from source to destination.

>### 1.4.3 End-to-End Delay
>### 1.4.4 Throughput in Computer Networks

In addition to delay and packet loss, another critical performance measure in computer networks is end- to-end throughput.

![d](https://user-images.githubusercontent.com/60957334/168460187-d672a985-c4ff-458e-9591-30893eb75bb8.png)

Thus, for this simple two-link network, the throughput is min{Rc, Rs}, that is, it is the transmission rate of the **bottleneck** **link**.

![sdf](https://user-images.githubusercontent.com/60957334/168460217-ede024c9-1bd8-42ae-8936-f77aee13eb1e.png)

***
>## 1.5 Protocol Layers and Their Service Models
>### 1.5.1 Layered Architecture 
![sdf](https://user-images.githubusercontent.com/60957334/168460243-49df3db9-9973-4d05-bfea-78b9cb6d880d.png)
![sdf](https://user-images.githubusercontent.com/60957334/168460247-ca8022d7-082e-422a-8efb-d2e2ea84dad9.png)

A layered architecture allows us to discuss a well-defined, specific part of a large and complex system. This simplification itself is of considerable value by providing modularity, making it much easier to change the implementation of the service provided by the layer

> Protocol Layering

 We are again interested in the **services** that a layer offers to the layer above—the so-called **service model** of a layer. 

A protocol layer can be implemented in software, in hardware, or in a combination of the two. Application-layer protocols—such as HTTP and SMTP—are almost always implemented in software in the end systems; so are transport-layer protocols. The network layer is often a mixed implementation of hardware and software. Also note that just as the functions in the layered airline architecture were distributed among the various airports and flight control centers that
make up the system, so too is a layer *n* protocol *distributed* among the end systems, packet switches, and other components that make up the network.

![Network 7 Layers](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FcgJ1bs%2FbtruwIivAHg%2Fkh2MVLn1zIFy0oOKdjeOjK%2Fimg.jpg)

![sdf](https://user-images.githubusercontent.com/60957334/168460333-d8d08e10-b93c-43e0-af33-2a5099ea1586.png)


> Application Layer

* HTTP/SMTP/FTP protocol

An application-layer protocol is distributed over multiple end systems, with the application in one end system using the protocol to exchange packets of information with the application in another end system. We’ll refer to this packet of information at the application layer as a **message**.


> Transport Layer

* TCP/UDP protocol

The Internet’s transport layer transports application-layer messages between application endpoints.

TCP also breaks long messages into shorter ­segments and provides a congestion-control mechanism, so that a source throttles its transmission rate when the network is congested. 

The UDP protocol provides a connectionless service to its applications. This is a no-frills service that provides no reliability, no flow control, and no congestion control. In this book, we’ll refer to a transport-layer packet as a **segment**.


> Network Layer

* IP protocol (routing protocol)
  
The Internet’s network layer is responsible for moving network-layer packets known as **datagrams** from one host to another.  The network layer provides the service of delivering the segment to the transport layer in the destination host.


> Link Layer

* Ethernet, WiFi, and the cable access network’s DOCSIS protocol
  
In particular, at each node, the network layer passes the datagram down to the link layer, which delivers the datagram to the next node along the route. At this next node, the link layer passes the datagram up to the network layer.

In this book, we’ll refer to the link-layer packets as **frames**.


> Physical Layer

* The protocols in this layer are again link dependent and further depend on the actual transmission
medium of the link (for example, twisted-pair copper wire, single-mode fiber optics). 


the job of the physical layer is to move the *individual bits* within the frame from one node to the next.


> The OSI(Open Systems
Interconnection) Model 
 the International Organization for Standardization (ISO) proposed that computer networks be organized around seven layers, called the Open Systems
Interconnection (OSI) model **[ISO 2016]**. 

in fact, the inventors of the original OSI model probably did not have the Internet in mind when creating it.


Thus, let’s consider the two additional layers present in the OSI reference model—*the presentation layer and the session layer*. The role of the presentation layer is to provide services that allow communicating applications to interpret the meaning of data exchanged. These services include data compression and data encryption (which are self-explanatory) as well as data description (which frees the applications from having to worry about the internal format in which data are represented/stored—formats that may differ from one computer to another). The session layer provides for delimiting and synchronization of data exchange, including the means to build a checkpointing and recovery scheme.

>### 1.5.2 Encapsulation 

![d](https://user-images.githubusercontent.com/60957334/168460400-96722a68-a579-4cd7-b314-b4689a8f8415.png)
***
## 1.6 Networks Under Attack
>***
>## 1.7 History of Computer Networking and the Internet 
>### 1.7.1 The Development of Packet Switching: 1961–1972
>### 1.7.2 Proprietary Networks and Internetworking: 1972–1980 
>### 1.7.3 A Proliferation of Networks: 1980–1990 
>### 1.7.4 The Internet Explosion: The 1990s
>### 1.7.5 The New Millennium 
***
>## 1.8 Summary


host / end system : 네트워크에 연결된 장치

communication link, packet switch 의 네트워크로 연결된다.

각각의 링크들은 다양한 전송률(transmission rate, 링크 대역폭)을 이용하여 데이터를 전송하며 전송률은 초당 비트 수를 의미하는 bps (bit per second) 단위를 사용한다.

한 end system -> another end system으로 보낼 data를 가지고 있을 때, 송신 end system은 그 데이터를 segment로 나누고 각 segment에 header를 붙인다. 이렇게 만들어진 정보 패키지는 컴퓨터 네트워크에서 packet이라고 불린다. packet 은 목적지 end system으로 네트워크를 통해 보내지고 목적직에서 원래의 데이터로 다시 조립된다.

packet switch는 다양한 형태와 특징이 있는데, 가장 널리 사용되는 종류로는 router, link-layer switch가 있다. 
router는 네트워크 코어에서 사용되며, link-layer switch는 보통 액세스 네트워크에서 사용된다.

패킷이 sender end system -> receiving end system에 도달하는 동안 거쳐 온 일련의 통신 링크와 패킷 스위치들을 네트워크상의 경로(route/path)라고 한다.

패킷은 트럭과 유사하고, 통신 링크는 도로, 패킷 스위치는 교차로, end system은 빌딩과 유사하다. 트럭이 운송 네트워크를 통해 경로를 따르는것처럼, 패킷은 컴퓨터 네트워크를 통한 경로를 따른다.

end system은 ISP(Internet Service Provider)를 통해서 인터넷에 접속하는데, ISP의 종류는 다양하고 다양한 네트워크 접속을 제공한다. 또한 웹사이트와 비디오 서버를 인터넷에 직접 연결하도록 CP(Content Provider)에게 인터넷 접속을 제공한다. 인터넷은 enad system을 서로 연결하는 것이므로 ISP들도 서로 연결되어야한다. 이들 하위 계층 ISP는 L3 communications, AT&T, Sprint, NTT와 같은 국가 그리고 국제 상위 계층 ISP를 통해 서로 연결된다. 상위 계층 ISP는 광 링크로 연결된 고속 라우터로 구성된다. 상위 계츠이든 하위 계층이던 각 ISP 네트워크는 따로 관리되고, IP protocol을 수행하며 naming과 주소배정 방식을 따른다.

end system, packet switch, 인터넷의 다른 구성요소는 인터넷에서 정보. 송수신을 제어하는 여러 프로토콜을 수행한다. 특히 TCP(Transmission Control Protocol)와 IP(Internet Protocol)는 인터넷에서 가장 중요한 프로토콜이다. IP 프로토콜은 라우터와 종단 시스템 사이에서 송수신되는 패킷 포맷을 기술한다. 이러한 인터넷의 프로토콜을 통칭하여 TCP/IP라고 한다. 

인터넷 표준(Internet Standard)은 IETF(Internet Engineering Task Force)에서 개발하며, IETF 표준 문서를 RFCs(Requests For Comments)라고 한다.

소켓이란?
An interface between application and N/W

the application creates a socket
The socket type dictates the style of communication (reliable vs best effort, connection-oriented vs connectionless)
![Two essential types of sockets](https://user-images.githubusercontent.com/60957334/168459149-6aa73c98-6cdb-4fb5-aac8-ed1b78cc01dd.png)




1.1.3 프로토콜이란 무엇인가?

프로토콜은 컴퓨터 사이에 연결된 선로상의 비트 흐름을 제어한다. 프로토콜은 둘 이상의 통신 개체 간에 교환되는 메시지 포맷과 순서뿐 아니라, 메시지의 송수신과 다른 이벤트에 따른 흐름들을 정의한다.

1.2 네트워크의 가장자리

host = end system.
때로는 client / server로 구분된다. 비공식적으로 클라이언트는 데탑, 모바일, 스마트폰 등을 의미한다.
오늘날 검색결과, 메일, 웹페이지, 비디오를 수신하는 대부분의 서버들은 커다란 데이터 센터 내에 있다.

1.3 네트워크 코어

네트워크 응용에서 종단 시스템들은 서로 메시지를 교환한다. 송신 시스템은 긴 매시지를 packet이라고 하는 작은 데이터 덩어리로 분할한다. 송신 측과 수신 측 사이에서 각 패킷은 통신 링크와 packet switch(router와 link-layer switch)를 거치게 된다. 패킷은 링크의 최대 전송속도와 같은 속도로 각각의 통신 링크상에서 전송된다. 따라서 송신 종단 시스템 혹은 패킷 스위치가 R bit/s의 속도로 링크상에서 L bits의 패킷을 송신한다면,그 패킷을 전송하는 데 걸리는 시간은 L/R초이다.

store-and-forward transmission

대부분의 패킷 스위치는 저장-후-전달 전송 방식을 이용한다. 
