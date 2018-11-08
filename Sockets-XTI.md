
[Berkeley Socket](https://en.wikipedia.org/wiki/Berkeley_sockets) (also known as BSD sockets) / [POSIX Sockets](http://pubs.opengroup.org/onlinepubs/9699919799/idx/networking.html) Interface

Sockets Headers:
* <fcntl.h> - file control options
* <net/if.h> - sockets local interfaces
* <sys/socket.h> - Main (Berkeley) Sockets Header
* <sys/stat.h> - data returned by the stat() function.
* <sys/uio.h> - definitions for scatter/gather I/O
* <sys/un.h> - definitions for UNIX-domain sockets
  - Use of Sockets for Local UNIX Connections

IP Address Resolution Headers:
* <arpa/inet.h> - definitions for internet operations
* <netdb.h> - definitions for network database operations
* <netinet/in.h> - Internet Protocol family (for IPv4 and IPv6)
  - Use of Sockets over Internet Protocols based on IPv4 and IPv6
  - Defines Internet protocol and address family (part of Berkeley sockets)
* <netinet/tcp.h> - Definitions for the Internet Transmission Control Protocol
  - Additional TCP control options (part of Berkeley sockets)
* <unistd.h> - standard symbolic constants and types

```
Socket socket = getSocket(type = "TCP") -- creation of a socket
connect(socket, address = "1.2.3.4", port = "80") -- connecting to remote host
send(socket, "Hello, world!") -- sending the string
close(socket) -- and finally closing the socket
```

Example [system calls](http://myriabit.com/ljsyscall/fosdem2013/?full#8):
```
local s = S.socket("inet", "stream, nonblock")
s:setsockopt("socket", "reuseaddr", true)
local sa = S.t.sockaddr_in(8000, "127.0.0.1")
s:bind(sa)
s:listen(128)
local ep = S.epoll_create()
ep:epoll_ctl("add", s, "in")
```

[X/Open Transport Interface](https://en.wikipedia.org/wiki/X/Open_Transport_Interface) (XTI)

> XTI provides similar functionality as the Berkeley sockets interface.
>
> - It is protocol independent in contrast to the socket interface which is heavily biased toward the [Internet Protocols](https://en.wikipedia.org/wiki/Internet_Protocol_Suite).
>
> - Is a transport service definition adhering to the [OSI model](https://en.wikipedia.org/wiki/OSI_model).
>
> XTI is now considered to be obsolete, so writers of new applications using the [Internet Protocol Suite (IPS)](https://en.wikipedia.org/wiki/Internet_Protocol_Suite) are recommended to use Sockets rather than XTI.
- [The Single UNIX® Specification (SUS), Version 2 (1997): Networking Services, Issue 5](http://pubs.opengroup.org/onlinepubs/7908799/xnsix.html)
- [Networking Services (XNS), Issue 5.2 Draft 2.0 (1999)](http://pubs.opengroup.org/onlinepubs/009619199/)
