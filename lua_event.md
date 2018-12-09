Name | Version / Update | Dependencies | Description
-- | -- | -- | --
[luaevent](https://luarocks.org/modules/harningt/luaevent) | 0.4.5-1 (37 days ago) | lua >= 5.1, <= 5.3, libevent >= 1.4, LuaSocket | libevent binding for Lua. With a higher level wrapper mimicking **copas**.
[lua-ev](https://luarocks.org/modules/brimworks/lua-ev) | v1.4-1 (3 years ago) | lua >= 5.1, libev >= 3.7 | Lua 5.1 interface to libev
[xjdrew/levent](https://github.com/xjdrew/levent) | 2 months ago | Lua >= 5.2, <= 5.3, libev 4.22 | a lua concurrency networking library inspired by [gevent](http://www.gevent.org/).
[luv](https://luarocks.org/modules/creationix/luv) | 1.22.0-1 (113 days ago) | lua >= 5.1, libuv >= 1.10? | Bare libuv bindings for lua. Part of the [luvit](http://luvit.io/) project
[lluv](https://luarocks.org/modules/moteus/lluv) | 0.1.9-1 (217 days ago) | lua >= 5.1, < 5.4, libuv >= 1.0.0 | Lua low-level binding to libuv
[richardhundt/luv](https://github.com/richardhundt/luv) | 6 years ago | Lua  >= 5.1, libuv 0.9 | libuv bindings for Lua
[pguillory/luajit-libuv](https://github.com/pguillory/luajit-libuv) | 4 years ago | LuaJIT, libuv | LuaJIT FFI binding for libuv

### Multithreading
> At the programming language level:
  - Channel (interprocess communication and synchronization via message passing)
  - Coroutine (non-preemptive multitasking)
  - Futures and promises (synchronizing program execution)
> At the operating system level:
  - Computer multitasking
    - [cooperative multitasking](https://en.wikipedia.org/wiki/Cooperative_multitasking)
    - [preemptive multitasking](https://en.wikipedia.org/wiki/Preemption_(computing)#PREEMPTIVE)
  - [Process](https://en.wikipedia.org/wiki/Process_(computing))
    - Threads (are scheduled preemptively)
    > are processes that run in the same memory context and share other resources with their parent processes.
    > Share all their memory space for cooperation processes to exchange data
    - Fibers (are scheduled cooperatively)
    > Cooperatively scheduled user threads. Like threads, fibers share address space but are threads that not run in parallel.
    - [Green threads](https://en.wikipedia.org/wiki/Green_threads)
    > are threads that are scheduled by a runtime library or virtual machine (VM) instead of natively by the underlying operating system.
    > Green threads emulate multithreaded environments without relying on any native OS capabilities, enabling them to work in environments that do not have native thread support.


```
    Preemptive, shared state:
        1. Custom Lua interpreter:
            - [LuaThread] (5.0/5.1) - threads share the same Lua state (synchronized); uses native OS threads (preemptive)

    Preemptive
        2. State per thread (no data exchange):
            - [lua-llthreads] - provides a very simple interface to pthreads. Each thread has an independent Lua state.
            - [lua-llthreads2] - drop-in replacement for [lua-llthreads] library with several additional functionality.

    Preemptive, message passing:
        3. State per thread + Copying based message passing: 
            - [Lanes] (5.1/5.2) - completely separate Lua states, one per thread, with asynchronous message passing
            - [lua-zmq] - a binding to ZeroMQ[3], the high-performance message queue library with a socket-style API.
            - [Effil] (5.1, 5.2, 5.3, LuaJIT) - thread safe tables + metatables, threads can be paused/resumed and canceled, FIFO channels.
              - Threads in independent Lua states. [transmit data between threads (Lua interpreter states) using effil.channel]
```
