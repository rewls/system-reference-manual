# ERRNO(3POSIX)

## NAME

- error return value

## SYNOPSIS

```c
#include <errno.h>
```

## DESCRIPTION

- The lvalue errno is used by many functions to return error values.

- Many functions provide an error number in errno, which has type int and is defined in <errno.h>.

- The value of errno shall be defined only after a call to a function for which it is explicitly stated to be set and until it is changed by the next function call or if the application assigns it a value.

- The value of errno should only be examined when it is indicated to be valid by a function's return value.

- Applications shall obtain the definition of errno by the inclusion of <errno.h>.

- No function in this volume of POSIX.1-2017 shall set errno to 0.

- The setting of errno after a successful call to a function is unspecified unless the decription of that function specifies that errno shall not be modified.
