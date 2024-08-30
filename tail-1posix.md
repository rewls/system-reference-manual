# TAIL(1POSIX)

## NAME

- copy the last part of a file

## SYNOPSIS

```sh
tail [-f] [-c number|-n number] [file]
```

## DESCRIPTION

- The tail utility shall copy its input file to the standard output beginning at a designated place.

- Copying shall begin at the point in the file indicated by the -c number or -n number options.

- The option-argument number shall be counted in units of lines or bytes, according to the options -n and -c.

- Both line and byte counts start from 1.

- Tails relative to the end of the file may be saved in an internal buffer, and thus may be limited in length.

- Such a buffer, if any, shall be no smaller than {LINE_MAX}*10 bytes.

## OPTIONS

- -c number

    - The application shall ensure that the number option-argument is a decimal integer, optionally including a sign.

    - The origin for counting shall be 1.

## OPERANDS

- file

    - A pathname of an input file.

    - If no file operand is specified, the standard input shall be used.

## STDIN

- The standard input shall be used if no file operand is specified, and shall be used if the file operandis '-' and the implementation treats the '-' as meaning standard input.

- Otherwise, the standard input shall not be used.

- See the INPUT FILES section.

## INPUT FILES

- If the -c option is specified, the input file can contain arbitrary data; otherwise, the input file shall be a text file.

## EXIT STATUS

- The following exit values shall be returned:

    - 0: Successful completion.

    - >0: An error occurred.
