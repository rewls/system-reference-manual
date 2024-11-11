# BZERO(3)

## NAME

- bzero, explicit_bzero -- zero a byte string

## SYNOPSIS

```c
#include <strings.h>

void bzero(void *s, size_t n);

#include <string.h>

void explicit_bzero(void *s, size_t n);
```

## DESCRIPTION

- The **bzero**() function erases the data in the *n* bytes of the memory starting at the location pointed to by *s*, by writing zeros (bytes containing '\0') to that area.

## ATTRIBUTES

- For an explanation of the terms used in this section, see **attributes**(7).

	┌─────────────────┬───────────────┬─────────┐
	│Interface        │ Attribute     │ Value   │
	├─────────────────┼───────────────┼─────────┤
	│bzero(),         │ Thread safety │ MT-Safe │
	│explicit_bzero() │               │         │
	└─────────────────┴───────────────┴─────────┘

## CONFORMING TO

- The **bzero**() function is deprecated (marked as LEGACY in POSIX.1-2001); use **memset**(3) in new programs.

- POSIX.1-2008 removes the specification of **bzero**().

- The **bzero**() function first appeared in 4.3BSD.
