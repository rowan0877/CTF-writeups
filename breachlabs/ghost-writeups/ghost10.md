# GHOST10 WRITEUP

1. connect to the ghost10 stage using `ssh ghost10@204.168.229.209 -p 2222`

2. after logging in, we list the files in the home directory using `ll` and find a file named `session-tokens.log`.

3. reading the file shows a large number of token-looking strings, with many of them repeated.

4. we can filter the entries containing `_` and sort them using `cat session-tokens.log | grep _ | sort -h`.

5. while going through the output, we find one token that stands out:

    `Str1ngs_R3v34l`

6. this is the credential for the next stage.

**flag - `Str1ngs_R3v34l`**
