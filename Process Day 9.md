# Operating System

## Process

For suppose if you want to perform some task you write it in a file and save with .cpp extension. This file/data is not ready to get executed by the CPU.

The file is compiled by the compiler and converted into a executable file with extension .exe. This executable file is ready to get executed by the CPU.

This executable file consists of instructions/data that can be understood by the OS. Human cannot understand it.

This executable file is known as program. The program resides inside the storage disk.

If we open the program it will be converted into the process and brought into the memory and gets executed by the CPU.

Process is program under execution.

Process is unit of work done by the computer. PC is logical association of hardware. If you want your PC to do some work, this work is done by the computer.

Why process is required?

If you want to perform some task. Yow write it inside a file and save with some extension like .cpp and it is compiled by the compiler and converted into the executable file called program. The program is brought into memory for execution and the execution is performed by the process.

### How Operating system converts the program into process or How operating system creates the process

The entire procedure consists of five steps. They are

**1. Loads the program and static data into the memory**

- OS loads the program and static data into the memory.
- static data contains all the data used for initialization.
- The example for static data is

```cpp
int a = 10;
char *name = "Yas";
```

- When the program is converted into the process the process initialize all the static data.
- OS loads all the instructions in the program along with the static data into thye memory.
  **2. Allocate the run time stack**
- Rum time stack is part of memory used to store all the recursive calls and the present data of the function before the recursive function is called.
- It is also used to store the local variables, function arguments and return values of the functions.

**3. Allocate Heap**

- Heap is a part of memory that is used for dynamic memory allocation. Like if we use malloc(), new() this memory is allocated in heap.

**4. I/O Tasks**

- For example in Unix system for performing the I/O taks various descriptors are formed. They are
  - Input descriptor
  - Output descriptor
  - Error descriptor
- Input descriptor consists of handler that controls where the input is taken for the process.
- Output descriptor consists of handler that controls where the output of process should be writte.
- Error descriptor consists of the handler that controls where the error should be shown or how error should be handled when the process generates an error.

**5. OS handoff the control to the main()**

- Now the process it allocate with stack, heap and descriptors. Now, the process starts its execution from the main() function. It is the only function known by os.
- Athe end of the main() function after completing all the operations we should have to write the

```c
return 0;
```

- It is because the process is created as child process of the other process. OS do not know that whether this process is completed sucessfully or not.
- By returning 0 we ensure that the process is executed successfully if any other thing is returned it means an error is generated and provide a way to handle it.

### Architecture of Memory

Every process is allocated with some memory. The architecture of the memory is

1. Stack
2. Heap
3. Data
4. Text

5. Text:
   It stores all the instructions of the program fetched from the disk. (Compiled code)
6. Data:
   It stores all the global variables and static data of the process.

Heap and Stack are kept as far as they can so that they have enough memory for execution.

The possible errors during the execution are

1. Stack overflow error:

   - If the Program conatains the recursive functions before calling the recursive function we should have to store all the data of the local variables inside the stack.
   - If the program does not have any base condition the recursion function keeps on executing and the size of stack increases. If the size of stack reaches the heap it will throw an Stack Overflow error.

2. Memory insufficient error:

   - All the dynamic memory allocations happens inside the heap area.
     After allocating the memory to a object the memory should be released by object if it is no longer required. In java it is done automatically. But in C/C++ the developer should take care of this.

   - If we are not releasing the memory of object which is no longer required and keeps on allocating the memory then heap size will also reach the stack resulting in memory insufficient error.

These errors can be avoided by

1. Stack overflow error:
   The developer should have set the proper base case so that the recursive function exceution will be stopped after the base case is reached.
2. Memory insufficient error:
   The developer should have to release the memory of the objects that are no longer required.

## Process Attributes

There will be lakhs and millions of processes created inside the OS. Process attributes are used to distinguish between the various processes.

All the processes created are stored inside the process table. Each entry of the process table is called Process Control Block(PCB).

PCB is a data structure that stores all the information/attributes related to the process.
Every process has its own PCB. OS recognize the process through the attributes of the process that are present inside the PCB.

The various blocks/attributes of the process inside the process control block are  
**1. Process Id:**

- It is a unique id assigned to the process which differentiates the one process from the other process.
- In order to assign a unique id to each process. OS keeps track of the counter which is intialized to zero when the os is booted. The counter will be incremented after assigning the counter value to a new process.

**2. Program Counter:**

- Program counter is a number which keeps track of which instruction is executed lastly.
- Suppose if a process completes it's time quantum and goes into wait state after comming back to execution CPU fetches the program counter value and starts executing the instructions from there.

**3. Process State:**

- Process state is used to store the current state of the process.

**4. Priority:**

- Based on the importance of the process the priority will be assigned to a process.
- The CPU executes the process with higher priority first.

**5. Registers:**

- While execution the cpu uses the many registers. They are
  - Base pointer register
  - Control pointer register
  - stack pointer register
- The CPU actually performs the computations on the registers. If the process reaches it time quantum all the data stored inside these registers is lost.
- To avoid this these registers data is store inside the register block and fetch back again when the CPU starts exceuting the process again.

**6. Open Files List:**  
 It is descriptor which stores all the operations performed by the process on the various files.

**7. Open Devices List**  
 It is descriptor which stores all the devices used by the process during it's execution.
