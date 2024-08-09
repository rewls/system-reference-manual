# FILE(1)

## NAME

- determine file type

## DESCRIPTION

- This manual page documents version 5.41 of the file command.

- file tests each argument in an attempt to classify it.

- There are three sets of tests, performed in this order: filesystem tests, magic tests, and language tests.

- The first test that succeeds causes the file type to be printed.

- The type printed will usually contain one of the words text, executable, or data meaning anything else.

- Exceptions are well-known file formats that are known to contain binary data.

- The magic tests are used to check for files with data in particular fixed formats.

- The canonical example of this is a binary executable (compiled program) a.out file, whose format is defined in <elf.h>, <a.out.h> and possibly <exec.h> in the standard include directory.

- Any file with some invariant identifier at a small fixed offset into the file can usually be described in this way.

## OPTIONS

- `-m`, `--magic-file magicfiles`

	- Specify an alternate list of files and directories containing magic.
