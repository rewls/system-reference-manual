# STRCAT(3)

## NAME

- strcat, strncat - concatenate two strings

## SYNOPSIS

```c
#include <string.h>

char *strcat(char *dest, const char *src);

char *strncat(char *dest, const char *src, size_t n);
```

## DESCRIPTION

- The strcat() function appends the src string to the dest string, overwriting the terminating null byte at the end of dest, and then adds a terminating null byte.

- The strings may not overlap, and the dest string must have enough space for the result.

- The strncat() function is similar, except that

	- it will use at most n bytes from src; and

	- src does not need to be null-terminated if it contains n or more bytes.

- As with strcat(), the resulting string in dest is always null-terminated.
