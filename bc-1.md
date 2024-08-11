# BC(1)

## NAME

- An arbitrary precision calculator language

## DESCRIPTION

- bc is a language that supports arbitrary precision numbers with interactive execution of statements.

- There are some similarities in the syntax to the C programming language.

- After all files have been processed, bc reads from the standard input.

### NUMBERS

- The most basic element in bc is the number.

### VARIABLES

- Numbers are stored in two type of variables, simple variables and array.

- There are four special variables, scale, ibase, obase and last.

- ibase and obase define the conversion base for input and output numbers.

### EXPRESSIONS

- The numbers are manipulated by expressions and statements.

- A simple expression is just a constant.

- bc converts constants into internal decimal numbers using the current input base, specified by the variable ibase.

- Input numbers may contain the characters 0-9 and A-Z.

- In the following descriptions of legal expressions, "expr" refers to a complete expression and "var" refers to a simple or an array variable.

- `expr + expr`: The result of the expression is the difference of the two expressions.

- `var = expr`: The variable is assigned the value of the expression.

### STATEMENTS

- Statements provide the sequencing of expression evaluation.

- In bc statements are executed "as soon as possible."

- Execution happens when a newline in encountered and there is one or more complete statements.

- In fact, both a semicolon and a newline are used as statement separators.

- The following is a list of bc statements and what they do:

	- expression
