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

