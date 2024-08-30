# BASENAME(3)

## NAME

- parse pathname components

## SYNOPSIS

```c
#include <libgen.h>

char *basename(char *path);
```

## DESCRIPTION

- Warning: there are two different functions basename() - see below.

- The function basename() break a null-terminated pathname string into directory and filename components.

- In the usual case, basename() returns the component following the final '/'.

- Trailing '/' characters are not counted as part of the pathname.

- If path dose not contain a slash, basename() returns a copy of path.

- If path is the string "/", then basename() return the string "/".

- If path is a null pointer or points to an empty string, then basename() return the string ".".

- basename() may modify the contents of path, so it may be desirable to pass a copy when calling the function.

- These functions may return pointer to statically allocated memory which may be overwritten by subsequent calls.

- Alternatively, it may return a pointer to some part of path, so that eh string referred to by path should not be modified or freed until the pointer returned by the function is no longer required.

## RETURN VALUE

- basename() return pointers to null-terminated strings.

	- Do not pass these pointers to free.

## EXAMPLES

```c
char *basec, *bname;
char *path = "/etc/passwd";

basec = strdup(path);
bname = basename(basec);
printf("basename=%s\n", bname);
```
