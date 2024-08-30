# MAN(1)

## NAME

- an interface to the system reference manuals

## SYNOPSIS

```sh
man [man options [[section] page ...] ...
man -k [apropos options] regexp ...
```

## DESCRIPTION

- Each page argument given to man is normally the name of a program, utility or function.

- The default action is to search in all of the available sections following a pre-defined order (see DEFAULTS), and toshow only the first page found, even if page exists in several sections.

- The table below shows the section numbers of the manual followed by the types of pages they contain.

    1. Executable program or shell commands

    2. System calls (functions provided by the kernel)

    3. Library calls (functions within program libraries)

    4. Special files (usually found in /dev)

    5. File formats and conventions, e.g. /etc/passwd

    6. Games

    7. Miscellaneous (including macro packges and conventions, e.g. man(7), groff(7), man-pages(7)

    8. System administration commands (usually only for root)

    9. Kernel routines [Non standard]

- A manual page consists of several sections.

- Conventional section names include NAME, SYNOPSIS, CONFIGURATION, DESCRIPTION, OPTIONS, EXIT STATUS, RETURN, VALUE, ERRORS, ENVIRONMENT, FILES, VERSIONS, STANDARDS, NOTES, BUGS, EXAMPLE, AUTHORS, and SEE ALSO.

- The following conventions apply to the SYNOPSIS section and can be used as a guide in other sections.

    - **bold text**: type exactly as shown.

    - <u>italic text</u>: replace with appropriate argument.

    - [-**abc]: any or all arguments within [ ] are optional.

    - **-a**|**-b**: option delimited by | cannot be used together.

    - <u>argument</u> ...: argument is repeatable.

    - [<u>expression</u>] ...: entire <u>expression</u> within [ ] is repeatable.

- Exact rendering may vary depending on the output device.

- The command or function illustration is a pattern that should match all possible invocations.

- In some cases it is advisable to illustrate several exclusive invocations as is shown in the SYNOPSIS section of this manual.

## EXAMPLES

- man man.7: Display the manual pagefor macro package man from section 7.

    - This is an alternative spelling of "man 7 man".

- man 'man(7)': Display the manual pagefor macro package man from section 7.

- man -a intro: Display, in succession, all of the available intro manual pages contained within the manual.

- man -k printf: Search the short descriptions and manual page names for the keyword printf as regular expression.

- man -f smail: Lookup the manual pages referenced by smail and print out the short descriptions of any found.

## DEFAULTS

- By default the order of sections is as follows:

    - 1 1p n l 8 3 3p 0 0p 2 3type 5 4 9 6 7

## OPTIONS

### Main modes of operation

- -f, --whatis

    - Approximately equivalent to whatis.

    - Display a short description from the manual page, if available.

    - See whatis(1) for details.

- -k, -apropos

    - Approximately equivalent to apropos.

    - Search the short manual page descriptions for keywords and display any matches.

    - See apropos(1) for details.

### Finding manual pages

- -a --all

    - By default, man will exit after displaying the most suitable manual page it finds.

    - Using this option forces man to display all the manual pages with names that match the search criteria.
