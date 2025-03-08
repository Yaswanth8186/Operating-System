# Operating System

## Introduction

For running any application in mobile/system it requires various resources like CPU, GPU, Memory, Disk.

### What happens if there is no OS or Why we need OS

If we open the youtube application it uses CPU, GPU, memory and disk and start running.

During this time if we try to open the other application like Whatsapp it goes into the hang state.

It is because when the youtube application starts ruiing it acquires lock or uses the entire memory, disk, CPU, GPU although it requires only some part of each resource. So, whatsapp can not run although there are available resources.

> Operating System makes sure that the these resources are managed effectively.

Operating System makes sure that it allocates only required amount of resources to each application rather than allocating the entire resources to the single application.

> Operating System acts as a interface between between user application and computer hardware.

Where we are writing code in c/c++ weuse functions like new() and malloc() to allocate memory.
Here, we are not worried about how the system is allocating the memory in the disk and in which sector the memory is getting allocated.

> Operating system helps in effective memory management.

If there is no OS, the developer has to write the code for resource management and memory management along with the application code which makes the application more bulky.

It also violates the principle of DRY(Do not reprat yourself) because the code for memory and resource management is same in the every application.

> So, Operating system handles the resource management and memory management and makes the application less bulky and the developer can focus only on writing the application code.

If the youtube application is running in memory, it uses some memory there is a chance that when the whatsapp application starts running in the memory there may be a chance that it can overwrite the memory of youtube application which leads to a serious security problem. This happens because there is no tracking that which application is using which part of the memory.

Operating System keeps track of which application is using which part of memory and makes sure that the an application will not over write the memory of another application.

> Operating system makes sure that that the application will execute in isolation and protection.

### Basics

1. **Application Software**  
   Applcation software performs a specific task for the user.

2. **System Software**
   System software controls and operates the computer systema and provides a platform to run application software.

   > OS is made up of collection of system software.

3. **Opertaing Sytem**
   Operating system is a piece of software that manages all the resources of a computer i.e, software and hardware and provides an environment in which the user can execute the program in a convinient and efficient manner by hiding the underlying complexity of hardware and acting as a resource manager.

### Operating System Functions

1. Access to the computer hardware.
2. It acts as a interface between the user application and computer hardware.
3. Resource Management (Arbitration)
4. Hides the underlying complexity of the hardware(Abstraction)
5. Faciliates the execution of the application program by providing the isolation and protection.
