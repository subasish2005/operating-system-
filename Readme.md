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