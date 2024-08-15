# STRLCPY(3bsd)

## NAME

- strlcpy, strlcat - size-bounded string copying and concatenation

## LIBRARY

- Utility functions from BSD systems (libbsd, -lbsd)

## SYNOPSIS

```c
#include <string.h>

size_t
strlcpy(char *dst, const char *src, size_t size);

size_t
strlcat(char *dst, const char *src, size_t size);
```

## DESCRIPTION

- They are designed to be safer, more consistent, and less error prone replacements for strncpy(3) and strncat(3).

- Unlike those functios strlcpy() and strlcat() take the full size of the buffer and guarantee to NUL-terminate the result.

- strlcpy() and strlcat() only operate on true "C" strings.

- The strlcpy() function copies up to size - 1 characters from the NUL-terminated string src to dst, NUL-terminating the result.

- The strlcat() function appends the NUL-terminated string src to the end of dst.

- It will append at most size -strlen(dst) - 1 bytes, NUL-terminating the result.

## RETURN VALUES

- The strlcpy(0 and strlcat() functions return the total length of the string they tried to create.

- It was done to make truncation detection simple.
