# Operating System

## Goals of Operating System

1. **Maximum CPU Utilization**
   - CPU processes the process, jobs, tasks.
   - CPU shouls be utilized in a maximum way.
   - The CPU should not be kept idle.
   - For example if there are three processes p1,p2,p3 and a CPU. If the CPU starts executing the process p1 and after a while p1 went to perform some I/O operations the CPU should not be kept idle and the other processes should be sent for execution until the p1 process comes back.
2. **Less Process Starvation**
   - The processes should not kept idle for a long time. The processes should have to make progress and responsive to the users.
   - For example if there are three processes p1, p2, p3 and a CPU. If a process P1 is getting executed and it contains a statement like while(1) or it takes lot of time to execute. During this time the others processes can not make progress and should have to starve for a long time. This situation should be handled in a effective way.
3. **High Priority task/job execution**
   - If the processes are getting executed and suddenly a high priority process comes for execution all the running processes should need to be halted and high priority process should be sent for execution.
   - For example when a usb drive is inserted into the system the system automatically executes the anti-virus scan program to check the USB. During this time all running processes should be halted and the anti virus program should be sent for execution.

> **Ready Queue**  
>  Ready queue consists of jobs that are ready to get executed if given chance.

## Types of Operating System

1. **Single Process Operating System**

   - In this type of operating system only one process can be executed at a time.
   - The execution of the new process starts only if the present running process is executed completely.
   - By using this type of OS, maximum CPU utilization can not be achieved because if the process p1 went to perform some I/O operations the CPU can not execute the other process as the execution of the previous process is not complete. During this time the CPU remains idle and maximum CPU utilization can not be achieved.
   - Less process starvation can not be achieved if the present executing process takes longer time to complete or went to perform some I/O operations the other processes should have to wait and can not make progress.
   - High priority job execution can not be achieved because if high priority jobs comes for execution it can get executed only if the present executing process completes its execution.
   - Example : MS-DOS(Microsoft Disk Operating System)

2. **Batch Processing Operating System**

   - In this type of operating system user prepares the jobs using the punch cards.
   - Then the user submits the job to the operator.
   - The operator sort the jobs into the batches on gthe basis of requirements.
   - Then the operator send the batches to the processor one by one.
   - The processor executes the process present in the batch one by one according to the **Single Process OS**
   - It is similar to the **Single Process OS** and the maximum CPU Utilization, less process starvation, high priority task execution i.e, goals of the operating system can not be achieved.
   - Example : ATLAS

3. **Multiprogramming Operating System**

   - In this type of operating system if the process p1 went to perform some I/O operations the OS will pick the other job /process from ready queue and starts its execution.
   - **Process Control Block(PCB)** stores the context, state of the process.
   - If the process p1 went to perform some I/O operations the OS stores the context of p1 inside the PCB and restores the context of P2 from PCB and continue its execution. This entire procedure is known as context switching.
   - By using this type of OS Maximum CPU utilization can be achieved as the OS starting executing the other process when the present executing process went to perform some I/O operations.
   - Less process starvation cannot be achieved.
   - High priority process execution can be achieved upto some extent.
   - Example : THE

4. **Multi Tasking Operating System**
   - In the case of Multi Processing Operating System if the process p1 contains while(1) Or takes lot of time to complete the other processes should have to starve.
   - In order to avoid this Multitasking operating system introduced the concept of time quantum. Int this case each process is assigned a time quantum. If the process under execution reaches its time quantum the other process will start its execution.
   - If there is big process which takes a lot of time to complete its execution reaches its time quantum OS stop its execution and the other process can progress avoiding starvation.
   - Each process will get a chance for execution resulting in less process starvation.
   - By using this type of perating system all the goals of Operating System can be achieved.
   - This type of OS uses the concept of context switching and time quantum.
   - Example : CTSS(Compatible Time Sharing System)
5. **Multi Processing Operating System**
   - This type of OS also uses the context switching and time quantum.
   - The difference between the Multi processing and Multi tasking operating system is number of CPU's.
   - In the multi processing operating system the number of CPUs are >= 1.
   - There are many number of CPU's present. If there are many processes each CPU executes the one process.
   - At a given time the OS executes more than one process.
   - If a high priority process comes for execution One CPU will execute the high priority process and other CPU's will execute the other processes.
   - The main advantage if one CPU will fail the other CPU's will continue the execution and providing the better and improved reliability and throughput.
   - Example : MS Windows
   - By using this OS we can achieve all the goals of operating system.
6. **Distributed Operating System**
   - In this type of operating system the OS is in one system and the CPU, memory are present in different locations and in the different systems which are interconnected through the internet, LAN.
   - If a system is executing the process the os will send the process to the another system for execution.
   - Differnt systems may have the different configuration such as GPU, high end, low end.
   - Based on the required resources by the process the system will send the process to the corresponding system.
   - It is also known as loosely coupled/connected autonomous interconnected computer nodes/systems.
   - By using this type of OS we can achieve all the goals of the operating system.
   - Example : LOCUS
7. **Real Time Operating System**
   - This type of operating system is used in the places where there is no chance of error and the real time computation is required.
   - For example in ATC systems the chance of error should be minimal and the computations should be done in real time.
   - If a process needs to get executed the OS will execute it as fast as it can in real time.
   - It is also used in industries like the Nuclear power plants.
