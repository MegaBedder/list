### Concurrency
Multitasking: 
- Lua's single-threaded coroutines
- Multiple pre-emptive threads

---

Reference Manual

- Coroutines
> user-level cooperative threads
>
> cooperative (non-preemptive) multitasking
>
> collaborative (non-preemptive) multithreading

Lua supports coroutines, also called collaborative multithreading. A coroutine in Lua represents an independent thread of execution. Unlike threads in multithread systems, however, a coroutine only suspends its execution by explicitly calling a yield function.

---

> Lua offers true, asymmetric coroutines.
> coroutines are a kind of collaborative (non-preemptive) multithreading.
>
> Each coroutine is equivalent to a thread.
> However, unlike "real" multithreading, coroutines are non preemptive.
> While a coroutine is running, it cannot be stopped from the outside.
> It only suspends execution when it explicitly requests so (through a call to yield).

PIL
> A coroutine is similar to a thread (in the sense of multithreading):
a line of execution, with its own stack, its own local variables, and its own instruction pointer; but sharing global variables and mostly anything else with other coroutines.

> The main difference between threads and coroutines is that, conceptually (or literally, in a multiprocessor machine), a program with threads runs several threads concurrently.

> Coroutines, on the other hand, are collaborative: A program with coroutines is, at any given time, running only one of its coroutines and this running coroutine only suspends its execution when it explicitly requests to be suspended.
