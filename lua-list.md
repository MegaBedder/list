Data formats / Serialization
- CSV (Comma-Separated-Values)
- JSON
- YAML - encoder/decoder
- [msgpack](https://github.com/kieselsteini/msgpack) - A MessagePack implementation for Lua 5.3 
- [lua-MessagePack](https://github.com/catwell/lua-MessagePack) - a pure Lua (5.1 & 5.3) implementation (spec v5)
- [lua-msgpack](https://github.com/kengonakajima/lua-msgpack) - msgpack implementation by pure Lua 5.1 works without LuajJIT and FFI.
- [lua-msgpack-native](https://github.com/kengonakajima/lua-msgpack-native) - Faster implementation of MessagePack for Lua runtime (Lua-specific C implementation)
- [lua-cmsgpack](https://github.com/antirez/lua-cmsgpack) - A self contained Lua MessagePack C implementation.
- [luajit-msgpack-pure](https://github.com/catwell/luajit-msgpack-pure) - MessagePack for LuaJIT (using FFI, no bindings, V4 API)

Databases
- SQLite
- MySQL / MariaDB
- PostgreSQL

Date and time
- icu-date - LuaJIT FFI bindings to ICU date and time library

Development support
- benchmark
- Debug - Tools to print call traces, insert watchpoints, inspect Lua objects
- Functional programming primitives
- logger
- strict - Module to prohibit use of undeclared Lua variables
- checks - Easy, terse, readable and fast check of the Lua functions + argument types
- tap - Tools to write nice unit tests conforming to Test Anything Protocol
- lrexlib - Regular expression library binding (PCRE flavour)
- lua-term - Terminal manipulation module
- LPeg - Parsing Expression Grammars library
- argparse - Feature-rich command-line argument parser for Lua

I18n
- iconv - Convert data between character sets

Miscellaneous
- 

Networking
- HTTP
- WebSocket
- SMTP

Operating systems/Interfaces
- POSIX APIs
- File I/O
- OS Funtions
- Socket I/O

-----------------------------

### Affecting Lua's Behaviour
- Data Structures
- Classes/Objects
- Error Handling
- Filter
- Function Handling
- Output Control
- Reflection
- Streams
- Sessions
- Variable handling

### Command Line Specific Extensions
- Ncurses — Ncurses Terminal Screen Control
- Newt (libnewt) - a programming library for color text mode, widget based user interfaces. 
- Readline — GNU Readline

### Compression and Archive
- Bzip2
- LZF
- Rar — Rar Archiving
- Zip
- Zlib — Zlib Compression

### Cryptography Extensions
- CSPRNG
- Hash — HASH Message Digest Framework
- Mhash
- OpenSSL
- Password Hashing
- Sodium

### Database Extensions
- PDO
- SQLite3

### Date and Time Related Extensions
- Date/Time
- Calendar

### File System Related Extensions
- Fileinfo
- Directories

### Human Language and Character Encoding Support
- iconv (GNU libiconv)
- intl (ICU - International Components for Unicode) — Internationalization Functions 
- Multibyte String (Unicode)

### Image Processing and Generation
- Cairo
- Exif — Exchangeable image information
- GD (libgd) — Image Processing and GD
- Gmagick
- ImageMagick — Image Processing

### Mail Related Extensions
- SMTP
- IMAP
- POP3
- NNTP

### Mathematical Extensions
- BC Math (libbcmath) — BCMath Arbitrary Precision Mathematics
- GMP (gmplib) — GNU Multiple Precision

### Process Control Extensions and System program execution
- libeio
- libev
- libevent
- PCNTL — Process Control
- POSIX
- pthreads (and pthreads-win32)
- Shared Memory (shmop)

### Text Processing
- BBCode — Bulletin Board Code
- CommonMark
- Parle — Parsing and lexing
- PCRE — Regular Expressions (Perl-Compatible)
- POSIX Regex — Regular Expression (POSIX Extended)
- Strings

### Variable and Type Related Extensions
- Ctype — Character type checking

### Web Services
- OAuth
- REST
- SOAP
- XML-RPC

### Windows Only Extensions
- COM — COM and .Net (Windows)
- DCOM

### XML Manipulation
- DOM
- libXML

### GUI Extensions
- [libui](https://github.com/andlabs/libui)

### Network
- URLs
- JSON
- Sockets
- FTP
