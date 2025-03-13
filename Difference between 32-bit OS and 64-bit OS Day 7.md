# Operating System

## 32-bit Operating system VS 64-bit Operating System

### 32-bit Operating System

CPU is embeded inside the mother board andit contains the billions of transistors inside it. Transistors are the individual digital circuits like OR, AND and NAND gates.

By implementing the digital circuits we make registers. Registers is the place inside the CPU where the actual computation is done.
It holds the addresses when you perform any operations.

A register is the memory block. 4 byte reister means the register can hold the 4 bytes of data, information at a time.

32-bit register means the register can hold 32 bits of data at a time. For a 32 bit processor requires 32 bit software for running.

64-bit register means the register can hold 64 bits of data ata atime. for 64 bit proocessor 64 bit software is required.

The Operating system that uses 32-bit registers is called 32-bit Operating System.
The Operating system that uses 64-bit registers is called 64.bit Operating system.

### 32-Bit Operating System

In this type of Operating system, the register can store the 32 bits of data at a time.

CPU fetches the data from the memory and store inside the blocks of the registers. The data is stored inside the memory at the addresss ranging from 0 to n.

In each bit the data stored is either 0 or 1. A 32-bit register can store the 2^32 unique addresses at a time.
A 32-bit operating system can support only 4 GB of RAM. Now a days for running the systems 4 GB of memory is not enough.
The performance is not good.
This type of operating system is used in older systems.

### 64-bit Operating System

In this type of operating system, the register can hold the 64 bits of data at a time.

64-bit of register can hold the 2^64 unique address at a time inside it.  
2^64 = 17179869184 GB of memory

If we try to add a two 64-bit numbers using the 32-bit operating system, it will be a diificult task because in 32-bit os the register can store the 32-bits of data at a time. So, to perform these task the 64-bit number is divided into two parts each part holding 32-bit of data. In the first cycle it adds the first 32 bits and in the second cycle it adds the next 32 bits. But it requires two CPU cycles to complete the task.

> The system performance is depended on number of CPU cycles, the lesser number of CPU cycles results in greater performance.

But in the case of 64-bit operating system the task can be completed in one CPU cycle resulting in the greater performance.

### Advantages of 64-bit Operating System over 32-bit Operating System

1. Addressable spaces:

   - The number of addressable spacesa re more in 64-bit Operating System compared to 32-bit Operating System.

   - It is because a 32-bit os can store 2 ^32 unique addresses at a time. The starting address is 00000001 and the ending address is FFFFFFFF.

   - In the case of 64-bit os it can store the 2^64 unique addresses at a time.The starting address is 0000000000000001 and the ending address is FFFFFFFFFFFFFFFF.

2. Resource usage:

   - If we try to add the extra resources like RAM in 32-bit OS it does not impact any performance because a 32-bit os can support only upto 4 GB of RAM.

   - In the case of 64-bit OS if we add extra RAM it will improve the performance.

3. Performance:

   - The performance is better in 64-bit os because it can process the 64-bits of data at a time.

   - In 1 CPU cycle 32-bit os can process 32-bits of data where as 64-bit os can process the 64-bits of data.

   - In order to perform any computaion 32-bit os require more CPU cycles where as 64-bit os require less cycles.

   - 1GHZ - it means the number of CPU cycles the system can process per second.
   - Generally the system can process the billions of CPU cycles per second.

4. Compatibility:

   - 64-bit CPU can run both 32-bit and 64-bit os. where as 32-bit CPU can run only 32-bit os.

5. Better Graphics Performance:
   - 8 bytes graphic calculations per CPU cycle make graphics intensive applications run better.
