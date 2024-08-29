# STRERROR(3)

## NAME

- return string describing error number

## SYNOPSIS

```c
#include <string.h>

char *strerror(int errnum);
```

## DESCRIPTION

- The strerror() function returns a pointer to a string that describes the error code passed in the argument errnum.

- This string must not be modified by the application, and the returned pointer will be invalidated on a subsequent call to strerror() of if the thread that obtained the string exits.

## RETURN VALUE

- The strerror() function return the appropriate error description string, or an "Unknown error nnn" message if the error number is unknown.
