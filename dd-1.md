# DD(1)

## NAME

- convert and copy a file

## SYNOPSIS

```sh
dd [OPERAND]...
dd OPTION
```

## DESCRIPTION

- Copy a file, converting and formatting according to the operands.

- bs=BYTES: read and write up to BYTES bytes at a time (default: 512); overrides ibs and obs

- count=N: copy only N input blocks

- if=FILE: read from FILE instead of stdin

- of=FILE: write to FILE instead of stdout

- N and BYTES may be followed by the following multiplicative suffixes: c=1, w=2, b=512, kB=1000, K=1024, MB=1000*1000, M=1024*1024, xM=M, GB=1000*1000*1000, G=1024*1024*1024, and so on for T, P, E, Z, Y, R, Q.

- Binary prefixes can be used, too: KiB=K, MiB=M, and so on.

- If N ends in 'B', it counts bytes not blocks.
