# STRSTR(3)

## NAME

- locate a substring

## SYNOPSIS

```c
#include <string.h>

char *strstr(const char *haystack, const char *needle);
```

## DESCRIPTION

- The strstr() function finds the first occurrence of the substring needle in the string haystack.

- The terminating null bytes are not compared.

## RETURN VALUE

- The function returns a pointer to the beginning of the located substring, or NULL if the substring is not found.
