# GHOST11 WRITEUP

1. connect to the ghost11 stage using `ssh ghost11@204.168.229.209 -p 2222`

2. after logging in, we list the files using `ls` and find a file named `stage.bin`.

3. using `file stage.bin` shows that it is a POSIX tar archive:

    `stage.bin: POSIX tar archive (GNU)`

4. extract the archive using `tar -xf stage.bin`.

5. this gives us a new file named `payload.txt.gz.xz`.

6. using `file payload.txt.gz.xz` shows that it is XZ compressed data with a CRC64 checksum:

    `payload.txt.gz.xz: XZ compressed data, checksum CRC64`

7. we can decompress the XZ layer using `xz -d payload.txt.gz.xz`, which gives us `payload.txt.gz`.

8. `file payload.txt.gz` shows that the file is gzip compressed, so we decompress it using `gzip -d payload.txt.gz`.

9. this gives us the final file `payload.txt`, which contains the password for the next stage.

10. read the password using `cat payload.txt`.

**flag - `Unwr4pp3d_Thr33`**
