# Operating System

## Process Scheduling/CPU Scheduling Algorithms

### Introduction

Process Scheduling:

Ready queue consists of jobs/processes which are ready to get executed by the CPU if they are scheduled.

If the CPU is free, CPU scheduler or STS pickup the job from the ready queue based on the process scheduling algorithm/CPU scheduling algorithm and dispatches it to the CPU for execution.
This process is known as process scheduling.

- Process scheduling algorithm/ CPU scheduling algorithm picks up the job and give to the CPU scheduler and scheduler dispatches the job to the CPU for execution.

**Types of Scheduling Algorithms:**  
The two different categories of the scheduling algorithms are

1. Non-Primitive Scheduling Algorithms
2. Primitive Scheduling Algorithms

**1. Non-Primitive Scheduling Algorithms:**

- In these algorithms there is no time quantum assigned to each process.
- After the CPU starts executing the process it will come back to ready queue only if it went to wait state to perform I/O operations.
- Otherwise the process gets terminated after the process completes its execution.

**2. Primitive Scheduling Algorithms**

- In this algorithms there is a time quantum assigned to each process.
- During execution the process can get terminated after completion of execution, can go to wait state when performing I/O operations and goes back to ready queue if it reaches the time quantum.

**Comparisons**

1. Starvation:

   - Process starvation is more in non-primitive scheduling algorithms because if the intensive process is scheduled for execution the remaining processes should have to wait(starve).
   - Other processes cannot make any progress.
   - Process starvation is less in primitive scheduling algorithms because each process has fixed time quantum after the time quantum is reached the other processes start executing. In this way all the processes can moke progress.

2. Maximum CPU utilization:

   - CPU utilization is more in primitive schedulin algorithms because the CPU executes the all processes.

3. Overhead:

   - Primitive scheduling algorithms are overhead because if the time quantum is 1 sec the context switching of processes occur for every 1 second which leads to performance overhead.

**Goals of scheduling algorithms**

1. Maximum CPU Utilization:

   - The scheduling algorithms should be designed in a way that the CPU should not be kept waiting.
   - The CPU should keep on executing the processes.

2. Minimum turn around time:

   - The turn around time is the time duration between when the process first comes to ready queue till its complete the execution and gets terminated.
   - The turn around time should be minimum.

3. Minimum waiting time:

   - The amount of time the process waits for getting CPU after entering into ready queue and till its complete the execution.

4. Minimum response time

   - The response time is duration of time between when the process first comes to ready queue and the time when the process gets CPU for the first time.

   - The response time should be minimum.

5. Maximum throughput:

   - Throughput is the number of processes completed execution per unit time. It is the factor used to measure the performance of the scheduling algorithm.
   - The maximum throughput means maximum number of processes will gets executed and maximum CPU utilization can be achieved.

Key Terms:

1. Arrival time(AT): It is the time when the process first arrived at the ready queue.
2. Burst time(BT): It is time required by the process for completing its execution.
3. Completion time(CT): It is the time when the process completes its execution totally.
4. Turn around time(TAT): It is the duration of time between when the process completes its execution and when the process first arrived at the ready queue. TAT = CT-AT
5. Wait time(WT): The amount of time the process waits for getting CPU. WT = TAT-BT
6. Response time(RT): It is the duration of time between when the process first comes to the ready queue and the time when the process gets the CPU for the first time.

#### First Come First Serve Scheduling Algorithm(FCFS):

It is non-primitive scheduling algorithm.

In this algorithm the scheduler picks up the jobs/processes which came first into the ready queue.
For example if there are three processes p1,p2,p3 arrived in the same order into the ready queue. The scheduler first picks the p1 then p2 followed by p3.

The main disadvantage of this scheduling algorithm is convoy effect.

For example

| Pid | Arrival Time | Burst Time | Completion Time | Turn around Time | Waiting time |
| --- | ------------ | ---------- | --------------- | ---------------- | ------------ |
| 1   | 0            | 20         | 20              | 20               | 0            |
| 3   | 1            | 2          | 22              | 21               | 19           |
| 2   | 2            | 2          | 24              | 22               | 20           |

In this example, the average waiting time is 13 which is high because the intensive process is picked first as the intensive process came first into the ready queue.

As the intensive process take lot of time for completing the execution the other process should have to wait(starve).

| Pid | Arrival Time | Burst Time | Completion Time | Turn around Time | Waiting time |
| --- | ------------ | ---------- | --------------- | ---------------- | ------------ |
| 1   | 0            | 2          | 2               | 2                | 0            |
| 3   | 1            | 2          | 4               | 3                | 1            |
| 2   | 2            | 20         | 24              | 22               | 2            |

In this example, the average waiting time is 1 which is low because the intensive process came late into the ready queue it gets executed last and the remaining processes will not wait.

**Convoy effect:**

- If there are processes with high burst time they will affect the waiting time of all other processes and average waiting time will be high. It is called convoy effect.
- Coonvoy effect is the situation where the processes require a resource for a shorter period of time are blocked by the process for a longer period of time. This leads to the poor resource management.
