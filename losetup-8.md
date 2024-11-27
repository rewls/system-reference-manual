# LOSETUP(8)

## NAME

- losetup - set up and control loop devices

## SYNOPSIS

- Get info:

    <pre><b>losetup</b> [<u>loopdev</u>]</pre>

    <pre><b>losetup</b> <b>-l</b> [<b>-a</b>]</pre>

- Set up a loop device:

    <pre><b>losetup</b> [<b>-o</b> <u>offset</u>] [<b>--sizelimit</b> <u>size</u>] [<b>--sector-size</b> <u>size</u>] [<b>--loop-ref</b> <u>name</u>] [<b>-Pr</b>] [<b>--show</>] <b>-f</b>|<u>loopdev file</u>

## DESCRIPTION

- **losetup** is used to associate loop devices with regular files or block devices, to detach loop devices, and to query the status of a loop device.

- If only the <u>loopdev</u> argument is given, the status of the corresponding loop device is shown.

- If no option is given, all loop devices are shown.

<br>

- Note that the old output format (i.e., **losetup -a**) with comma-delimited strings is deprecated in favour of the **--list** output format.

<br>

- It’s possible to create more independent loop devices for the same backing file.

- This setup may be dangerous, can cause data loss, corruption and overwrites.

- Use **--nooverlap** with **--find** during setup to avoid this problem.

<br>

- The loop device setup is not an atomic operation when used with **--find**, and **losetup** does not protect this operation by any lock.

- The number of attempts is internally restricted to a maximum of 16.

- It is recommended to use for example **flock**(1) to avoid a collision in heavily parallel use cases.

## OPTIONS

- The <u>size</u> and <u>offset</u> arguments may be followed by the multiplicative suffixes KiB (=1024), MiB (=1024*1024), and so on for GiB, TiB, PiB, EiB, ZiB and YiB (the "iB" is optional, e.g., "K" has the same meaning as "KiB") or the suffixes KB (=1000), MB (=1000*1000), and so on for GB, TB, PB, EB, ZB and YB.

- **-o**, **--offset** <u>offset</u>

    - The data start is moved offset bytes into the specified file or device.

    - The offset may be followed by the multiplicative suffixes; see above.
