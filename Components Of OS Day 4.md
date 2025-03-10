# Operating System

## Components of Operating System

The two main components of the Operating System are

1. **User Space** - User apps run here.
2. **Kernel** - interacts directly with the hardware.

### User Space

- It can not interact with the hardware directly.
- It provides an environment to run user apps in a convinient and efficient way.
- User Space in windows is GUI.
- User Space in Linux is CLI. Here we use commands to interact with the system.

- In order to create a new folder in windows we right click the mouse and select new folder and assign a name to it.
- In the case of Linux in the terminal we execute the mkdir command. mkdir uses the system calls and directs the file management to create the folder.
- New Folder in GUI internally runs using mkdir.
- User space can interact with the kernel

### Kernel

- It is also known as heart of Operating System.
- It can directly interact with the hardware.
- It receives the specific commands from the user space and reads it and directs the hardware to act accordingly.

### Functions of Kernel

1. **Proces management**
   - Creating and terminating the process.
   - Scheduling the threads/processes.
   - If a user creates the number of processes it makes sure that the Maximum CPU utilization, less process starvation, High priority job execution is achieved.
   - It also takes care of context switching and time sharing bewteen the processes, Process Synchronization.
   - Process Communication - When two processes are executing in isolation and protection some times the processes need to communicate and share the information. The process communication is handled by process management.

- Suspending and resuming the process.

2. **Memory Management**

   - Allocating/Deallocating the memory to a process.
   - It also takes care of free space/memory management. Suppose if a process is allocated with some memory and after a while if the process exits the memory becomes free. All the available memory should be tracked so that it can be allocated to the other process when required.

3. **File Management**
   - Creating and deleting the files.
   - Directory management(Creating and deleting the directories).
   - Mapping the files into Secondary Storage.
   - Files are stored in the directories. The directories are stored in hierarchical mannaer. / is the root directory of the disk.
4. **I/O Device Management**
   - It manages and controls all the I/O devices and I/O Operations of the computer.
   - Suppose a input device like pendrive is insert the kernel checks the haedware and notifies the user about the input device and provides a way to access the pendrive through user space and notifies the user when it is removed.

### Types of Kernel

1. **Monolithic Kernel**

   - All the functions of the kernel are palced inside the kernel and performed by the kernel.
   - There are two modes
     1. User Mode
     2. Kernel mode
   - For switching between the user mode and kernel mode a software interrupt is generated.
   - When you open a CLI it opens in a user mode and after you finished wrriting the command and press enter it will switch to kernel mode and reads the command from the user space and directs the hardware to act accordingly using the system calls.
   - Example : Linux, Unix, MS-DOS.

Advantages

- The communication is fast between the different components/functions of the kernel.

Disadvantages

- It makes the kernel bulky.
- It is less reliable because if any function fails entire kernel will stop working because they are inter-connected.

2. **Micro Kernel**

- The major functions of the kernel i.e, Memory Management and Process Management are placed inside the kernel.
- The remaining functions like File Management, I/O Management are placed inside the user space.
- The main problem is initially a process starts in user space and then switches to memory space to perform the resource and memory management respectively. Inordr to perfoem some I/O operations it need to switch to user space after completion it again nedds to shift to kernel space after that to read any file it agains need to switch to user mode.
- Here we observe that the there is overhead of switching between user mode and kernel mode.
- Example : L4 Linux, Symbian OS  
  Advantages

1. Kernel is less bulky.
2. More reliable.
3. Stable.

Disadvantages

1. Less Performance
2. Overhead of switching between user mode and kernel mode.

> ### Inter Process Communication
>
> - Suppose if a process is getting executed in user space and another space is getting executed in kernel space if the both processes want to communicate the communication between user space and kernel space is achieved through Inter Process Communication.
> - Inter Process Communication is achieved in two ways
>
> 1. **Shared Memory**
>    - A memory is placed in the middle. The data that is to be communicated is placed inside the memory by the process p1 and the other process p2 comes and read the data from the memory
> 2. Message Passing
>
> - A channel is prepared between the user space and kernel space and the processes will communicate through the system calls.

3. Hybrid Kernel

- This kernel is prepared by combining both the advantages of the Monolithic kernel and Micro kernel.
- The File management functionality is placed inside the user space.
- The remaining functionalities are placed inside the kernel space.
- Example: MacOS, MS Windows 

Advantages

- Performance is improved.
- Overhead of switching between user space and kernel space is reduced.

Disadvantages

- Less reliable.
