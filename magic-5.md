# MAGIC(5)

## NAME

- file command's magic pattern file

## DESCRIPTION

- This manual page documents the format of magic files as used by the file(1) command, version 5.41.

- The format of the source fragment files that are used to build this database is as follow: Each line of a fragment file specifies a test to be performed.

- A test compares the data starting at a particular offset in the file with a byte value, a string or a numeric value.

- The line consists of the following fields:

	1. offset

		- A number specifying the offset into the file of the data which is to be tested.

	2. type

		- The type of the data to be tested.

		- The possible values are:

			- string: A string of bytes.

	3. test

		- The value to be compared with the value from the file.

	4. message

		- The message to be printed if the comparison succeeds.
