# STRDUP(3)

## NAME

- strdup, strndup, strdupa, strndupa - duplicate a string

## SYNOPSIS

```c
#include <string.h>

char *strdup(const char *s);
```

## DESCRIPTION

- The strdup() function returns a pointer to a new string which is a duplicate of the string s.

- Memory for the new string is obtained with malloc(3), and can be freed with free(3).

## RETURN VALUE

- On success, the strdup() function returns a pointer to the duplicated string.

- It returns NULL if insufficient memory was available, with errno set to indicate the cause of the error.
