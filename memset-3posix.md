# MEMSET(3POSIX)

## NAME

- memset -- set bytes in memory

## SYNOPSIS

```c
#include <string.h>

void *memset(void *s, int c, size_t n);
```

## DESCRIPTION

- The  functionality  described  on  this reference page is aligned with the ISO C standard.

- Any conflict between the requirements described here and the ISO C standard is unintentional.

- This volume of POSIX.1‐2017 defers to the ISO C standard.

- The  *memset*()  function  shall copy c (converted to an unsigned char) into each of the first *n* bytes of the object pointed to by *s*.

## RETURN VALUE

- The *memset*() function shall return *s*; no return value is reserved to indicate an error.

## ERRORS

- No errors are defined.
