# STRLEN(3POSIX)

## NAME

- strlen, strnlen — get length of fixed size string

## SYNOPSIS

```c
#include <string.h>

size_t strlen(const char *s);
size_t strnlen(const char *s, size_t maxlen);
```

## DESCRIPTION

- For  *strlen*():  The  functionality  described on this reference page is aligned with the ISO C standard.

- Any conflict between the requirements described here and the ISO C standard is unintentional.

- This volume of POSIX.1‐2017 defers to the ISO C standard.

- The  *strlen*()  function shall compute the number of bytes in the string to which s points, not
including the terminating NUL character.

## RETURN VALUE

- The *strlen*() function shall return the length of *s*; no return value shall be reserved to indicate an error.

## ERRORS

- No errors are defined.

- The following sections are informative.
