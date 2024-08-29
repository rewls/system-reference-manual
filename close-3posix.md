# CLOSE(3POSIX)

## PROLOG

- This manual page is part of the POSIX Programmer's Manual.

- The Linux implementation of this interface may differ, or the interface may not be implemented on Linux.

## NAME

- close a file descriptor

## SYNOPSIS

```c
#include <uistd.h>

int close(int filedes);
```

## DESCRIPTION

- The close() function shall deallocate the file descriptor indicated by fildes.

- To deallocate means to make the file descriptor available for return by subsequent calls to open() or other functions that allocate file descriptors.

- All outstanding record locks owned by the process on the file associated with the file descriptor shall be removed.

- When all file descriptors associated with a open file description have been closed, the open file description shall be freed.

- If the link count of the file is 0, when all file descriptors associated with the file are closed, the space occupied by the file shall be freed and the file shall no longer be accessible.

## RETURN VALUE

- Upon successful completion, 0 shall be returned; otherwise, -1 shall be returned and errno set to indicate the error.
