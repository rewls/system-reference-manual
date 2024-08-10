# BASH(1)

## NAME

- GNU Bourne-Again SHell

## SYNOPSIS

```sh
bash [options] [command_string | file]
```

## DESCRIPTION

- Bash is sh-compatible command language interpreter that executes commands read from the standard input or from a file.

## QUOTING

- Quoting is used to remove the special meaning of certain characters or words to the shell.

- Quoting can be used to disable special treatment for special characters, to prevent reserved words from being recognized as such, and to prevent parameter expansion.

- There are three quoting mechanisms: the escape character, single quotes, and double quotes.

- A non-quoted backslash (\) is the escape character.

- It preserves the literal value of the next character that follows with the exception of <newline>.

- Enclosing characters in single quotes preserves the literal value of each character within the quotes.

- A single quote may not occur between single quotes, even when preceded y a backslash.

- Enclosing characters in double quotes preserves the literal value of all characters within the quotes, with the exception of $, `, \, and, when history expansion is enabled, !.

- The characters $ and ` retain their special meaning within double quotes.

- The backslash retains its special meaning only when followed by one of the following characters: $, `, ", \, or <newline>.

- A double quote may be quoted within double quotes by preceding it with a backslash.

- The special parameters * and @ have special meaning when in double quotes (see PARAMETERS below).

## PARAMETERS

- A parameter is an entity that stores values.

- It can be a name, a number, or one of the special characters listed below under Special Parameters.

### Special Parameters

- The shell treats several parameters specially.

- `*`: Expands to the positional parameters, starting from one.

## EXPANSION

- Expansion is performed on the command line after it has been split into words.

### Parameter Expansion

- The '$' character introduces parameter expansion, command substitution, or arithmetic expansion.

- `${parameter}`

	- The value of parameter is substituted.

	- The braces are required when parameter is a positional parameter with more than one digit, or when parameter is followed by a character which is not to be interpreted as part of its name.

### Pathname Expansion

- After word splitting, unless the -f option has been set, bash scans each word for the characters *, ?, and [.

- If one of these characters appears, and is not quoted, then the word is regarded as a pattern and replaced with an alphabetically sorted list of filenames matching the pattern (see Pattern Matching below).
