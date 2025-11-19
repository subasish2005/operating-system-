this is the read me file for the opeating system 
***Mulitprogramming operating system ***
a single program cannot in general keep either the cpu or the io devices busy at all times the basic idea of multiprogramming operating system is it keeps several jobs in main memeory simultaneoulsy 
teh jobs are kept initially on the disk in the job pool.this pool consists of all processes residing on disk awaiting allocation of main memory 
the operating system picsk and begins to execute one of the jobs in main memory .eventually the job moy have to wait for some task such as io operations to complete 
in a  non multiprogrammed system the cpu would sit idle and wait but ina multi programmed system the operating system simply switches to and ececutes another job when that job needs to wait the cupu switches to another job and so on 
even tually teh first job finishes waiting and gets the cpy  back so conclusion is as long as at least one job needs to execute teh cpu is never idle 
***multitasking operating system***
is is an extension of multiprogramming operating system in which the cpu is not idle at all times and the job switching is so fast that it seems like all the jobs are running at the same time simultaneouls and its done using the round robin algorithm and in muliprogramming the multiple processes are from the same user but in multitasking the multiple processes are from different users and so on 
***multiprocessing operating system***
a multiprocessing operating system supports the simultaneous execution of multiple processing by utilizing two or more cpu within a single computer system .the gole is to enhance processing speed and reliability 

how it works?
the system distirbutes processes across multiple cpu allowign tasks to be executed parallel this paralleslism increases efficiency and reduces processing time and improvees system prformance 

advantages
increased throughput
improved performance
improved reliability
better resources utilization

***Real-time operating system***
an rtos is designed to process data and execute tasks within a strict time constraint providign predictable and deterministic responses to real time events .it is essential for applications requiring real-time performance such as video games and medical devices 
mechanism:rtos proritizes tasks based on their urgency and importance using real time scheduling algorithms .it ensueres the high priority tasks are executed first and low priority tasks are executed last and preempting low priority tasks to allow high priority tasks to execute
advantage of rtos
predictability:ensures  consistent timely responses to real time events 
reliabilit:provides stable and dependable performance in time sensititve applications
resource management :efficiently lmanages system resources to meet the demands of reaal time applications minimizing latency and maxmimizing throughput
there are two type 
hard real time operating system:ensures tasks are completed within the specified time constraints and cannot be preempted by lower priority tasks and are syspened if they exceed their time constraints.t=t0=0t=0
soft real time operating system:allows for some fleixibility in deadlines reacting at t=t+0=0+t=0+ delays are acceptable but kept to a minimum and is common in system like digitabl camera mobile phones and online data processing where delay are not critical 
***batch operating system***
a batch os executes a group of smimilar jobs collected into batches without user interaction during execution user submit jobs to the opeartor who groups them and allows the os to execute them sequentially
 how it works ?
  User submits jobs → Jobs stored on input devices (cards/tape)

  OS loads job → Executes → Stores output

  User collects output later

feautures :no real time interactions 
           jobs processed sequentially or based on priority 
           user spooling to optimize cpu time 

what is spooling :spooling stand for simulaneously peripheral operation on line and it is a buffering technique used for operations system to overlap io operations with cpu processing .instead of sending data directly into an io device which is usually slower than cpu the data is stored temporarily in a buffer or disk area called the spool 
this allows the cpu to continue executing other tasks without waiting for slow io devices liek printer and etc 

how does spooling work ?
A user program generates output (example: print request).

Instead of sending it directly to the printer, the OS stores it in a spool file (buffer on disk).

A separate background process (spooler) monitors the spool and sends jobs to the device one-by-one.

As the printer works, the OS can continue accepting new print requests.

advantages :
            better utilization of cpu compared to manual operations 
            reduces turn around time delay in large job enviroments 

***distributed operating system***
it manages physically separate computers as if they are one system 

advantages :
            allows distributed processing of data
            decentralized reesources sharing 
            load distributed
            fault tolerance 

advantages are :
shared computations and resources 
scalability 

disadvantages are :
complex communication and synchronization
network dependency 

examples : amoeba os 
           google borg 

***network operating system ***
allows computers to communicate,share files with each other over a network
 

 | Feature              | Batch OS         | Multiprogramming | Time Sharing     | Real Time OS          | Distributed OS | Network OS        | Multiuser OS    | Multiprocessing OS      | Mobile/Embedded OS |
| -------------------- | ---------------- | ---------------- | ---------------- | --------------------- | -------------- | ----------------- | --------------- | ----------------------- | ------------------ |
| User Interaction     | ❌ None           | ❌ Very low       | ✔️ High          | ❌/✔️ Risk-based       | ❌ Hidden       | ✔️ Network level  | ✔️ Multi access | ✔️ Not user-focused     | ✔️ UI based        |
| Scheduling           | Simple batch     | Non-preemptive   | Preemptive       | Priority/Deadline     | Load-balanced  | Client-Server     | Fairness based  | Parallel CPU scheduling | Lightweight        |
| Response Time        | Slow             | Faster           | Very fast        | Deterministic         | Variable       | Network dependent | Moderate        | Fast                    | Fast               |
| Hardware Requirement | High             | Medium           | High             | Application dependent | Very high      | Medium            | Medium–High     | Multi-CPU               | Low/Medium         |
| Use Case             | Billing, payroll | Mainframes       | Shared computing | Military, Robotics    | Cloud, Cluster | Enterprise LAN    | Servers         | Parallel computation    | Smartphones/IoT    |


| OS Type                 | Essential Properties                                            |
| ----------------------- | --------------------------------------------------------------- |
| **Batch OS**            | Non-interactive, sequential execution, job scheduling, spooling |
| **Multiprogramming OS** | CPU maximization, memory protection, scheduling                 |
| **Time-Sharing OS**     | Preemptive scheduling, rapid response, multiuser support        |
| **Real-Time OS**        | Predictability, priority scheduling, bounded lateness           |
| **Distributed OS**      | Transparency, communication, load balancing, fault tolerance    |
| **Network OS**          | Resource sharing, secure communication, centralized access      |
| **Multiuser OS**        | User isolation, authentication, concurrent sessions             |
| **Multiprocessing OS**  | Parallelism, multitasking, synchronization, locking             |
| **Mobile/Embedded OS**  | Lightweight kernel, power optimization, real-time support       |


system calls:a system call is a mechanism that allows a user level program to request a service from the operating system kernel .since user programs cannot directly access hardware or execute privileged insruction system calls act as a contorlled interface between user mode and kernel mode 

user programs are in a restricted enviroment called the user mode where 
  direct access to hardware is blocked 
  privileged instructions are not allowed 

to perform such restricted operations program must request the os to do it ontheiir behjalf this request is made through a system call
mode bit : 
          in order to ensure the proper execution fo the operating sytem we must be able to distinguish between the execution of operating system code or kernel process and user defined code or user process 

at the very least we need two separate modes of operation user mode and kernel mode also called supervisor mode system mode or previleged mode .a bit called the mode bit is added to the hardware of the computer to indicate the current mode kernel(0) or user mode(1)

process :
         a process is a program in execution 
         a program is not ineherantly a process .a program is a passive entitiy meaning it is a file containing a list of instructions stored on a disk and and is oftern referred to as an executable file 

         a program becomes a process when the executable file is loaded into main memory and its process control block is created 
         conversely a process is an activee entity that requires resources like main memory and cpy time etc 

the process consists of the meta space the stack data and the head data and the program code or text section 

what is scheduler ?
a scheduler is a componnent of the operating system which is responsible for selecting processes and deciding which process runs at a particular time and managing process transition among different states 

long term scheduler:in multiprogramming os more preocesses are submitted that can eb executed immediately tehse processes are spooled to mass storage device where they are kept for late execution the long term scheduler or job scheduler selects processes form this pool and loads them into the main memory for execution 
                                  it takes the data from the new to ready state or loads the data to the main memory in gist 
                                
short term scheduler:the short term scheduler or cpu scheduler selects processes from the ready queue and loads them into the cpu for execution 
                      it takes the data from the ready to running state or loads the data to the cpu 

middle term scheduler : suspened ready and suspened block 
                        so if the memory is less 
                        swapping from the main memory to the disk  
                        swapping from the disk to the main memory
                
digree of multiprogramming depends upon the longterm scheduler 
dispatcher the dispatcher is the module that gives contorl of the cpu to the process selected by the short term scheduler ,now the short term scheduler determines that which process is to be loaded from ready to running but the dipatcher is the module that does it 
and this switching is called context switching and the time to switch is called a context switch overhead 

STRUCTURE OF AN OPERATING SYSTEM 
operating system differ in how their components are organised internally the internal organisation model of the os affects performance modularity and security ease of maintainance and scalability 
there are three types 
monilithic os:a monolithic os is a simplest design where the entire operating system runs in kernel mode as one large program .all system services like file system scheduling and memory management devices ,device drivers ,networking etc  share the same address space and execute without protection boundaries .

 ┌──────────────────────────────┐
 │       User Applications      │
 └──────────────────────────────┘
                │
                ▼
 ┌──────────────────────────────┐
 │        System Call API       │
 └──────────────────────────────┘
                │
                ▼
 ┌──────────────────────────────┐
 │       Monolithic Kernel      │
 │  (File system, scheduler,    │
 │   drivers, memory mgmt etc.) │
 └──────────────────────────────┘
                │
                ▼
 ┌──────────────────────────────┐
 │          Hardware            │
 └──────────────────────────────┘

layered os :in a layered os design the operating system is divided into level each built on top of the lower one .each layer provided a set of services to the higher level and uses serviecs of the lower level 
 ┌───────────────┐
 │  User Programs │   ← Layer 5
 └───────────────┘
        ▲
 ┌───────────────┐
 │  File System   │   ← Layer 4
 └───────────────┘
        ▲
 ┌───────────────┐
 │ Device Drivers │  ← Layer 3
 └───────────────┘
        ▲
 ┌───────────────┐
 │ Scheduling &   │  ← Layer 2
 │ Memory Mgmt    │
 └───────────────┘
        ▲
 ┌───────────────┐
 │  Hardware      │  ← Layer 0–1
 └───────────────┘


microkernel os :a microkernel os keeps only the most essential o s functionlity inside the kernel and everything else device drivers fiel system and network stack gui runs on user space services or servers 
microkernel contains 
low level memory management
cpu scheduling 
inter process communication 
basic device communication 
       ┌──────────────────────────────┐
       │      User Applications       │
       └──────────────────────────────┘
                   │
                   ▼
       ┌──────────────────────────────┐
       │  User-Level OS Services      │
       │ (File systems, drivers, GUI, │
       │  network, device managers)   │
       └──────────────────────────────┘
                   │   IPC messages
                   ▼
      ┌───────────────────────────────┐
      │        Microkernel            │
      │ (IPC, scheduling, memory mgmt)│
      └───────────────────────────────┘
                   │
                   ▼
           ┌─────────────┐
           │  Hardware    │
           └─────────────┘


virtual machines : the virtual machines is a software abstraction of physical hardware allowing mulitple operating system or processes to run independently on the same computer 

there are two type s
system virtual machine:provide a virtual hardware environment for running an entire os instance 
managed by vmm or hypervisor 

process virtual machine :provide enviroment to run a single program or language runtime 

***thread***
a thread is the smallest unit of processing that can be scheduled and executed by an operating system the main difference between a thread and a process is that a thread is a part of a process and a process is a collection of threads
a process is a program  in execution and a thread is a single sequence of execution within that process 

thread is the smallest component of a process or a light weight process
provide a wat to improve application preformance through parallelism
so rather than making copy for the same process we use multithreading 

so a thread has 
stack
data 
code 
heap

multithreading :multithreading is the ability of an os to support multiple concurrent paths of execution withing a single process .the multithreading defines how user level threads are mapped to kernel level threads

advantage of multithreading :responsiveness 
utilization of multiprocessor architecture 
fast context switch
resorce sharing 
communication 
types of thread 


user thread                                                           kernel thread
multithreading in user process                           multithreadin in kernel process
created without kernel intervention                      kernel itself is multithreaded 
context switching is very fast                           context switching is very slow 
(as no kernel interaction )                              (as kernel is involved )
if one thread is blocked the entire 
process will be blocked 
(as os is unaware that user process has thread           individual will be blocked 
so treatement will be like single process)
generic and run across os                                specific to os 
faster to create and manage                              slower to create and manage 


***scheduling ***
arrival time :time at which process enters a ready state 
burst time :amount of cpu time required by the process to complete its execution 
completion time :time at which process finishes execution 
turn around time :completion time minus arrival time or waiting time plus burst time
waiting time :turn around time +burst time 

process synchronization :as we understand ina multiprogramming enviroment a good number of process compete for limited number of resources 
concurrent access to shared data at some time may result in data inconsistency

race conidition :the condition in which the output of the process depends on the execution sequence of the process i.e. if we change the order of execution of different process with respect to other process teh output may change 

that is why we need some kind of synchronization to eliminate the posibility of race condition or data inconsistency

general structure of a process
initial section :where processi s accessing private resources 

entrysection :entry section is that part of code where each process request for permission to enter its critical section 

critical section :where process is accessing shared resources 

exit section :it is the section where a process will exit from its critical section 
 
 remainder section :remaining code 

 {
    initial section//unshared resources or personal data 
    entry section
    critical section
    exit section
    remainder section//unshared resources or personal data
 }
 mutual excusion :a process is said to be in mutual exclusion if it has access to only one resource at a time and the process in entry section are not allowed into the critical section 
        no two processes shoudl be present in the critical section at the same time i.e. only one process is allowed in the critical section at an instant of time 

progress :if no process is executing in the critical section than only those process which are not operating in the remainder section or initial section can compete to enter into the critical section and there should be no dead lock 

Bounded waiting :there exists a bound or limit on the number of times a proces is allowed to enter into the critical section before an process is allowed and no process should wait indefinitely to enter the critical section
                 so a process after a fixed no of times shall not be allowed into the critical section and the other process will be allowed a chance into the ciritical section 


solution to critical section problem 
we generally have the following solution to a ciritcal section problems:
1. two process solution :
using boolean variable turn 
using boolean array flag 
peterson solution 

2. operating system solution :
countins semaphore
binary semaphore

3. hardware solution :
test and set lock 
disable interrupts

there are 3 different idea to achieve valid solution in which some are invalid and some are valid 
1-using boolean variable turn:now when the turn is zero then the p 0 runs and for example the burst time p0  is completed in the first execution only but the flag is turnt to 1 so it will go to p1 but it wont run because the turn is not zero and it wont be able to enter into the critical section and cause starvation and thus the progress is not valid in this case 
p0()
{
  while (turn!=0);
  critical section 
  turn=1
  remainder section 

}
and p1()
{
  while (turn!=1);
  critical section 
  turn=0
  remainder section 
}
2-using boolean array flag
here we will use a boolean array flag with two cells where each cell is initialized to f 
so we will use a flag array and with the array we will be able to understand if the process wants to go to the critical section or not

3-peterson solution
here we can take as if both the turn and flag are there 
so the flag difines whether the process wants to go to the critical section or not
and the turn decides if the process is in critical section or not 
after we switch as if we did in case of the p0 then switch to p1 then the first time it will apprear as dead lock but when we try once again in the p0 then we can enter into the critical section thus the deadlock breaks 
eveyr process can enter into the critical section only once and only one process can enter into the critical section at a time and thus the progress is valid


if there are multipel semaphore involved in a critical section problem then the order should be same for a dead lock to not occur in the critical section problem 
for example 
s1      s2

s2      s1
this will not work as the order of wait is different between the two 
now if we take the order as

s1      s1
s2      s2
now the deadlock will not occur
 classical problems on synchronization 

1. producer consumer problem /bounder buffer problem 
2. reader writer problem 
3. dining philosopher problem

.producer consumer problem : there are two process producer and consumers producer produce information and put it into a buffer which have a cell that is consumed by a consumer 
.both producers and consumer can produce and consume only one article at a time

over flow :the overflow condidition is the producer produces enough info to be stored in the buffer but the consumer is not able to consume it
underflow :the underflow condidition is the consumer consumes the info from the buffer but the producer is not able to produce it and the buffer is empty 
when the producer is producing data and the consumer is trying to consume it at the same time then there are chances of collision and deadlock and thus this is a classical problem on synchronization

producer consumer problem needs to sort out three majour issues
