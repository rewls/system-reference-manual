# WRITE(3POSIX)

## PROLOG

- This manual page page is part of the POSIX Programmer's Manual.

- The Linux implementation of this interface may differ, or the interface may not be implemented on Linux

## NAME

- write on a file

## SYNOPSIS

```c
#include <unistd.h>

ssize_t write(int fildes, const void *buf, size_t nbyte);
```

## DESCRIPTION

- The write() function shall attempt to write nbyte bytes from the buffer pointed to by buf to the file associated with the open file descriptor, fildes.

- Before any action described below is taken, and if nbyte is zero and the file is a regular file, the write() function may detect and return errors as described below.

- In the absence of errors, or if error detection is not performed, the write() function shall return zero and have no other results.

- On a regular file or other file capable of seeking, the actual writing of data shall proceed from the position in the file indicated by the file offset associated with fildes.

- Before successful return from write(), the file offset shall be incremented by the number of bytes actually written.

- On a regular file, if the position of the last byte written is greater than or equal to the length of the file, the length of the file shall be set to this position plus one

- If the O_APPEND flag of the file status flags is set, the file offset shall be set to the end of the file prior to the end of the file prior to each write and no intervening file modification operation shall occur between changing the file offset and the write operation.

- If a write() requests that more bytes be written than there is room for, only as many bytes as there is room for shall be written, only as many bytes as there is room for shall be written.

- The next write of a non-zero number of bytes would give a failure return.

- After a write() to a regular file has successfully returned:

	- Any successful read() from each byte position in the file that was modified by that write shall return the data specified by the write() for that positio until such byte positions are again modified.

	- Any subsequent successful write() to the same byte position in the file shall overwrite that file data.

## RETURN VALUE

- Upon successful completion, these functions shall return the number of bytes actually written to the file associated with fildes.

- This number shall never be greater than nbyte.

- Otherwise, -1 shall be returned and errno set to indicate error.
