# READ(3POSIX)

## PROLOG

- This manual page is part of the POSIX Programmer's Manual.

- The Linux implementation of this interface may differ, or the interface may not be implemented on Linux.

## NAME

- read from a file

## SYNOPSIS

```c
#include <unistd.h>

ssize_t read(int fildes, void *buf, size_t nbyte);
```

## DESCRIPTION

- The read() function shall attempt to read nbytes bytes from the file associated with the open file descriptor, filedes, into the buffer pointed to by buf.

- The behavior of multiple concurrent reads on the same pipe, FIFO, or terminal device is unspecified.

- Before any action described below is taken, and if nbyte is zero, the read() functio may detect and return errors as described below.

- In the absence of errors, or if error detection is not performed, the read() function shall return zero and have no other results.

- On files that support seeking (for example, a regular file), the read() shall start at a position in the file given by the file offset associated with fildes.

- The file offset shall be incremented by the number of bytes actually read.

- No data transfer shall occur past the current end-of-file.

- If the starting position is at or after the end-of-file, 0 shall be returned.

- The read() function reads data previously written to a file.

- If any portion of a regular file prior to the ed-of-file has not been written, read() shall return bytes with value 0.

- Upon successful completion, where nbyte is greater than 0, read() shall mark for update last data access timestamp of the file, and shall return the number of bytes read.

- For regular files,  no data transfer shall occur past the offset maximum established in the open file description associated with filedes.

- A read() from a STREAMS file can read data in three different modes: byte-stream mode, message-nodiscard mode, and message-discard mode.

- The default shall be byte-stream mode.

- In byte-stream mode, read() shall retrieve data from the STREAM until as many bytes as were requested are transferred, or until there is no more data to be retrieved.

- Byte-stream mode ignores message boundaries.

- How read() handles zero-byte STREAMS messages is determined by the current read mode setting.

- In byte-stream mode, read() shall accept data until is has read nbyte bytes, or until there is no more data to read, or until a zero-byte message block is encountered.

- The read() function shall then return the number of bytes read, and place the zero-byte message back on the STREAM to be retrieved by the next read(), getmsg(), or getpmsg().

## RETURN VALUE

- Upon successful completion, these functions shall return a non-negative integer indicating the number of bytes actually read.

- Otherwise, the functions shall return -1 and set errno to indicate the error.

## EXAMPLES

### Reading Data into a Buffer

```c
#include <sys/types.h>
#include <unistd.h>
...
char buf[20];
size_t nbytes;
ssize_t bytes_read;
int fd;
...
nbytes = sizeof(buf);
bytes_read = read(fd, buf, nbytes)
```
