# Operating System

## Multi-Threading

**Introduction**

Suppose if you write a Armstrong Number program in c++. The file is saved with .cpp extension. While execution of the file, the compiler will convert the .cpp file into the executable file with .exe extension. If you open the executable file you can not read/understand it because the information is stored in the form of bits which can be understanded by the system.

> The executable file is different for the different machines/system.

This executable file will be executed by the system. Every application has its own executable file. The executable file is also known as program. The program usually resides in the storage disk.

If a user wants to execute any program by clicking it, the file comes into the memory from storage for execution. When a program comes into the memory for execution the program is known as process.

> **Process**
> Program under execution is called process.

**Thread**  
Thread is a light weight process which can execute independently from the other threads. It is also known as sub-process.

Suppose if a process contains differnt subprocess/tasks which are independent of each other. Here, each subprocess is known as thread.
Threads help to execute the process fastly by achievening the parallelism. This is because each thread is executed by the different CPU's as they are independent of each other.

> The threads will be executed asynchronously.

For example there is a process which will take a input from the user and do the processing on the input and display the result to the user and it also stores the user input in the cloud. Here the processing and storing in the cloud are the two different tasks. Each task is executed by one thread and the process is executed fastly.

But the concept of threads is apllicable in the cases of multiprocessing environment because although there are many threads if the number of CPU is one the CPU can execute only one thread at a time and the goal of multithreading is not achieved. If there are more than one CPU's one CPU will execute one thread and the remaining CPU's executes other threads at a time resulting in the faster execution of the proceess.

For example, if there is a image_conversion program which converts the image of size 100 x 100 from jpg to png form. Suppose if the user had given a image with a size of 100 x 200 as input. It can divided into the two tasks with each task consisting the image of size 100 X 100. At the end the result of the two tasks is combined.
Let us assume that each task takes 10 seconds. If there is no multi-threading it takes 20 seconds for conversion. By using multi-threading and the image_conversion program is independent the conversion can be completed in 10 seconds.

### Difference between Multi-Threading and Multi-Tasking

| Multi-Threading                                                                                              | Multi-Tasking                                                                    |
| ------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------- |
| Concept of more than one thread being context-switched.                                                      | Concept more than one process is being context-switched                          |
| The number of CPU's are > 1                                                                                  | The number of CPU's are 1                                                        |
| As the threads belong to the same process isolation and protection of threads is not required.               | As the processes are different isolation and protection of processes is required |
| A process is divided in to the different sub-processes called threads which have their own path of execution | It is the process of executing the more than 1 process simultaneously.           |

> As the threads belong to the same process isolation and memory protection is not required and utilizes the same memory space and resources.

**Program**

- Program is a executable file which contains the set of instructions written to complete specific task/operation on the computer.
- It is a compiled code and ready to get executed.
- It is stored inside the disk.

**Process**

- Program under execution is known as Process.
- It is present inside the RAM.

**Thread**

- Thread is a light weight process which have independent path of execution in the process.
- Used to achieve the parallelism by dividing the process into the sub-taks also known as threads which have independent path of execution.
- Example : Mutiple tabs in a browser, text editor(Saving, Formatting and Spell Check).

**Threads Scheduling**

Threads are scheduled for execution based on their priority. The thread with more priority gets the more time quantum of a process.

### Difference between Thread Context Switching and Process Context Switching

| Thread Context Switching | Process Context Switcing |
| --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| OS saves the current state of the thread and switches to the another thread within the same process by restoring its state. | OS saves the current state of the process and switches to the another process by restoring its state. |
| No need to switch the memory address space.                                                                                  | Need to switch the memory address space.                                                               |
| Fast Switching                                                                                                              | Slow Switching                                                                                        |
| CPU's cache state is preserved.                                                                                              | CPU's cache state is flushed.                                                                          |
