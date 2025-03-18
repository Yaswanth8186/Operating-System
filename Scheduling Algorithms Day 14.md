# Operating System

## Scheduling Algorithms

### Multi-Level Queue Scheduling Algorithm(MLQ)

- It is real life implementation algorithm.
- FCFCS, SJF, Priority and RR scheduling algorithms are not used/implemented now a days directly. Only RR is used among them at different levels of OS.
- Now a days they are implemented in a optimized way.
- In the earlier algorithms there is no categorization of the processes.
- But, in the MLQ Sheduling ALgorithm the processes are divided into three different categories. They are

1. System Process:
   - These processes are created by th OS. For example init is the first process created by OS after OS boots up.
   - Some of the system processes are network processes. These processes are required to run the kernel/OS.
2. Interactive Processes:
   - These processes require user input. In word the processes wait for I/O to be performed.
   - These processe are called foreground processs because you can see them infront of GUI.
3. Batch Processes:
   - These processes do not require any user input. These processes are also called background processes. These processes run in the background.
   - For example in orphan and zombie processes we use sleep 100&. & at the end of command runs the process in the background.

- For each type of process a separate queue will be maintained like System Process Queue for System Processes, Interactive Process Queue for Interactive Processes and Batch Process Queue for Batch Processes.
- System Process Queue has highest priority followd by Interactive process queue and Batch process queue respectively.
- It means System processes get more chance for execution followed by Interactive processes and batch processes.
- When the process arrives the os places the process ino the corresponding queue based on the nature of the process. Once the process is placed inside a queue then it can not be moved into the other queue. The process will remain inside the same queue till its complete the execution.
- Each queue will use it own scheduling algorithm for picking up the processes from that queue.
- For example, the SP queue can use Round Robin Algorithm, IP queue can use SJF algorithms and BP queue can use priority algorithm.
- For scheduling among these three queues Primitive priority scheduling algorithm is used.
- For example if there are three processes p1, p2, p3. p1 is a batch process, p2 is a interactive process and p3 is a system process. If first p1 arrives then p1 will be scheduled for execution after some time if p2 arrives, p2 will be scheduled for execution as the interactive processes has higher priority compared to batch processes. Then if p3 arrives, p3 will be scheduled for execution as the system processes have higher priority compared to interactive processes.
- If there are processes present in each queue. After all the processes present in the system queue gets executed the processes in the interactive queue will get executed followed by processes in the batch queue.
- If there are more processes present inside the system queue the processes in the interactive queue and job queue should have to wait which leads to increase in the average waiting time i.e, convoy effect.

### Multi-Level Feedback Queue Algorithm(MLFQ)

- It is used nowadays. It is user-defined. It is more flexible.
- There are multiple queues used in this algorithm. The number of queues used can be cutomizable.
- The movement of processes from one queue to another queue is allowed in this algorithm. It is not allowed in the MLQ algorithm.
- Here the processes are separated based on their burst time. The processes with lower burst time are place in the higher queue while the processes with the higher burst time are moved to the lower queue.
- The interactive processes are placed in the higher queue because interactive processes will start when the user open any appplication related to I/O. After opening if the user can not perform any task the user will not be satisfied. To avoid this interactive processes are placed in the higher queue and they get more chance/priority.
- Each queue will have its own scheduling algorithm.
- For execution, the queues at higher level will be given more priority where as the queues at the lower level will be given less priority.
- If there are many processes with less burst time, the processes with more burst time present in the lower queue should have to wait which leads to convoy effect.
- To avoid convoy effect aging method is used. This method increases the priority of the processes present in the lower queue for every specific period of time.
- It is more flexible and configurable.
- For example, if there are four queues. First three queues uses the round robin algorithm with the time quantum 2, 4, 8 respectively and the fourth queue will use the FCFS scheduling algorithm.
- If the process p1 with burst time 10 comes first it will be placed inside the queue-1. As the time quantum of q-1 is less compared to burst time of p1, it will be moved to the next queue 2. AS queue-2 also have less time quantum compared to the burst time of process p1 it will be moved to the next queue 3.
  As queue-3 also have less time quantum compared to the burst time of process p2, it will be moved to the next queue.
- The number of queue used can be customizable.
- Here, there will be less process starvation because the processes with less burst time will get executed first.

**Design of MLFQ**

- Number of queues to be used is decided by the designer.
- The scheduling algorithms used in each each queue.
- The method used to promote the process form the lower level queues to higher level queues - Aging.
- The method used to demote the process from the higher level queues to lower level queues.
- In which queue the process should need to be placed when it arrived first.

### Comparison between various scheduling algorithms

1. FCFS

   - It is simple to design.
   - There is no process preemption. The process gets executed completely.
   - The convoy effect is present. If the process with high burst will arrive first it will get executed and other processes should have to wait.
   - There is no overhead of context-switching.

2. Non-Primitive SJF

   - It is complex to design.
   - There is no process preemption. The process gets executed completely.
   - The convoy effect is present. If the process with high burst will arrive first at t = 0, the other processes with less burst time should have to wait.
   - There is no overhead of context-switching.

3. primitive SJF

   - It is complex to design.
   - There is process preemption. If the process with less burst time comes after sometime the context-switching will happens.
   - The convoy effect is not present.
   - There is overhead of context-switching because of the process preemption.

4. Non-Primitive Priority Scheduling Algorithms

   - It is complex to design.
   - There is no process preemption. The process gets executed completely.
   - The convoy effect is present because if the higher priority process keeps on comming the lower priority processes should have to wait for long time.
   - There is no overhead of context-switching.

5. Primitive Priority Scheduling Algorithm

   - It is complex to design.
   - There is process preemption. If the process with high priority comes after sometime the context-switching will happens.
   - The convoy effect is present because if the higher priority process keeps on comming the lower priority processes should have to wait for long time.
   - There is overhead of context-switching.

6. Round Robin Scheduling Algorithm

   - It is simple to design.
   - There is process preemption. The context-switching will happens if the process reaches its time quantum.
   - The convoy effect is not present because each process will get progress after sometime and the average waiting time will be less.
   - There is overhead of context-switching.

7. MLQ

   - It is complex to design.
   - There is process preemption. If the process with high priority comes the context-switching will happens.
   - The convoy effect is present because the process with less priority or processes in lower queue should have to wait.
   - There is overhead of context-switching.

8. MLFQ

   - It is complex to design.
   - There is process preemption. If the process with high priority comes the context-switching will happens.
   - The convoy effect is present because the process with less priority or processes in lower queue should have to wait.
   - There is overhead of context-switching.
