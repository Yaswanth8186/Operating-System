# Operating System

## Process States

There is a block inside the process control block called process state which stores the current state of the process.

The process goes through throgh the various process states during the lifecycle of the process. These process states are

**1. New:**

- When the OS is converting the program into the process the process will be in new state.

**2. Ready:**

- After the program is fully converted into the process then the process is placed inside the ready queue. All the processes inside the ready queue are in ready state. These are ready to get executed if they are scheduled by the CPU.

**3. Running:**

- In this state, the process is scheduled by CPU and the process is under execution.
- **4. Waiting:**
- During the execution, if the process went to perform some I/O operations then the process is in waiting state. till the process completes performing I/O operations the process will be in waiting state.
- If the process completes performing I/O operations the process goes to ready queue and will eb in ready state.

**5. Terminated**

- If the process completes its execution completely then the process is in terminated state.

**Procedure:**

1. When the OS is converting the program into the process the process will be in new state.
2. After the process is fully loaded the process is placed inside the ready queue and the process will be in raedy state.
3. After that by using the scheduler dispatch the process will be scheduled by CPU for execution then the process is in running state.
4. In running state, if process reaches its time quantum during its execution the process is again sent back to ready queue(ready state) by generating an software interrupt. If the process want to perform some I/O operations the process will be in waiting state and after completion of I/O the process will be sent back to ready queue(ready state).
5. If the process in running state completes its execution the process will exit the CPU and goes to terminated state.

**Types of Queues:**

**1. Job queue:**

- All the jobs/processes which are in the new state are placed inside the job queue. The scheduler used to dispatch the jobs/processes from job queue to ready queue is called job scheduler or long term scheduler.

- There is pool which consists of many programs that are compiled. The job scheduler brings the jobs/processes from the pool to the new state(job queue) and from job queue to the ready state(ready queue).

**2. Ready queue:**

- The ready queue consists of jobs/processes that are ready to get executed by the CPU.
- The scheduler used to dispatch the jobs/process from ready queue to CPU for execution is called CPU scheduler or short term scheduler.

**Types of Schedulers:**

There are two types of schedulers. They are

**1. CPU scheduler**

- It is also known as short term scheduler.
- It works with high frequency and the ideal time is low.
- It dispatches the jobs/processes from the ready queue to CPU for execution.
- CPU scheduler keeps on checking the CPU whether it is ideal or not for every fraction of second.
- If CPU is ideal it pickups the job/process from ready queue and dispatch it to CPU for execution. CPU scheduler picks up the jobs from the ready queue based on the scheduling algorithm, priority.

**2. Job scheduler**

- It is also known as long term scheduler.
- It picks up the jobs/process from the pool and places them in job queue and from job queue to ready queue.
- It works with low frequency and the ideal time is high.
- At 0th minute, if it picks the jobs from pool and again it picks the jobs from pool after 1 minute.

> Degree of multi-programming is the number of jobs/processes that are present in ready queue at a time. Degree of multi-programming is depended on job scheduler/long term scheduler. Because the job scheduler picks up the jobs from pool and place them inside the ready queue.
