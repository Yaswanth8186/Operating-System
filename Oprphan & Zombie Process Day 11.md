# Operating System

### Mid Term Scheduler(MTS)

- Long term scheduler or Job scheduler picks up the ready to get exceuted programs from the pool which is present in second storage and dispatches them for execution by converting the programms into process new state initially and into the ready queue with ready state.
- Short term scheduler or CPU scheduler pickups the processes/jobs from the ready queue and schedules them for execution by using the scheduling algorithms.

- Degree of multiprogramming is number of job/processes present in the ready queue at a  given time.
-  Job scheduler should make sure that it picks up the mix of jobs/processes from pool and dispatches them to the ready queue because if the job scheduler picks only CPU intensive processes or I/O intensive Processes and dispatches them to ready queue then these processes will take a lot of time for execution a nd other processes should nedd to starve.

- For suppose if the degree of multiprogramming is incresed i.e, the number of processes/jobs present in the ready queue are increased.
- There might be a situation that the intensive processes are getting executed and they require more memory for execution and there is no free memory left to maintain the ready queue as the degree of multiprogramming is increased.
- In this case the CPU will make use of the swap area present the seconday memory and swaps out the processes from ready queue and places them inside the swap area.
- The size of the swap area in more as it is present in the secondary memory.
- If the any intensive process completes its execution the memory will be freed and the CPU swaps in the processes from swap area to the ready queue.
- These entire process of swap-in and swap-out is handled by Medium Term Scheduler(MTS).
- In the earlier system only STS and LTS are only used. In the latest system MTS is also used.

### Context Switching

- Every process will have its own PCB and PCB consists of pid, state, program counter, priority, registers, file descriptors and device descriptors.
- For example if there are two processes p1, p2 in the ready queue. If the process p1 is scheduled for execution by the CPU. The CPU fetches the p1 process details/context from the process control block like program counters, registers, file and device descriptors and starts the execution of the instructions by using the program counter. Program counter contains the details of instructions to be executed. While execution the cpu fectches the instructions and stores them in the registers. The actual computation by cpu is done here.
- If the process p1 reaches its time quantum or performing some I/O operations then the p2 process is scheduled for execution by the CPU.
- During this time context switching takes place and cpu store the information of p1 process program counter, registers, file and device descriptors inside the process control block of p1 and restores the PCB values of p2.
- The context switching task is overhead because the code to perform the context switching is present inside the kernel and that code need to be executed by the CPU. During this time no other process will be executed by the CPU and some process starvation will occur.

### Orphan Process

- fork() is used to create a new process.
- Ever process is created as a child of any parent process.
- The parent process uses fork() and create a new child process.
- The first process that is created when the os boots up is init process in linux and it pid is 1.
- After that any process created is child of init process.
- Orphan process is the process without any parent process.
- Suppose if you created a process p1 and it is in running state by using the fork() the p1 process creates the p2 process as child process and p2 is also in running state.
- Now during this time if any error has raised in p1 and p1 process will be terminated and p2 process has no parent and p2 process is now orphan process.
- It is the rule/norm that if the programmer is creating the child process by using fork() from the parent process. The parent process should have to wait untill the child process completes its execution.
- Now the OS can not track the process p2 as it is not present in the tree structure and the os cannot create the child processes under p2.
- To avoid this the os makes the parent of the orphan process as init process.
- If the process creates the child process the parent process should have to wait until the child process completes its exceution.
- After child process completes execution it returns some value. Parent process reads the value and gets terminates.
- & detaches the present process from the parent process and run it as the separate process without parent.   
### Zombie Process

- All the parent and child process information will be present inside the process table.
- If the process creates the child process the parent process should have to wait until the child process completes its execution.
- After the child process completes its exceution it returns the exit status to parent and release the resources allocated to it but it is exited from the process table only if the parent process comes to wait state and reads the exit status.
- If the parent process goes on wait state for a longer time than required, the child process become a zombie process until the parent process reads the exit status.
- If the parent process creates the thousands of child process and each child process require 1ms for completeing the execution. And the parent process went to wait state for 5 minutes which is huge time the child process will have to wait and become zombies.
- The main problem is, the size of the process table is limited if there are huge number of zombie process present inside the process table the os can not create the new process inside the process table and the system can not perform the new tasks.
