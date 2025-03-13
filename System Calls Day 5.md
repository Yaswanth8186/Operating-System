# Operating System
## System Calls

The two components of the operating system are User space and kernel space.

User space and kernel space are two difference areas. Normally they cannot communicate each other directly.

User space is the place where the user applications are running. In the user space user can interact with the application. But the core work like process managament, memory management, file management and I/O management are handled by kernel space.

User space will not have access to the hardware. But the kernel space have access to the hardware.

Suppose if the application like word needs to start running in the user space it require some memory, CPU execution cycles. Normally these things are handled by the kernel. So, user space should have to communicate with kernel and ask to allocate memory, CPU execution cycles for its execution. So, this communication between user space and kernel can be achieved by using the system calls.

> System calls provide a mechanism in which the user space can communicate with the kernel space.

#### Example
Creating a new folder can be done in two ways

1. In the GUI, By right clicking the mouse we can see the new select new after that select the folder and provide the file name. Then the new folder is created.
2. Another way is through the terminal. Inside the terminal write the command mkdir followed by file name it will also creates the new folder.

But the GUI method, internally uses the mkdir command to create the new file.

> - All system calls are wriiten in C(Low Level C). Low level C can directly interact with the hardware.  
> - User space can communicate with the kernel using the system call interface.  
> - Every system call implementation is present inside the kernel.  
> - After receiving the instructions from the user space the system call interface maps it to the corresponding implementation in the kernel and the command will get executed from the kernel.


> By using the software interrupt we can switch between the user mode and kernel mode.

> **System Call**
> - A system call is a mechanism through which the user program can request a sevice from the kernel for which it does not have the permission to perform.
> - System call is the only way throgh which the process can go to kernel mode form the user mode.

Types of System Calls

1. Process Management
   - Create process, terminate process
   - load,execute
   - end, abort
   - set process attributes, get process attributes
   - allocate, deallocate memory
   - wait event, signal event
   - wait for time
2. File Management
   - vreate file, delete file
   - open file, close file
   - read, write, reposition
   - set filr attributes, get file attributes
3. Device Management
   - Reuest device, release devive
   - logically attach or detach device
   - set device attributes, get device attributes
   - read, write, reposition
4. Information maintenance
   - set process, file, device attributes
   - get process, file, device attributes
   - get system date, set system data
   - get date and time, set date and time