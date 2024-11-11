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

- See libbsd(7) for include usage.

## DESCRIPTION

- They are designed to be safer, more consistent, and less error prone replacements for strncpy(3) and strncat(3).

- Unlike those functions **strlcpy**() and **strlcat**() take the full size of the buffer and guarantee to NUL-terminate the result.

- **strlcpy**() and **strlcat**() only operate on true "C" strings.

<br>

- The **strlcpy**() function copies up to *size* - 1 characters from the NUL-terminated string *src* to *dst*, NUL-terminating the result.

<br>

- The **strlcat**() function appends the NUL-terminated string *src* to the end of *dst*.

- It will append at most *size* -strlen(dst) - 1 bytes, NUL-terminating the result.

## RETURN VALUES

- The **strlcpy**() and **strlcat**() functions return the total length of the string they tried to create.

- It was done to make truncation detection simple.

<br>

- Note, however, that if **strlcat**() traverses *size* characters without finding a NUL, the length of the string is considered to be size and the destination string will not be NUL-terminated (since there was no space for the NUL).

- This keeps **strlcat**() from running off the end of a string.

- In practice this should not happen (as it means that either *size* is incorrect or that *dst* is not a proper "C" string).

- The check exists to prevent potential security problems in incorrect code.

## EXAMPLES

- The following code fragment illustrates the simple case:

	```c
	char *s, *p, buf[BUFSIZ];

	...

	(void)strlcpy(buf, s, sizeof(buf));
	(void)strlcat(buf, p, sizeof(buf));
	```

- To detect truncation, perhaps while building a pathname, something like the following might be used:

	```c
	char *dir, *file, pname[MAXPATHLEN];

	...

	if (strlcpy(pname, dir, sizeof(pname)) >= sizeof(pname))
		   goto toolong;
	if (strlcat(pname, file, sizeof(pname)) >= sizeof(pname))
		   goto toolong;
	```

- Since it is known how many characters were copied the first time, things can be sped up a bit by using a copy instead of an append:

	```c
	char *dir, *file, pname[MAXPATHLEN];
	size_t n;

	...

	n = strlcpy(pname, dir, sizeof(pname));
	if (n >= sizeof(pname))
		   goto toolong;
	if (strlcpy(pname + n, file, sizeof(pname) - n) >= sizeof(pname) - n)
		   goto toolong;
	```

- However, one may question the validity of such optimizations, as they defeat the whole purpose of **strlcpy**() and **strlcat**().

- As a matter of fact, the first version of this manual page got it wrong.
