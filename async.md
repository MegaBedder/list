- a batteries-included event loop
- a preemptive scheduler

--- | --- |
--- | --- |
[Futures](http://aturon.github.io/blog/2016/08/11/futures/) | the underlying model |
[how futures are currently used](https://tokio.rs/docs/getting-started/hello-world/) | without async/await syntax
[async/await](https://github.com/rust-lang/rfcs/blob/master/text/2394-async_await.md) [[examples]](https://github.com/alexcrichton/futures-await) [[blog]](http://aturon.github.io/2018/04/24/async-borrowing/) | is syntax sugar over futures that allows you to write code in the usual
the mechanics behind [how async/await works](https://boats.gitlab.io/blog/) | read all posts titled async/await
[asynchronous programming in Rust](https://aturon.github.io/apr/) | Async in Rust: what you need to know
[asyncio](https://docs.python.org/3/library/asyncio.html) | Python Asynchronous I/O
[greenlet](https://github.com/python-greenlet/greenlet) | Lightweight in-process concurrent programming
[cqueues](http://25thandclement.com/~william/projects/cqueues.html) [[example]](https://github.com/RussellHaley/lua-http-endpoints) [[wiki]](https://github.com/wahern/cqueues/wiki) | a type of event loop for Lua. It doesn't use callbacks, instead you communicate with an event controller by the yielding and resumption of Lua coroutines
[lua-sched](https://github.com/starwing/luasched) | toy coroutine scheduler project
[Copas](http://keplerproject.github.io/copas/) | Non-blocking single threaded network socket library
[Lua and preemptive scheduling for coroutines](http://lua-users.org/lists/lua-l/2013-03/msg00904.html) | ===
[lua-handlers](http://lua-users.org/lists/lua-l/2010-12/msg01156.html) | async tcp/udp sockets and HTTP requests.
[coroutines vs futures and generators](http://lua-users.org/lists/lua-l/2015-05/msg00296.html) | ===
[Async/await for ECMAScript](https://github.com/tc39/ecmascript-asyncawait) | ===
[The only bad thing about ES7 async/await](https://codeplanet.io/the-only-bad-thing-about-es7-asyncawait/) |  async/await pattern to perform work in serial which could have been parallelized
[Asynchronous Programming with Async and Await](https://docs.microsoft.com/en-us/previous-versions/hh191443(v=vs.140)) | C# and Visual Basic
[Async/Await - Best Practices in Asynchronous Programming](https://msdn.microsoft.com/en-us/magazine/jj991977.aspx) | ===
