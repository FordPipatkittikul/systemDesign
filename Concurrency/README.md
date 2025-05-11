# Concurrency != Parallelism

- Parallelism

Definition: Parallelism is about actually executing multiple tasks at the same time, typically using multiple processors or cores.

Example: Like having multiple waiters, each serving a table at the same time.

Focus: Doing multiple tasks simultaneously.

- Concurrency - providing an illusion of doing more than one thing at the same time.

Definition: Concurrency is about dealing with multiple tasks at the same time conceptually. It doesn’t necessarily mean they are running at the same instant, just that progress is being made on all of them.

Example: Like a single waiter managing several tables by quickly switching between them. Only one task is being executed at a time, but the work seems simultaneous because of rapid context switching.

Focus: Managing multiple tasks by switching.

# Processes

- A process is an independent program in execution.
- Each process has its own memory space and resources.
- Processes do not share memory (communication between processes requires Inter-Process Communication like File, signal, sockets, pipes)

# Threads

- A thread is a lightweight unit of execution within a process.
- Threads share the same memory of their parent process.
- Easier to create and manage than processes.

# Thread Pools

- A thread pool is a collection of pre-created, reusable threads.
- Instead of creating a new thread every time, tasks are assigned to threads in the pool.
- Improves performance by reducing the overhead of creating and destroying threads repeatedly.