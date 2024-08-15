# nsswitch.conf(5)

## NAME

- Name Service Switch configuration file

## DECRYPTION

- The Name Service Switch (NSS) configuration file, /etc/nsswitch.conf, is used by the GNU C Library and certain other applications to determine the sources from which to obtain name-service information in a range of categories, and in what order.

- Each category of information is identified by a database name.

- The file is plain ASCII text, with columns separated by spaces or tab characters.

- The first column specifies the database name.

- The remaining columns describe the order of sources to query and a limited set of actions that can be performed by lookup result.

- The following databases are understood by the GNU C Library:

    - passwd

## FILES

- A service named SERVICE is implemented by a shared object library named libnss_SERVICE.so.X that resieds in /lib.

    - /etc/nsswitch.conf: NSS configuration file.

    - /lib/libnss_files.so.X: implements "files" source.

- The following files are read when "files" source is specified for respective databases:

    - passwd: /etc/psaswd
