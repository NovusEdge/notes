The method to structure an overview of computer networks is as follows:

After introducing some basic technology and concepts, it's best to examine basic hardware and software components of the network, beginning at the [[#The Network Edge|network edge]] working our way up to the [[#The Network Core|network core]]. 

The next thing to do will be examining the more abstract concepts of networking like loss and throughput of data, as well as introduce some key-architectural principles in computer networking, namely, _protocol layering and service models_. 

There's also a section of the material that will analyze and study the vulnerability of networks and different types of network attacks.

# What Is The Internet?
There are several ways to describe the internet. First, we can describe the internet in the terms of hardware and software components. Second, we can describe the internet in terms of the internetworking architecture and infrastructure that provides services to distributed applications.

## The Nuts-and-Bolts Description
The Internet is a computer network that interconnects hundreds of millions of com-  puting devices throughout the world. Not too long ago, these computing devices were  primarily traditional desktop PCs, Linux workstations, and so-called servers that store  and transmit information such as Web pages and e-mail messages. Increasingly, however, nontraditional Internet end systems such as laptops, smartphones, tablets, TVs, gaming consoles, Web cams, automobiles, environmental sensing devices, picture frames, and home electrical and security systems are being connected to the  Internet. Indeed, the term computer network is beginning to sound a bit dated, given the many nontraditional devices that are being hooked up to the Internet.

In Internet jargon, all of these devices are called **hosts** or **end systems**. In general though, hosts tend to be giant servers ("big computer systems") wheras clients usually tend to be smaller device systems, like a PC or cellular devices.

End systems are connected together by a network of **communication links** and **packet switches**. There are several types of communication links, which are made up of different types of physical media, including _coaxial cables_, _copper wire_, _optical fiber_ and _radio spectrum_. 

Different links can transmit data at different rates, with the **transmission rate** of a link measured in _bits/second_

***Definition***: The rate at which information flows through a given medium (measured in bits) per unit time, is called **transmission rate**. The standard unit of transmission rate is _bits/second_.

When one end system has data to send to another end system, the sending end system segments the data into smaller chunks and adds _header bytes_ to each segment. The resulting chunks of information are known as **packets**, are then sent to their destination end system through the network, where they are reassembled into the original data.

A packet switch takes a packet arriving on one of its incoming communication links and forwards that packet on one of its outgoing communication links. They come in many variations, but the 2 most prominent ones are: **routers** and **link-layer switches**. Link-layer switches are typically used in access networks, while routers are typically used in the network core. 

***Definition***: The sequence of comm. links and packet switches traversed by a packet from the source to destination is known as a **route** or a **path** through the network.

End systems access the Internet through **Internet Service Providers (ISPs)**. Each ISP is in itself a network of packet switches and communication links. 

The Internet is all about connecting end systems to each other, so the ISPs that provide access to end systems must also be interconnected. These lower-tier ISPs are interconnected through national and international upper-tier ISPs such as Level 3 Communications, AT&T, Sprint, and NTT. An upper-tier ISP consists of high-speed routers interconnected with high-speed  fiber-optic links. Each ISP network, whether upper-tier or lower-tier, is managed independently, runs the IP protocol, and conform to certain naming and address conventions.

End systems, packet switches, and other pieces of the Internet run **protocols** that control the sending and receiving of information within the Internet. The **Transmission Control Protocol(TCP)** and the **Internet Protocol (IP)** are two of the most important protocols in the Internet. 

==The **IP** protocol specifies the format of the packets that are sent and received among routers and end systems.== _The Internet's principle protocols are collectively known as **TCP/IP**_

**Internet standards** are developed by the [Internet Engineering Task Force (IETF)](https://www.ietf.org/). The IETF standards are documents called **[requests for comments(RFCs)](https://www.ietf.org/standards/rfcs/)**. RFCs tend to be quite technical and detailed, and define protocols like TCP, IP, HTTP, SMTP etc. _Other bodies also define standards for network components, most notably for network links. The IEEE 802 LAN/MAN Standards Committee [IEEE 802 2012](https://en.wikipedia.org/wiki/IEEE_802), for example, specifies the Ethernet and wireless WiFi standards._ 

## A Services Description
This approach describes the Internet as _an infrastructure that provides services to applications._ These applications include e-mail, web surfing, social networks, instant messaging, Voice-over-IP(VoIP), video streaming, peer-to-peer (P2P) file sharing, remote login, and much more. These applications are said to be **distributed applications**, since they involve multiple end systems that exchange data with each other. ==Importantly, Internet applications run on end systems, they do not run on the packet switches in the network core.== Although packet switches facilitate the exchange of data among end systems, they are not concerned with the application that is the source or sink of data. 

Now, we get to an important question: _==How does one program running on one end-system instruct the Internet to deliver data to another program running on another end system?==_

End systems attached to the internet provide an **Application Programming Interface (API)** that specifies how a program running on one end-system asks the Internet infrastructure to deliver data to a specific destination program running on another end-system.


