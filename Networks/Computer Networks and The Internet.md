The method to structure an overview of computer networks is as follows:

After introducing some basic technology and concepts, it's best to examine basic hardware and software components of the network, beginning at the [[#The Network Edge|network edge]] working our way up to the [[#The Network Core|network core]]. 

The next thing to do will be examining the more abstract concepts of networking like loss and throughput of data, as well as introduce some key-architectural principles in computer networking, namely, _protocol layering and service models_. 

There's also a section of the material that will analyze and study the vulnerability of networks and different types of network attacks.

# What Is The Internet?
There are several ways to describe the internet. First, we can describe the internet in the terms of hardware and software components. Second, we can describe the internet in terms of the internetworking architecture and infrastructure that provides services to distributed applications.

## The Nuts-and-Bolts Description
The Internet is a computer network that interconnects hundreds of millions of com-  puting devices throughout the world. Not too long ago, these computing devices were  primarily traditional desktop PCs, Linux workstations, and so-called servers that store  and transmit information such as Web pages and e-mail messages. Increasingly, however, nontraditional Internet end systems such as laptops, smartphones, tablets, TVs, gaming consoles, Web cams, automobiles, environmental sensing devices, picture frames, and home electrical and security systems are being connected to the  Internet. Indeed, the term computer network is beginning to sound a bit dated, given the many nontraditional devices that are being hooked up to the Internet.

In Internet jargon, all of these devices are called **hosts** or **end systems**. In general though, hosts tend to be giant servers ("big computer systems") whereas clients usually tend to be smaller device systems, like a PC or cellular devices.

End systems are connected together by a network of **communication links** and **packet switches**. There are several types of communication links, which are made up of different types of physical media, including _coaxial cables_, _copper wire_, _optical fiber_ and _radio spectrum_. 

Different links can transmit data at different rates, with the **transmission rate** of a link measured in _bits/second_

***Definition***: The rate at which information flows through a given medium (measured in bits) per unit time, is called **transmission rate**. The standard unit of transmission rate is _bits/second_.

When one end system has data to send to another end system, the sending end system segments the data into smaller chunks and adds _header bytes_ to each segment. The resulting chunks of information are known as **[[Bibliography#^46bd9a|packets]]**, are then sent to their destination end system through the network, where they are reassembled into the original data.

A packet switch takes a packet arriving on one of its incoming communication links and forwards that packet on one of its outgoing communication links. They come in many variations, but the 2 most prominent ones are: **routers** and **link-layer switches**. Link-layer switches are typically used in access networks, while routers are typically used in the network core. 

***Definition***: The sequence of comm. links and packet switches traversed by a packet from the source to destination is known as a **route** or a **path** through the network.

End systems access the Internet through **Internet Service Providers (ISPs)**. Each ISP is in itself a network of packet switches and communication links.  ^de7bfc

The Internet is all about connecting end systems to each other, so the ISPs that provide access to end systems must also be interconnected. These lower-tier ISPs are interconnected through national and international upper-tier ISPs such as Level 3 Communications, AT&T, Sprint, and NTT. An upper-tier ISP consists of high-speed routers interconnected with high-speed  fiber-optic links. Each ISP network, whether upper-tier or lower-tier, is managed independently, runs the IP protocol, and conform to certain naming and address conventions.

End systems, packet switches, and other pieces of the Internet run **protocols** that control the sending and receiving of information within the Internet. The **Transmission Control Protocol(TCP)** and the **Internet Protocol (IP)** are two of the most important protocols in the Internet. 

==The **IP** protocol specifies the format of the packets that are sent and received among routers and end systems.== _The Internet's principle protocols are collectively known as **TCP/IP**_

**Internet standards** are developed by the [Internet Engineering Task Force (IETF)](https://www.ietf.org/). The IETF standards are documents called **[requests for comments(RFCs)](https://www.ietf.org/standards/rfcs/)**. RFCs tend to be quite technical and detailed, and define protocols like TCP, IP, HTTP, SMTP etc. _Other bodies also define standards for network components, most notably for network links. The IEEE 802 LAN/MAN Standards Committee [IEEE 802 2012](https://en.wikipedia.org/wiki/IEEE_802), for example, specifies the Ethernet and wireless WiFi standards._ 

## A Services Description
This approach describes the Internet as _an infrastructure that provides services to applications._ These applications include e-mail, web surfing, social networks, instant messaging, Voice-over-IP(VoIP), video streaming, peer-to-peer (P2P) file sharing, remote login, and much more. These applications are said to be **distributed applications**, since they involve multiple end systems that exchange data with each other. ==Importantly, Internet applications run on end systems, they do not run on the packet switches in the network core.== Although packet switches facilitate the exchange of data among end systems, they are not concerned with the application that is the source or sink of data. 

Now, we get to an important question: _==How does one program running on one end-system instruct the Internet to deliver data to another program running on another end system?==_

End systems attached to the internet provide an **Application Programming Interface (API)** that specifies how a program running on one end-system asks the Internet infrastructure to deliver data to a specific destination program running on another end-system.

In simpler words, the Internet API is a set of rules that the sending program must follow so that the Internet can deliver the data to the destination program.
Even with all these examples and descriptions of the internet, there are still several questions that arise:

- _What are packet switching and TCP/IP?_
- _What are routers?_
- _What kinds of communication links are present in the Internet?_
- _What is a distributed application?_
- _How is a device really attached to the Internet?_

***Remark***: Checkout [[An Overview of Protocols]] for, well, an overview of what protocols are about. The reason being that the knowledge of protocols will come in handy when discussing the next topic. :)

# The Network Edge
Until now, the common terminology used for systems connected to a network was: _end-systems_. While this is true, this term is a bit lacking, since it does not tell us much. A better term to use for these end-systems is: _hosts_, since they host (i.e. _run_) application programs such as web-browsers, web-servers, e-mail client/server programs and a whole lot more.

Hosts are sometimes (well it's grown more common as networks have grown) further into 2 categories, namely:
- _Servers_
- _Clients_

Informally, clients tend to be the users, i.e. the ones that make use of services, the _consumers_. On the other hand, servers tend to be the _providers_, i.e. the ones that provide the services that clients consume/make use of.


## Access Networks
The access network is _the network that physically connects an end system to the first router (edge-router) on a path from the end system to any other distant end system_.


### Home Access: DSL, Cable, FTTH, Dial-Up, and Satellite

Home access networks are exactly what they sound like; they connect households to the broader Internet. Currently, the two most prevalent types of broadband residential access are **[[Bibliography#^61ea71|Digital Subscriber Line (DSL)]]** and **[[Bibliography#^8a8f18|Cable]]**. 

A residence typically obtains DSL internet access from the same local telephone company (telco) that provides its wired local phone access. Thus when DSL is used, a customer's telco is also it's [[#^de7bfc|ISP]]. Each customer's _DSL modem_ uses the existing telephone line to exchange data with a **Digital Subscriber Line Access Multiplexer (DSLAM)** located in the telco's local _central office (CO)_

The home's DSL modem takes digital data and translates it into high frequency tones for transmission over telephone lines to the CO; the analog signals from many such home networks are translated back to digital format by the DSLAM.

The residential telephone line carries both data and traditional telephone signals simultaneously, which are encoded at different frequencies:  
- A _high-speed downstream channel_, in the `50 kHz to 1 MHz` band .
- A _medium-speed upstream channel_, in the `4 kHz to 50 kHz` band.
- An _ordinary two-way telephone channel_, in the `0 to 4 kHz` band.

This approach makes the single DSL link appear as if there were three separate links, so that a telephone call and an Internet connection can share the DSL link at the same time. (all thanks to a technique called **[[Frequency-Division Multiplexing]]**).

