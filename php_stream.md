
Name | scheme://
-- | --
[PHP Stream Socket Transports](http://php.net/manual/en/transports.php) | tcp, udp, unix, udg, ssl, sslv3, tls, tlsv1.0, tlsv1.1, tlsv1.2
[PHP Stream Wrappers](http://php.net/manual/en/wrappers.php) | https, ftps, compress.zlib, compress.bzip2, php, file, glob, data, http, ftp, phar, zip
[PHP Stream Context](http://php.net/manual/en/stream.contexts.php) | socket, http, ftp, ssl, phar, zip, Context parameters: notification
[PHP Stream Filters](http://php.net/manual/en/filters.php) | zlib.*, bzip2.*, convert.iconv.*, string.strip_tags, convert.*, consumed, dechunk


**[PHP Streams](http://php.net/manual/en/intro.stream.php)**: [stream/(wrapper)/(context)/(filter)]
> Es una API extensible que permite que se registren nuevos streams en tiempo de ejecución (run-time).
>
> Presenta un enfoque unificado para operaciones comunes para el manejo de archivos y sockets en PHP.
>
> Permite que su script acceda a archivos, sockets, URL (socket transports y wrappers), memoria (filters) y objetos definidos por el script ([streamwrapper](http://php.net/manual/en/class.streamwrapper.php) object, URL wrapper implemented as a PHP class).

- **PHP Stream**: Representar fuentes de datos transmisibles (streamable data sources).
- **PHP Stream Wrapper**: Proporcionar soporte para recuperar datos y metadatos de las URL, mediante un wrapper a la API Stream.
  - **Stream Contexts**: Ajustar el comportamiento del wrapper, mediante el método ***stream_open*** del objeto ***Stream Wrapper***.
- **Stream Filters**: Un filtro es una pieza final de código que puede manipular la información que está siendo leída o escrita en un flujo.
  - Cualquier stream, una vez abierto, pueden tener filtros aplicados, que procesan datos a medida que se leen / escriben en el Stream.
    - **Stream Buckets**: son una abstracción que unifica fundamentalmente diferentes tipos de datos mediante un contenedor de datos.
    - **Stream Brigades**: sirve para permitir una manipulación (flexible y eficiente) de datos, y es la unidad que pasa a su filtro y desde él.
  - Al usar Buckets y Brigades en lugar de un simple buffer, simplemente podemos reemplazar los caracteres in situ, sin asignar ni copiar ningún bloque grande de memoria.
  - En lugar de mover/copiar grandes bloques de datos, solo estamos manipulando (mediante filtros) punteros en un bloque existente.


Name | Functions | Client | Server | Note
-- | -- | -- | -- | --
PHP Stream FileSystem | fopen, file_get_contents | X | - | URL style wrappers (php, file, glob, data, [http](https://lxr.room11.org/xref/php-src%407.3/ext/standard/http_fopen_wrapper.c#109), [ftp](https://lxr.room11.org/xref/php-src%407.3/ext/standard/ftp_fopen_wrapper.c#413))
PHP Stream FileSystem | SplFileObject::__construct(), SplFileInfo::openFile() | X | - | URL style wrappers, object oriented interface for a file.
PHP Stream Socket | [(p)fsockopen](https://lxr.room11.org/xref/php-src%407.3/ext/standard/fsock.c#php_fsockopen_stream) | X | - | URL style [socket transports](https://lxr.room11.org/xref/php-src%407.3/main/streams/transports.c#54)
PHP Stream Socket | [stream_socket_](https://lxr.room11.org/xref/php-src%407.3/ext/standard/streamsfuncs.c#89)* | X | X | URL style [socket transports](https://lxr.room11.org/xref/php-src%407.3/main/streams/transports.c#54)
Socket extension |socket_* | X | X | Low-level interface to the socket communication functions based on the popular BSD sockets.
cURL extension | curl_* | X | - | libcurl, that allows you to connect and communicate to many different types of servers with many different types of protocols.
pecl/http | http\\* | X | - | Extended HTTP support.
Swoole extension | Swoole\\* | X | X | Swoole is a high-performance networking framework using an event-driven, asynchronous, non-blocking I/O model. It can be used to develop high-performance, scalable, concurrent TCP, UDP, Unix socket, HTTP, Websocket services.


[Definition](http://php.net/manual/en/resource.php) | Created By | Used By | Destroyed By | [Resource Type](http://php.net/manual/en/function.get-resource-type.php)
-- | -- | -- | -- | --
[Socket extension](http://php.net/manual/en/intro.sockets.php) | socket_create() | socket_accept(), socket_bind(), socket_connect(), socket_listen(), socket_read(), socket_write() | socket_close() | Socket
[cURL extension](http://php.net/manual/en/intro.curl.php) | curl_init() | curl_setopt(), curl_exec() | curl_close() | curl
[pecl/http](https://github.com/m6w6/ext-http) | http\Client::__construct() | http\Client\Request() | -- | --
[Swoole extension](http://php.net/manual/en/intro.swoole.php) | Swoole\Http\Client | Swoole\Http\Request, Swoole\Http\Response | Swoole\Http\Client::close | --
-- | -- | -- | -- | i/o vector
Dir handle ([Directories](http://php.net/manual/en/book.dir.php)) | opendir() | readdir(), rewinddir() | closedir() | stream (dir)
File handle ([Filesystem](http://php.net/manual/en/book.filesystem.php)) | fopen(), tmpfile() | **feof()**, fflush(), fgetc(), fgetcsv(), fgets(), fgetss(), **flock()**, fpassthru(), fputs(), fwrite(), fread(), **fseek(), ftell(), fstat(), ftruncate(), set_file_buffer(), rewind()** | fclose() | stream (file)
Process handle ([Program Execution](http://php.net/manual/en/intro.exec.php)) | [popen()](http://php.net/manual/en/function.popen.php) | **feof()**, fflush(), fgetc(), fgetcsv(), fgets(), fgetss(), fpassthru(), fputs(), fwrite(), fread() | pclose() | stream (pipe)
Socket handle ([Network](http://php.net/manual/en/intro.network.php)) | fsockopen(), pfsockopen() | fflush(), fgetc(), fgetcsv(), fgets(), fgetss(), fpassthru(), fputs(), fwrite(), fread() | fclose() | stream (socket)
