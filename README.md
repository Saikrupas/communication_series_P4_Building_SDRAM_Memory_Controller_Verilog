## 💡 SDRAM(Synchronized Dynamic Random Access Memory)

+ <mark>SDRAM, or Synchronous Dynamic Random-Access Memory</mark>, is a type of computer memory that synchronizes with the system's clock to operate faster than conventional DRAM.
+ This synchronization allows it to handle data transfers more efficiently by operating in a pipeline and fetching data in bursts, making it the standard type of RAM used in most modern computers.


### 🚀 Features
+ **Synchronous with clock :** Unlike asynchronous DRAM, SDRAM is synchronized with the system clock. This means both the CPU and the memory know exactly when data will be ready, eliminating wait times and increasing overall speed.

+ **Pipelining :** SDRAM uses a pipeline to accept a new instruction before the previous one is finished processing, allowing for a higher number of operations in a given time.

+ **Burst mode :** SDRAM is optimized for the fact that memory accesses are often sequential. It uses an on-chip burst counter to rapidly increment the column part of the address, fetching an entire block of data in a single burst, which is much faster for sequential reads.

### 🚧Evolution and generations
+ First generation: The first commercial SDRAM was released in 1993 by Samsung. It was called Single Data Rate (SDR) SDRAM and could perform one read or write operation per clock cycle.
+ DDR SDRAM: Subsequent generations, starting with Double Data Rate (DDR) SDRAM, perform two operations per clock cycle (one on the rising and one on the falling edge of the signal).
+ Current technology: Today, there are several generations of DDR SDRAM, including DDR2, DDR3, DDR4, and the current fastest version, DDR5. 
