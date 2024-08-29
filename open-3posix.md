# OPEN(3POSIX)

## PROLOG

- This manual page is part of the POSIX Programmer's Manual.

- The Linux implementation of this iterface may differ, or the interface may not be implemented on Linux.

## NAME

- open file

## SYNOPSIS

```c
#include <sys/stat.h>
#include <fcntl.h>

int open(const char *path, int oflag, ...);
```

## DESCRIPTION

- The open() function shall establish the connection between a file and a file descriptor.

- It shall create an ope nfile description that refers to a file and file descriptor that refers to that open file description.

- The file descriptor is used by other I/O functions to refer to that file.

- The path argument points to a pathname naming the file.

- The open() function shall return a file adescriptor for the named file, allocated as described in Section 2.14, File Descriptor Allocation.

- The open file description is new, and therefore the file descriptor shall not share it with any other process in the system.

- The file offset used to mark the current position with the file shall be set to the beginning of the file.

- The file status flags and file access modes of the open file description shall be set according to the value of oflag.

- Values for oflag are constructed by a bitwise-inclusive OR of flags from the following list, defined in <fcntl.h>.

- Applications shall specify exactly one of the first five values (file access modes) below in the value of oflag:

	- `O_RDONLY`: Open for reading only.

## RETURN VALUE

- Upon successful completion, these functions shall open the file and return a non-negative integer representing the file descriptor.

- Otherwise, these functions shall return -1 and set errno to indicate the error.

- If -1 is returned, no files shall be created or modified.
