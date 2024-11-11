# GAWK(1)

## NAME

- pattern scanning and processing language

## DESCRIPTION

- Gawk is the GNU Project's implementation of the AWK programming language.

- This version in turn is based on the description in The AWK Programming Language, by Aho, Kernighan, and Weinberger.

- Gawk provides the additional features found in the current version of Brian Kernighan's awk and numerous GNU-specific extensions.

## AWK PROGRAM EXECUTION

- An AWK program consists of a sequence of optional directives, pattern-action statements, and optional function definitions.

```awk
@include "filename"
@load "filename"
@namespace "name"
pattern { action statements }
function name(parameter list) { statements }
```

- Fawk first reads the program source from the program-file(s) if specified, from arguments to --source, or from the first non-option argument on the command line.

## VARIABLES, RECORDS AND FIELDS

### Fields

- As each input record is read, gawk splits the record into fields, using the value of the FS variable as the field separator.

- In the special case that FS is a single space, fields are separated by runs of spaces and/or tabs and/or newlines.

- Each field in the input record may be referenced by its position: $1, $2, and so on.

- $0 is the whole record, including leading and trailing whitespace.

### Built-in Variables

- `FS`

	- The input field separator, a space by default.

## PATTERNS AND ACTIONS

- AWK is line-oriented language.

- The pattern comes first, and then the action.

- Action statements are enclosed in { and }.

- Either the pattern may be missing, or the action may be missing.

- If the pattern is missing, the action executes for every single record of input.

### I/O Statements

- print

	- Print the current record.
