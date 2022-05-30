9The _[[A Tour of Computer Systems#^6f42cd|hello]]_ program has much more to it than meets the eye. To understand what happens to it when we run it, we first need to look into the hardware organization of a typical system. Here's a complicated diagram showing how it all looks like graphically:

![Hardware organization of a typical system](typical-hwd-org.png)

***NOTE***: The above image is modeled after the family of _[[Bibliography#^bec183|Intel Pentium systems]]_, but all systems have a similar look and feel.

There are some key terms that these sort of systems use for referring to different components and/or processes, let's look at some of them and their descritpions:

#### Buses
Well, looking at the term as is, one can probably _guess_ (maybe) that it has something to do with transportation of something, and they'd be right.

Running throughout the system is a collection of electrical conduits called _buses_ that carry bytes of information back and forth between the components. Buses are typically designed to transfer fixed-sized chunks of bytes known as _words_. The number of bytes in a word ( the _word size_ ) is a fundamental system parameter that varies across systems. 32-bit machines have a word size of _4 bytes_ and 64-bit machines have a word size of _8 bytes_. 

Here's a table mapping word types to bytes:

|  Word Type  |  Size   |
|:-----------:|:-------:|
|    Byte     | 1 byte  |
|    Word     | 2 bytes |
| Double Word | 4 bytes |
|  Quad-Word  | 8 bytes |

#### I/O Devices
Input/output (I/O) devices are the system's connection to the external world. Our example system has 4 I/O devices; a keyboard and a mouse for user input, a display for user output, and a disk drive for data storage. Initially the ` hello ` program resides on the disk.

==Each I/O device is connected to the _I/O bus_ by either a _controller_ or an _adapter_==. The distinction between the two is, mainly, how they package data. _**Controllers** are chip sets in the device itself or on the system's main printed circuit board (often called the motherboard)_. _An **Adapter** is a card that plugs into a slot on the motherboard._ Regardless, the purpose of these two is the same, that is, to transfer information back and forth between the I/O bus and an I/O device.

#### Main Memory
The _main memory_ is a **temporary storage device** that holds both a program and the data it manipulates while the processor is executing the program.

Physically, the memory consists of _[[Bibliography#^16762b|dynamic random access memory (DRAM)]]_ chips. Logically, memory is organized as a linear array of bytes, each with it's own unique address (array index) starting at zero. In general, each of the machine instructions that constitute a program can consist of a variable number of bytes. The size of data items corresponding to values in a C program can vary according to the type of said value.

#### Processor

The _central processing unit_ (CPU), or simply _processor_ 