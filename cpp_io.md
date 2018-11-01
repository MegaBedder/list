C++ includes two input/output libraries:

## C-style I/O functions
> C++ also includes the input/output functions defined by C.

Name | Description
-- | --
fopen, fclose, fflush | File access
fread, fwrite | Direct input/output
fgetc, fgets, fputc, fputs | Unformatted input/output
scanf, fscanf, printf, fprintf | Formatted input/output
ftell, fgetpos, fseek, fsetpos, rewind | File positioning
feof | Error handling
rename, tmpfile | Operations on files

## stream-based I/O library
> The stream-based input/output library is organized around abstract input/output devices.
>
> These abstract devices allow the same code to handle input/output to files, memory streams, or custom adaptor devices that perform arbitrary operations (e.g. compression) on the fly.

Name | Description
-- | --
ios | Abstraction
fstream | File I/O implementation
sstream | String I/O implementation
strstream [deprecated] | Array I/O implementations
syncstream | Synchronized output

### I/O Manipulators
> The stream-based I/O library uses I/O manipulators to control how streams behave.
>
> Manipulators are helper functions that make it possible to control input/output streams.

Name | Description
-- | --
dec, hex, oct | changes the base used for integer I/O
quoted | inserts and extracts quoted strings with embedded spaces 
