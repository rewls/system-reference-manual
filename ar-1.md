# AR(1)

## NAME

- create, modify, and extract from archives

## DESCRIPTION

- An archive is a single file holding a collection of other files in a structure that makes it possible to retrieve the original individual files.

- The original files' contents, mode, timestamp, owner, and group are preserved in the archive, and can be restored on extraction.

- GNU ar can maintain archives whose members have names of any length.

- ar is considered a binary utility because archives of this sort are most often used as libraries holding commonly needed subroutines.

- ar creates an index to the symbols defined in relocatable object modules in the archive when you specify the modifier s.

- Once created, this index is updated in the archive whenever ar make a change to its contents.

- An archive with such an index speeds up linking to the library, and allows routines in the library to call each other without regard to their placement in the archive.

- You may use nm -s or nm --print-armap to list this index table.

- GNU ar can optionally create a thin archive, which contains a symbol index and references to the original copies of the member files of the archive.

- This is useful for building libraries for use within a local build tree, where the relocatable objects are expected to remain available, and copying the contents of each object would only waste time and space.

- An archive can either be thin or it can be normal.

- Thin archives are also flattened, so that adding one thin archive to another thin archive does not nest it, as would happen with a normal archive.

- The paths to the elements of the archive are stored relative to the archive itself.

## OPTIONS

- GNU ar allows you to mix the operation code p and modifier flags mod in any order, within the first command-line argument.

- If you wish, you may begin the first command-line argument with a dash.

- The p keyletter specifies what operation to execute; it may be any of the following, but you must specify only one of them:

	- r

		- Insert the files member... into archive.
