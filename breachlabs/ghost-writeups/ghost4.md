# GHOST4 WRITEUP

1. connect to ghost4 using `ssh ghost4@204.168.229.209 -p 2222` & password: `i wont be mentioning this field anymore`

2. list the contents and we see a `vault` folder in the current directory.

3. inside the `vault` folder we see multiple records and a few files named `password`, `hash`, etc.

4. we notice that most of the files inside the folder have a file size of 63 bytes, and when we check their contents, they contain some possible md5 hashes.

    ===== some files have a 63 byte size =====

    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0483`
    
    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0484`
    
    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0485`
    
    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0486`
    
    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0487`
    
    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0488`
    
    `-rw-r--r-- 1 ghost4 ghost4    63 Sep 15 13:12 record_0489`

    ===== some of the files have a 48 byte size =====

    `-rw-r--r-- 1 ghost4 ghost4    48 Sep 15 13:12 record_0477`
    
    `-rw-r--r-- 1 ghost4 ghost4    48 Sep 15 13:12 record_0404`
    
    `-rw-r--r-- 1 ghost4 ghost4    48 Sep 15 13:12 record_0291`
    
    `-rw-r--r-- 1 ghost4 ghost4    48 Sep 15 13:12 record_0182`

5. lets filter out the files which are NOT 63 bytes using the following command:

    `ls -l | grep --invert-match 63`

    this gives us the files which have a different size from the majority of the records.

6. now since this is a CTF, it's mostly obvious that the credentials are stored in one of these files, so lets check them using `cat`.

    `for f in $(ls -l | grep -v 63 | awk '{print $NF}'); do cat "$f"; done`

7. after checking the files, we find that `record_0086` contains the following content:

    `[CLASSIFIED] CREDENTIAL: Gr3p_F1nds_Truth`

8. the credential gives us the flag.

**flag - `Gr3p_F1nds_Truth`**
