# GETOPT

## NAME

- command option parsing

## SYNOPSIS

```c
#include <unistd.h>

int getopt(int argc, char * const argv[], const char *optstring);
```

## DESCRIPTION

- The getopt() function is a command-line parser that shall follow Utility Syntax Guidelines 3, 4, 5, 6, 7, 9, an 10 in the Base Definition volume of POSIX.1-2017, Section 12.2, Utility Syntax Guidelines.

- The parameters argc, and argv are the argument count and argument array as passed to main().

	- See exec().

- The argument optstring is a string of recognized option characters; if a character is followed by a <colon>, the option takes an argument.

- The getopt() function shall return the next option character from argv that matches a character in optstring, if there is one that matches.

- If the option takes an argument argument, getopt() shall set the variable optarg to point to the option-argument as follows:

	1. If the option was the last character in the string pointed to by an element of argv, then optarg shall contain the next element of argv, and optind shall be incremented by 2.

	2. Otherwise, optarg shall point to the string following the option character in that element of argv, and optind shall be incremented by 1.

- If, when getopt() is called:

	- argv[optind] is a null pointer

	- *argv[optind] is not the character -

	- argv[optind] points to the string "-"

	- getopt() shall return -1 without changing optind.

- If getopt() encounters an option character that is not contained in optstring, it shall return the <question-mark? character.

- If it detects a missing option-argument, it shall return the <colon> character if the first character of optstring was a <colon>, or a <question-mark> character otherwise.

- The getopt() function shall return the next option character specified on the command line.

- A <colon> shall be returned if getopt() detects a missing argument and the first character of optstring was a <colon>.

- A <question-mark> shall be returned if getopt() encounters option character not in optstring or detects a missing argument and the first character of optstring was not a <colon>.

- Otherwise, getopt() shall return -1 when all command line options are parsed.
