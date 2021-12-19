### Q1:Process Vs Thread
A process is the execution of a program.

Thread is an execution unit that is part of a process. A process can have multiple threads, all executing at the same time. 

The typical difference is that threads (of the same process) share memory space whileas processes are mostly isolated, they have their own memory space.

#### Q2: What is a thread pool?
A thread pool manages the pool of worker threads, it contains a queue that keeps tasks waiting to get executed.

A thread pool manages the collection of Runnable threads and worker threads execute Runnable from the queue.

java.util.concurrent.Executors provide implementation of java.util.concurrent.Executor interface to create the thread pool in java. Thread Pool Example program shows how to create and use Thread Pool in java.

#### Q3: During a thread's lifetime, what states can it have?
here are five states a thread can have: New, Runnable, Running, time_waiting/Blocked and Terminated.

#### Q4: What is a race condition? (definition + explanation + solution)
A race condition occurs when multiple concurrent threads race to be the first to run. If the winner was not the one that was supposed to run first, the code may exhibit unexpected behavior. The problem can be resolved with synchronization.

#### Q5: What is synchronization?
Synchronization forces threads to run one at a time to prevent a race condition or multiple threads trying to perform the same task.

#### Q6: synchronized block?
A synchronized block allows you to designate a particular portion of a method as synchronized. That is, only a single thread will be allowed to run until it completes

#### Q7. What is context switching
Context switching is where the current state of a thread or process is stored so the execution of that thread can be resumed at a later time. This enables a single CPU to manage multiple threads or processes.

#### Q8: what the thread scheduler is and its relationship to thread priority?
The thread scheduler is what allocates CPU time to threads and determines the order in which threads execute.

#### Q9: What is time slicing?
Time slicing is the process used by the thread scheduler to divide CPU time between the available active threads.

#### Q10: Why might you describe thread behavior as unpredictable? (Reason + elaborate + aftermath)
Because thread scheduling is determined by the CPU, different CPUs may give priority to different threads. This means there is a chance two CPUs will not run your threads in the same order, creating unpredictability in your code execution.

#### Q11：Explain the busy spin technique and why you might use it.
usy spin is where you pause a thread by making it run an empty loop for a certain period. Unlike other methods like wait() or sleep(), a busy spin doesn't give up CPU control and therefore preserves CPU cache.

#### Q12. busy spin technique and why you might use it.
Busy spin is where you pause a thread by making it run an empty loop for a certain period. Unlike other methods like wait() or sleep(), a busy spin doesn't give up CPU control and therefore preserves CPU cache.

#### Q13. thread starvation
Threads are blocked indefinately waiting to enter a synchronized bloc. Thread starvation is when there is insufficient CPU capacity to execute a thread. This can happen with low-priority threads, or threads that are demoted in favor of other threads.

#### Q14: Can you start a thread twice?
nce a thread has been executed, it is considered dead. You cannot restart a dead thread.

#### Q15: Can you describe a deadlock situation?

Example: "A deadlock situation is where multiple threads are waiting on each other to release CPU resources so they can run. This can happen when, for example, a single thread has exclusive priority but needs resources from a waiting thread, or all the threads are depending on one another to release needed resources."

#### Q16: What happens when a livelock occurs?
A livelock is similar to a deadlock situation, except with a livelock, the state of the threads change without ever making progress. For example, if all the threads are caught in infinite loops.

#### Q17: the difference between the wait() and sleep()
The wait() method pauses a thread and waits until there are notify() or notifyAll() method calls from other threads. The sleep() method pauses for a given period, allowing other threads to run, after which it resumes execution.

#### Q18: daemon thread
A daemon thread is a low-priority thread. It may provide background services or support to the other threads, e.g. GC

#### Q19: Why must you override the run() method in your thread class?
If we don't overridden the run() method, the thread will not do anything.

#### Q20:  How might you achieve thread safety?
You can achieve thread safety through several techniques, including synchronization, using the Volatile keyword or using atomic wrapper classes.

#### Q21: What is the difference between synchronous and asynchronous programming?
Synchronous programming is when a single thread is assigned a single task. Asynchronous programming is when a single task is shared between multiple threads.

### How to create a thread
runnable interface, extends Thread, Thread pool, callable(pros, can throw exceptions, can return generics)

### runnable 
cons: 
1. return void
2. it can not catch exception

### program vs process vs thread
| program | process |
|---------| ---------|
|static code| excution of program |
|hard drive| OS will assign memory for each process |
|classloader load it to JVM so it will become process| |


