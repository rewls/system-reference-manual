# FIND(1)

## NAME

- search for files in a directory hierarchy

## SYNOPSIS

```sh
find ... [starting-point...] [expression]
```

## DESCRIPTION

- GNU find searches the directory tree rooted at each given starting-point by evaluating the given expression from left to right, according to the rules of precedence (see section OPERATORS), until the outcome is known.

- If no starting-point is specified, '.' is assumed.

## EXPRESSION

- This is a kind of query specification describing how we match files and what we do with the files that were matched.

- An expression is composed of a sequence of things:

	- Tests

		- Tests return a true or false value, usually on the basis of some property of a file we are considering.

	- Actions

		- Actions have side effects and return either true or false, usually based on whether or not they are successful.

	- Operators

		- Operators join together the other items within the expression.

## TESTS

- `-name pattern`

	- Base of file name matches shell pattern `pattern`.

- `-type c`

	- File if of type `c`:

		- `d`: directory

		- `f`: regular file

## ACTIONS

- `-delete`

	- Delete files; true if removal succeeded.

- `-exec command ;`

	- Execute command; true if 0 status is returned.

	- All following arguments to find are taken to be arguments to the command until an argument consisting of `;` is encounter.

	- The string `{}` is replaced by the current file name being processed everywhere it occurs in the arguments to the command.

	- Both of these constructions might need to be escaped or quoted to protect them from expansion by the shell.

	- The specified command is run once for each matched file.

	- There are unavoidable security problems surrounding use of the -exec action; you should use the -execdir option instead.

- `-execdir command ;`

	- Like -exec, but the specified command is run from the subdirectory containing the matched file, which is not normally the directory in which you started find.

	- As with -exec, the {} should be quoted if find is being invoked from a shell

	- This a much more secure method for invoking commands, as it avoids race conditions during resolutio of the paths to the matched files.

	- If you use this option, you must ensure that your $PATH environment variable does not reference `.`; otherwise, an attacker can run any commands they like by leaving an appropriately-named file in a directory in which you will run -execdir.

	- The same applies to having entries in $PATH which are empty or which are not absolute directory names.

- `-print`

	- True; print the full file name on the standard output, followed by a newline.

## OPERATORS

- Listed in order of decreasing precedence:

	- `( expr )`

		- Force precedence.

		- Since parentheses are special to the shell, you will normally need to quote then.

		- Many of the examples in this manual page use backslashes for this purpose: `\(...\) instead of `(...)`.

	- `expr1 -o expr2`

		- Or; expr2 is not evaluated if expr1 is true.

