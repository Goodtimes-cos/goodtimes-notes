---
published: true
subtitle:
date: 2024-06-25
tags: 
---

# Concurrency and Context Switching
At a fundamental level, concurrency is about two or more separate activities
happening at the same time.

It encompasses both parallelism, using multiple processing units
to execute operations in parallel, as well as task-switching and threading.

## What is a thread?
A thread is an execution context, which is all the information a CPU needs to execute a stream of instructions. The CPU gives the illusion that it's doing
multiple computations at the same time.

Technically, an execution context consists of values of the CPU's registers. A process is a bunch of resources associated with a computation, such as pages, file descriptors and security credentials, which can have many threads.

Please read the following on execution context: [Threads - roll your own](https://people.kth.se/~johanmon/ose/assignments/contexts.pdf).

## Concurrency: Multiple processes
We divide the application into multiple, separate, single-threaded processes
that run simultaneously. These processes can pass messages via normal
channels, like signals, sockets, files and pipes.

The downside of using this method is that communication is often difficult between separate processes, as they don't share the same memory, and
slow due to OS protections. However, it's also safer to write concurrent threads with processes, rather than threads.

Another advantage is that you can run the separate processes on
distinct machines connected over a network.

## Concurrency: Multiple threads
We run multiple threads in a single process, where each thread runs
independently of the others. All threads share the same address space,
making communication simple. Furthermore, the associated overhead is far smaller than using multiple processes, as protections are fewer.

## Why would you not use concurrency?
When it's not worth the cost:
- Often multi-threaded code is harder to write and maintain,
- Performance gains may not be sufficient,
- Threads are in limited supply due to kernel and stack resources,
- The more threads you have running, the more context switching the OS has to do, which may reduce the overall performance of the application.