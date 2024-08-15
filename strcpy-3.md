# STRCPY(3)

## NAME

- strcpy, strncp - copy a string

## SYNOPSIS

```c
#include <string.h>

char *strcpy(char *dest, const char *src);

char *strncpy(char *dest, const char *src, size_t n);
```

## DESCRIPTION

- The strcpy() function copies the string pointed to by src, including the terminating null byte, to the buffer pointed to by dest.

- The strings may not overlap, and the destination string dest must be large enough to receive the copy.

- Beware of buffer overruns!

- The strncpy() function is similar, except that at most n bytes of src are copied.

- Warning: If there is no null byte among the first n bytes of src, the string placed in dest will not be null-terminated.

- If the length of src is less than n, strncpy() writes additional null bytes to dest to ensure that a total of n bytes are written.

## RETURN VALUE

- The strcpy() and strncpy() functions return a pointer to the destination string dest.

## NOTES

- Some programmers consider strncpy() to be inefficient and error prone.

- If the programmer knows that the size of dest is greater than the length of src, then strcpy() can be used.

- One valid use of strncpy() is to copy a C string to a fixed-length buffer while ensuring both that the buffer is not overflowed and that unused bytes in the destination buffer are zeroed out.

### strlcpy()

- Some systems (the BSDs, Solaris, and others) provide the following function:

	```c
	size_t strlcpy(char *dest, const char *src, size_t size);
	```

- The function is similar to strncpy(), but it copies at most size-1 bytes to dest, always adds a terminating null byte, and does not pad the destination with null bytes.

- The return value is the length of src, which allows truncation to be easily detected.

- strlcpy() is not present in glibc and is not standardized by POSIX, but available on Linux via the libbsd library.
