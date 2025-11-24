## What's the Difference Between SDRAM, DDR and DRAM Memory Chips?
-----

&copy; saikrupas 

There are a wide variety of volatile and non-volatile internal storage units that are utilized in computers today. <mark><u>Dynamic Random Access Memory (DRAM)</u></mark> is among the most often employed architectures due to its cost-effectiveness as compared to <mark><u>Static Random-access Memory (SRAM)</u></mark>.</br>

Let's talk about the major differences between the different types of DRAM including <u>Synchronous Dynamic Access Memory (SDRAM)</u> and the various types of <u>Double Data Rate (DDR) topologies (i.e.: DDR2, DDR3, DDR4)</u>.</br>

**Primary Memory**</br>

+ The computer's main memory that the CPU can access directly for fast read and write operations.</br>
+ Its contents are lost when the power is turned off.</br>
+ Random access memory(RAM), Read-only memory (ROM), and cache memory.</br>
+ It holds the operating system, currently running applications, and the data they are processing.</br>

**Random access memory(RAM)**</br>

+ A specific type of primary memory that allows for both reading and writing of data.</br>
+ Data is lost when the power is off, which is why it's also called temporary or main memory.</br>
+ It is very fast, allowing the CPU to access data quickly.</br>
+ It stores data and instructions that the CPU is actively using to perform tasks.</br>


**Difference between SRAM and DRAM :-**</br>

| SRAM | DRAM |
|:-----:|:-----:|
|static random access momory|Dynamic random access memory|
|Transiostors/flip-flops are used to store information in SRAM.|Capacitors are used to store information in DRAM.|
|It has less storage capacity.|It has large storage capacity.|
|SRAMs are low density devices.|DRAMs are high density devices.|
|SRAMs are used in cache memories.| DRAMs are used in main memories.|
|SRAM is expensive than DRAM.|DRAM is cheaper than SRAM.|
|The power consumption of SRAM is more.|The power consumption of DRAM is less.|
|SRAM's structure is complex than DRAM.|DRAM's structure is simplex than SRAM.|
|SRAM does not need periodic refeshment to maintain data.|DRAM needs periodic refreshment to maintaion the charge in the capacitors for data.|
|SRAM is faster than DRAM.|DRAM is slower than SRAM.|

-----

**What is DRAM?**

+ <mark><u>Dynamic Random Access Memory (DRAM)</u></mark> implements a series of <u>**capacitors**</u> that are meant to store individual bits for Random Access Memory(RAM). </br>
+ RAM is a type of memory that can <mark>access a data element regardless of its position in a sequence</mark>. So, in essence, the time it takes to access any data is constant.</br>
+ An optimal design of access transistors and storage capacitors as well as advancement in semiconductor processes have made DRAM storage the cheapest memory available. </br>
+ As stated earlier <mark>DRAM is most often employed as a computer’s main memory due to its cost-effectiveness</mark> as compared to SRAM counterparts.</br>
+  DRAM technology has gone through some major revisions over the decades to drastically <u>reduce cost-per-bit, increase clock rate, and reduce the overall dimensions of this component</u>. These improvements can be associated with a number of changes including the introduction of the smaller DRAM cell, synchronous DRAM architectures, and finally DDR topologies.</br>

**DRAM Cell Structure**

+ A typical 3-transistor DRAM cell employs the use of access transistors and a storage transistor to switch the input capacitance of the storage transistor ON (bit value 1) and OFF (bit value 0). The array of transistors are tied to read and write columnlines and rowlines that are also known as bitlines and wordlines respectively.</br>

> bitline(columnline) ----> read </br>
> wordline(rowline)  -----> write

+ The components and data lines are arranged in such a way that allows for both write and read operations with a singular storage transistor.</br>
+ For instance, a <u>traditional 3-transistor DRAM cell</u> (from Figure 1(a)) performs a write command by sending voltage to the gate of the M1 access transistor which in turn, charges the gate capacitance of M3. The write line is then driven low and the charge stored in the gate capacitance of M3 slowly dissipates -- <mark>thus the term dynamic.</mark>

<img width="310" height="310" alt="image" src=DRAM_CELL_1.png/></br>

Figure 1(a): 3-transistor DRAM cell </br>

+ But the Current technologies will often <u>employ a 1-transistor/1-capacitor (1T1C) memory cell</u> (from Figure 1(b)) for <u>more densely packed memory chips</u>. The <mark>CMOS gate is tied to the word line while the source is tied to the bit line</mark>.</br> 
+ <mark>A write command is accomplished by turning the gate to the transistor on thereby sending current to the discrete storage capacitor</mark>.</br>
+ <mark>A read is accomplished by sharing the charge stored in the capacitor with the bit line. The architecture requires a rewrite (refresh) after every read operation as the charge sharing destroys the information contained in the DRAM cell</mark>. Typically, this recharge happens every few milliseconds to compensate for charge leaks from the capacitor.</br>

<img width="310" height="310" alt="image" src=DRAM_CELL_2.png/></br>

Figure 1(b): 1-transistor/1-capacitor DRAM cell </br>

**Asynchronous Transfer Mode(ATS) Switching**

+ The real complexity of this technology lies several layers of hierarchy up where an array of thousands of cells need to be tracked and assessed for various operations such as writes, reads, and refreshes. </br>

+ Current DRAM technology utilizes multiplexed addressing where the same address input pins are leveraged for both the row and column addresses, this ultimately<u> saves space and lessens pin count</u>.</br>

+ The operations performed through the use of a <mark>Row Address Strobe (RAS) and a Column Access Strobe (CAS) clock.</mark> The RAS validates that the signal sent to the DRAM is, in fact, a row address while the CAS validates input column addresses. On the falling edge of the RAS, the address present on the DRAM address pins are inputted into the row address latches.</br>

+ On the falling edge of the CAS, the addresses are inputted into the column address latches on its falling edge. In essence, turning on an entire row (in the memory array) allows the information stored on the capacitors to be read (sensed), or, allows the charging/discharging of the storage capacitors for a write. </br>

+ This is accomplished through the use of a number of <mark> peripheral circuits including row/column latches, row address buffers, row/column decoders, wordline drivers, and bitline sense amplifiers.</mark> </br>

+ In the case of the <u> 1T1C DRAM cells</u>, a sense amplifier is often used as a row buffer to prevent the loss of information in the DRAM cells that are read (every read destroys the information in that DRAM cell).</br>

+  Sense amplifiers essentially senses whether or not the storage capacitor has adequate charge and then takes a low power signal and amplifies it to a full logic value (0 or 1). </br>

+ A selected row in memory cannot be accessed until the informations is loaded and stored into the sense amplifiers. This is what leads to CAS (Column Access Strobe) latency where if the desired row is not active by the time it is requested, additional time is required. </br>

As shown in **Figure 2**, in the first step, when the RAS is low, all the cells in an entire row is read by its sense amplifier -- a process that takes a relatively long time. After this, the row is active so that the columns may be accessed for a read or write. Access time (read/write cycle time) for the  RAS is generally much higher than a CAS due to the sense amplifying step. Bus speeds for asynchronous DRAMs typically do no exceed 66 MHz.</br>

<img width="310" height="310" alt="image" src=DRAM_WAVE.png/></br>

Figure 2: Address timing for asynchronous DRAM.</br>

**SDRAM vs DRAM**

+ DRAM operate in either a synchronous or an asynchronous mode.</br>

+ In the synchronous mode <mark>all operations (read, write, refresh) are controlled by a system clock. This system clock is synchronous with the clock speed of the CPU of a computer (~133 MHz).</mark> The reason for this is that it actually allows for much higher clock speeds (3x) than conventional DRAM. All operations to and from the DRAM are executed at the rising edge of a master clock. The typical <mark>single data rate (SDR) SDRAM clock rates are 100 and 133 MHz.</mark>

+ One major differentiating factor in <mark>SDRAM architectures is the memory being divided into a number of sections of equal size. These memory banks can perform access commands simultaneously, allowing for much greater speeds than the average DRAM.</mark>

+ As shown in **Figure 3**, the basic core and operations of the DRAM is essentially the same, the synchronous interleave involved an I/O command interface coming separately from the DRAM chip.</br>

+ The major contribution to the enhanced speeds of SDRAMs come from the concept of pipelining --- while one bank may be in a precharging stating going through access latency, reading may be taking place in another bank so that the memory chip is constantly outputting data. In other words, the architecture of multiple banks allows for concurrent access of different rows.</br>

**SDRAM vs DDR**

+ While the clock rate of a single data-rate (SDR) SDRAM--often referred to as simply SDRAM--would suffice for many applications, they are often not nearly enough for multimedia applications. The next iteration of the SDRAM was the double-data-rate SDRAM (DDR SDRAM). </br>

+ Where the primary evolution came with the ability to transfer data on both the rising and falling edges of the master clock while all commands and operations took place only on the rising edge of the clock -- effectively sending twice the data per clock cycle. </br>

+ This is <mark>accomplished through a prefetching operation where the wide internal bus prefetches two bits(words) of data simultaneously to burst two words of equal width out on the I/O pins. Also known as a 2-bit prefetch, this essentially doubles the data rate without increasing the power consumption of the memory unit.</br>

+ It should also be noted that there is a marked improvement in power efficiency with the DDR architectures, `where DDR2 runs at 2.5V, DDR3 at 1.5V to 1.65V, and DDR4 at 1.2V.` This is due to the revisions in the power management circuitry of the device as well as the ability to more smartly increase the frequency of data transfers without increasing power consumption. The reduction in power consumption allow DDR modules to be a more desirable option for computers that can run off of battery power (e.g.: a laptop).</br>


**NOTES**
> 2 bit word =  is a very simple, archaic machine that processes data in two-bit chunks.  In this 2-bit context, each word can only represent 4 possible values ($2^2$ = 4).
> $2^2$ = 4 bits (1 nibble)
> 1 byte data word = 8 bits ($2^4$ = 8 bits)
> 2 byte data word = 16 bits ($2^8$ = 16 bits)
> 4 byte data word = 32 bits ($2^16$ = 32 bits)
> 8 byte data word = 64 bits ($2^32$ = 64 bits) => 64 bits/8 bits = 8 bytes => 8 bytes * 8 bits = 64 bits

+ `A word's bit size is variable and depends on the computer's architecture; it is not a fixed number. Historically, a 16-bit word was common, but modern 32-bit and 64-bit processors have 32-bit and 64-bit word sizes, respectively. A word is essentially the natural data size that a computer's CPU can process or transfer in a single operation.`

**DDR, DDR2, DDR3, DDR4 - What's the Difference?**

+ The underlying components and functionality/operations for the later evolutions of DDR (DD2, DD3, DDR4) remains the same with the differentiating factor of an increase in clock speed.</br>

+  For instance, a DDR2 RAM added a 2x clock multiplier to the DDR SDRAM interface thereby doubling data transfer speeds while maintaining the same bus speed.This way a ‘4-bit prefetch’ is employed from the memory array to the I/O buffer. Along the same lines 8 bits of data are prefetched in DDR3 modules and 16 bits for DDR4 modules.</br>

<img width="1000" height="410" alt="image" src=BLOCK_DIG.png/></br>

Figure 3: A DRAM memory array with SDRAM interface (to the right) and DDR control interface (to the left).</br>

+ While the core of the volatile DRAM architecture has remained essentially the same, the additional command interfaces off-chip has evolved increased capacity and decreased cost-per-bit. This major evolutions in performance of DRAM could then be contributed to the pipelining of data as well as the increase in I/O buffer frequency.</br>

-----
-----

