# TRUNCATE(1)

## NAME

- shrink or extend the size of a file to the specified size

## SYNOPSIS

```sh
truncate OPTION... FILE...
```

## DESCRIPTION

- A FILE argument that does not exist is created.

- If a FILE is larger than the specified size, the extra data is lost.

- If a FILE is shorter, it is extended and the sparse extended part reads as zero bytes.

- `-s`, `--size=SIZE`: set or adjust the file size by SIZE bytes

- The SIZE argument is an integer and optional unit.

- Units are K,M,G,T,P,E,,Z,Y,R,Q (powers of 1024) or KB, MB, ... (powers of 1000).

- Binary prefixes can be used, too: KiB=K, MiB, and so on.

- SIZE may also be prefixed by one of the following modifying characters: '+' extend by, '-' reduce by, '<' at most, '>' at least, '/' round down to multiple of, '%' round up to multiple of.
