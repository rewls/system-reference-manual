# STDIN(3)

## NAME

- standard - standard I/O streams

## SYNOPSIS

```c
#include <stdio.h>

extern FILE *stdin;
```

## DESCRIPTION

- A file with associated buffering is called a stream and is declared to be a pointer to a defined type FILE.

- The fopen() function shall create certain descriptive data for a stream and return a pointer to designate the stream in all further transactions.

- Normally, there are three open streams with constant pointers declared in the <stdio.h> header and associated with the standard open files.

- At program start-up, three streams shall be predefined and need not be opened explicitly: standard input, standard output, standard error.

- The standard input and standard output streams are fully buffered if and only if the stream can be determined not to refer to an interactive device.

- The following symbolic values in <unistd.h> define the file descriptors that shall be associated with the C-language stdin, stdout, and stderr when the application is started:

    - STDIN_FILENO: Standard input value, stdin.

        - Its value is 0.

    - STDOUT_FILENO: Standard output value, stdout.

        - Its value is 1.

    - STDERR_FILENO: Standard error value, stderr.

        - Its value is 2.m:w
