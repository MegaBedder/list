```c
// https://lxr.room11.org/xref/php-src%407.3/main/network.c#287
/* Connect to a remote host using an interruptible connect with optional timeout.
 * Optionally, the connect can be made asynchronously, which will implicitly
 * enable non-blocking mode on the socket.
 * Returns the connected (or connecting) socket, or -1 on failure.
 */
PHPAPI php_socket_t php_network_connect_socket_to_host(
        const char *host,
        unsigned short port,
		int socktype,
        int asynchronous,
        struct timeval *timeout,
        zend_string **error_string,
		int *error_code,
        char *bindto,
        unsigned short bindport,
        long sockopts
		);

// https://lxr.room11.org/xref/php-src%407.3/main/network.c#759
/* Connect to a socket using an interruptible connect with optional timeout.
 * Optionally, the connect can be made asynchronously, which will implicitly
 * enable non-blocking mode on the socket.
 */
PHPAPI int php_network_connect_socket(
        php_socket_t sockfd,
		const struct sockaddr *addr,
		socklen_t addrlen,
		int asynchronous,
		struct timeval *timeout,
		zend_string **error_string,
		int *error_code
        );
```

```c
// https://lxr.room11.org/xref/php-src%407.3/main/network.c#1094
/* deprecated. Convert a socket into a stream. */
PHPAPI php_stream *_php_stream_sock_open_from_socket(
        php_socket_t socket,
        const char *persistent_id STREAMS_DC
        );

// https://lxr.room11.org/xref/php-src%407.3/main/network.c#1119
/* Open a connection to a host and return a stream. */
PHPAPI php_stream *_php_stream_sock_open_host(
        const char *host,
        unsigned short port,
		int socktype,
        struct timeval *timeout,
        const char *persistent_id STREAMS_DC
        );
```
