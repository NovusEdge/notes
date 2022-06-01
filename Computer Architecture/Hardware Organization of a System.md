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

The _central processing unit_ (CPU), or simply _processor_ , is the engine that interprets (or executes) instructions stored in the main memory. ==At it's core is a word-sized register (storage device) called the [[Bibliography#^50b001|program counter (PC)]]==. At any point in time, the PC points at (contains the address of) some machine-language instruction in main-memory. The PC is commonly called: _instruction pointer (IP)_ in Intel x86 and ltanium microprocessors, and sometimes called the _instruction address register (IAR)_. You can read up more about it later in the notes, or on the [[Bibliography#^50b001|wikipedia reference in the bibliography]]. 

A processor _appears_ to operate according to a very simple instruction execution model, defined by its _[[Bibliography#^f9d5ed|instruction set architecture]]_. In this model, instructions execute in strict sequence, and executing a single instruction involves performing a series of steps. The processor reads the instruction from memory pointed at by the PC, interprets the bits of the instruction, performs some simple instruction, which may or may not me contiguous in memory to the instruction that was just executed. Here's a reference to [[Bibliography#^e45081|intel's instruction set architecture]].

There are only a few of these simple operations, and they revolve around main memory, the _register file_, and the _arithmetic/logic unit_ (ALU). The register file is a small storage device that consists of a collection of word-sized registers, each with it's own unique name. The ALU computes new data and address values.  Here are some examples of the simple operations a CPU might carry out:

- ***Load***: Copy a byte or a word from main memory into a register, _overwriting the pervious contents of the register_. 
- ***Store***: Copy a byte or a word from a register to a location in main memory, _overwriting the previous contents of that location_.
- ***Operate***: Copy the contents of two registers to the ALU, perform an arithmetic operation on the two words, and store the result in a register, _overwriting the pervious contents of that register_.
- ***Jump***: Extract a word from the instruction itself and copy that word into the PC, _overwriting the previous value of PC_.

One can distinguish the processor’s instruction set architecture, describing the effect of each machine-code instruction, from its microarchitecture, describing how the processor is actually implemented.

