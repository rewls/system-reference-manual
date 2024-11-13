# MEMMOVE(3POSIX)

## NAME

- memmove -- copy bytes in memory with overlapping areas

## SYNOPSIS

```
#include <string.h>

void *memmove(void *s1, const void *s2, size_t n);
```

## DESCRIPTION

- The functionality described on this reference page is aligned with the ISO C standard.

- Any conflict be tween the requirements described here and the ISO C standard is unintentional.

- This volume of POSIX.1‐2017 defers to the ISO C standard.

<br>

- The *memmove*() function shall copy *n* bytes from the object pointed to by *s2* into the object pointed to by *s1*.

- Copying takes place as if the *n* bytes from the object pointed to by *s2* are first copied into a temporary array of *n* bytes that does not overlap the objects pointed to by *s1* and *s2*, and then the *n* bytes from the temporary array are copied into the object pointed to by *s1*.

## RETURN VALUE

- The memmove() function shall return *s1*; no return value is reserved to indicate an error.

## ERRORS

- No errors are defined.
