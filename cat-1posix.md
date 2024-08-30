# CAT(1POSIX)

## NAME

- concatenate and print files

## OPERANDS

- The following operand shall be supported:

	- file

		- A pathname of an input file.

		- If no file operands are specified, the standard input shall be used.

		- If a file is '-', the cat utility shall not close and reopen standard input when it is referenced in this way, but shall accept multiple occurrences of '-' as a file operand.

## STDIN

- The standard input shall be used only if no file operands are specified, or if a file operand is '-'.

## INPUT FILES

- The input files can be any file type.

## EXIT STATUS

- The following exit values shall be returned:

	- 0: All input files were output successfully.

	- >0: An error occurred.
