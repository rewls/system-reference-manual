# ISALPHA(3POSIX)

## NAME

- isalpha, isalpha_l -- test for an alphabetic character

## SYNOPSIS

```
#include <ctype.h>

int isalpha(int c);
int isalpha_l(int c, locale_t locale);
```

## DESCRIPTION

- For isalpha(): The functionality described on this reference page is aligned with the ISO C standard.

- Any conflict between the requirements described here and the ISO C standard is unintentional.

- This volume of POSIX.1‐2017 defers to the ISO C standard.

- The *isalpha*() and *isalpha_l*() functions shall test whether *c* is a character of class alpha in the current locale, or in the locale represented by *locale*, respectively; see the Base Definitions volume of POSIX.1‐2017, *Chapter 7, Locale*.

- The *c* argument is an **int**, the value of which the application shall ensure is representable as an **unsigned char** or equal to the value of the macro EOF. If the argument has any other value, the behavior is undefined.

## RETURN VALUE

- The *isalpha*() and *isalpha_l*() functions shall return non-zero if *c* is an alphabetic character; otherwise, they shall return 0.

## ERRORS

- No errors are defined.

- The following sections are informative.

## APPLICATION USAGE

- To ensure applications portability, especially across natural languages, only these functions and the functions in the reference pages listed in the SEE ALSO section should be used for character classification.

## SEE ALSO

- *isalnum*(), *isblank*(), *iscntrl*(), *isdigit*(), *isgraph*(), *islower*(), *isprint*(), *ispunct*(), *isspace*(), *isupper*(), *isxdigit*(), *setlocale*(), *uselocale*()
