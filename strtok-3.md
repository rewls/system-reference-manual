# STRTOK(3)

## NAME

- extract tokens from strings

## SYNOPSIS

```c
#include <string.h>

char *strtok(char *str, const char *delim);
```

## DESCRIPTION

- The strtok() function breaks a string into a sequence of zero or more nonempty tokens.

- On the first call to strtok(), the string to be parsed should be specified in str.

- In each subsequent call that should parse the same string, str must be NULL.

- The delim argument specifies a set of bytes that delimit the tokens in the parsed string.

- The caller may specify different strings in delim in successive calls that parse the same string.

- Each call to strtok() returns a pointer to a nullterminated string containing the next token.

- This string does not include the delimiting byte.

- If no more tokens are found, strtok() returns NULL.

- A sequence of calls to strtok() that operate on the same string maintains a pointer that determines the point from which to start searching for the next token.

- The first call to strtok() sets this pointer to point to the first byte of the string.

- The start of the next token is determined by scanning forward for the next nondelimiter byte in str.

- If such a byte is found, it is taken as the start of the next token.

- If no such byte is found, then there are no more tokens, and strtok() returns NULL.

- The end of each token is found by scanning forward until either the next delimiter byte is found or until the terminating null byte ('\0') is encountered.

- If a delimiter byte is found it is overwritten with a null byte to terminate the current token, and strtok() saves a pointer to the following byte.

- From the above description, it follows that a sequence of two or more contiguous delimiter bytes in the parsed string is considered to be a single delimiter, and that delimiter bytes at the start of end of the string are ignored.

## RETURN VALUE

- The strtok() function return a pointer to the next token, or NULL if there are no more tokens.

## BUGS

- Be cautious when using these functions.

- If you do use them, note that:

	- These functions modify their first argument.

	- These functions cannot be used on constant strings.

	- The identity of the delimiting byte is lost.

	- The strtok() functions uses a static buffer while parsing, so it's not thread safe.
