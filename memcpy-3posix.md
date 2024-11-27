# MEMCPY(3POSIX)

## NAME

- memcpy -- copy bytes in memory

## SYNOPSIS

```
#include <string.h>

void *memcpy(void *restrict s1, const void *restrict s2, size_t n);
```

## DESCRIPTION

- The functionality described on this reference page is aligned with the ISO C standard.

- Any conflict between the requirements described here and the ISO C standard is unintentional.

- This volume of POSIX.1‐2017 defers to the ISO C standard.

<br>

- The *memcpy*() function shall copy *n* bytes from the object pointed to by *s2* into the object pointed to by *s1*.

- If copying takes place between objects that overlap, the behavior is undefined.

## RETURN VALUE

- The *memcpy*() function shall return *s1*; no return value is reserved to indicate an error.

## ERRORS

- No errors are defined.

- The following sections are informative.

## APPLICATION USAGE

- The *memcpy*() function does not check for the overflow of the receiving memory area.
