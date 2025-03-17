# Operating System

## Scheduling Algorithms

### Shortest Job First Algorithms(SJF):

- In this algorithms the scheduler picks up the job/process with least burst time/execution time from the ready queue and dispatches it to the CPU for execution.
- This is because in the FCFS we have observed that the if the intensive job comes first into the ready queue, it will be scheduled for execution. In this case the remaining processes should have to wait for long time for getting exceuted. The average waiting time of all the processes is high which leads to the convoy effect.
- So, here we schedule the processes with least burst timme first.
- At a given time there are many processes present in the ready queue. In that case the process with least burst time is scheduled for execution.

**Non-Primitive SJF:**

- In this case if a process with less burst time is scheduled for execution, the process will gets executed completely. After that the other process will get executed. There will be no process preemption.
- The deciding factor is Arrival Time + Burst Time

Example:

![Non-Primitive SJF](/Photos/Non-Primitive%20Shortest%20Job%20First%20Scheduling%20Algorithm.jpg)

- In the example, we have observed that the total waiting time of all the processes is 31 and the average waiting time is 7.75.
- The main disadvantage at time t = 0, if ther is only process p1 with the burst time 80 is present. It will get scheduled and it takes 80 units of time for completion.
- If there are other processes with less burst time after t > 0, the other processes should have to starve leading to increase in the average waiting time also known a s convoy effect.

**Primitive SJF:**

- For each second(assumption), the STS scheduler checks the ready queue and dispatches the process with the less burst time for execution.
- Here the deciding factor is Arrival time + Burst Time + Preemption.

Example:

![Primitive SJF](/Photos/Primitive%20Shortest%20job%20first%20scheduling%20Algorithm.jpg)

- In the example, we have observed that the waiting time of all the processes is 26 and the average waiting time is 6.5.
- Here there will be no problem of convoy effect because if there is a process p1 with burst time 80 at t = 0 is scheduled for execution, after 1 unit of time the SJS checks the ready queue for the process with least burst time.
- If there is a process with less burst time present in the ready queue the context switching happens and the process with least burst time will get executed. The processes with less burst time will no longer need to starve.

### Priority Scheduling Algorithm

- In this algorithm the STS picks up the process with the highest priority from the ready queue and dispatches it for execution.
- At the given time there are many processes present in the ready queue the scheduler picks the process with highest priority and dispatches it for execution.

Non-Primitive Priority Scheduling Algorithm:

- In this algorithm if the process with highest priority is picked and dispatched for execution, it will get executed completely by the CPU. There is no process preemption.
- The deciding factor is Arrival Time and Priority

Example:

![Non-Primitive Priority Scheduling Algorithm](/Photos/Non-Primitive%20Priority%20Scheduling%20Algorithm.jpg)

- From the example we have observed that the waiting time of all the processes is 67 and the average waiting time is 9.5
- The main problem here is convoy effect because it there is a processes with least burst time but less priority and there are processes with higher priority the processes with least priority should keep on waiting which leads to increase in the average waiting time.
- If the higher priority processes keep on comming the least priority processes should keep on waiting and leads to extreme convoy effect.

Primitive Priority Scheduling Algorithm:

- In this algorithm for every 1 sec(assumption), the STS keep on checking the ready queue for the higher priority jobs and schedules the higher priority job for execution by context switching. There will be process preemption.
- The deciding factor is Arrival Time + Priority + Preemption.

Example:

![Primitive Priority Scheduling Algorithm](/Photos/Primitive%20Priority%20Scheduling%20Algorithm.jpg)

- In the above example we have observes that the waiting time of all the processes is 80 and the average waiting time is 11.4
- In this algorithm there is the problem of context switching overhead because if the high priority process keep on comming for every 1 second the context switching will also happen for 1 sec.
- It also leads to the convoy effect as the process with less priority should keep on waiting and sometimes it also leads to extreme convoy effect.

### Biggest drawback in Primitive and Non-Primitive Priority Scheduling Algorithms

**Indefinite Waiting or Extreme Starvation or Extreme Convoy Effect**

- Suppose if there are some processes with least priority and there are processes with highest priority and if the higher priority processes keeps on comming into the ready queue the higher priority processes are only scheduled for execution.
- The least priority processes should have to wait for an indefinite amount of time and sometimes they may not get CPU at all.

There is rumour that the IBM 7094 system was launched at MIT in 1967. In that system the priority scheduling algorithm is used.After that there are many jobs are submitted to the system. In 1973 they have observed that the there are many low priority jobs are present in the ready queue from 1967. Because of the higher priority jobs the low priority jobs did not got CPU for execution.

**Solution**

**Aging**

- Aging method is used to overcome the problem of indefinite waiting/extreme starvation/extreme convoy effect.
- Aging method increases the priority of the low priority jobs by 1(customizable) for every specific amount of time. So that at some time the priority of those processes will become high and gets executed.
- For example the priority of the low priority job is increased by 1 for every 15 seconds(customizable). After sometime the priority will become high and the process gets executed.

### Round Robin Scheduling Algorithm

- It is called because it gives chance to the every process present in the ready queue fo getting executed.
- In this algorithm every process will get chance for execution and each process can make progress. Because of this the starvation is less in this algorithms.
- As the starvation is less there will be no convoy effect.
- It is the most popular algorithm and it is even used now in different levels of operating system.
- It is also known as FCFS primitive version.
- It is easy to implememt.
- It is designed for the time sharing systems. It is mainly used in the multi-tasking operating systems.
- The deciding factor is Arrival Time and Time quantum.
- In this algorithm a fixed time quantum is assigned for the each process after the process reaches its time quantum the os checks if the remaining burst time.
- If the burst time is completed the process gets terminated otherwise the process is placed inside the queue again.

Example:

![Round Robin Scheduling Algorithm](/Photos/Round%20Robin%20Scheduling%20Algorithm.jpg)

- In the above example we have observed that the waiting time of all the processes is 38 and the average waiting time is 6.3
- We noticed that the average waiting time is low. So, there will be no problem of starvation and convoy effect.
- The main problem is overhead of context switching. In the above example, the time quantum is 2 and the context switching is also more. If the time quantum is 1 the context switching will be even more. Which will cause the high overload of the context switching.
- It will be more efficient because here we are not depending on the burst time which is assumption.
