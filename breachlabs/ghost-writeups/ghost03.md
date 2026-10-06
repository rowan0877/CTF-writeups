# GHOST3 WRITEUP

1. connect to the ghost3 stage using `ssh ghost3@204.168.229.209 -p 2222` & password: `figure it out`

2. upon listing the files inside the landing directory, we notice a `map.txt` file which tells us the locations of various workstation folders.

3. the mapped locations are as follows:

    `ghost3@breachlab:/var/intel$ ls archive/`
    
    `ls: cannot open directory 'archive/': Permission denied`

    `ghost3@breachlab:/var/intel$ ls ops/`
    
    `access_codes.dat` `operative_list.txt`

    `ghost3@breachlab:/var/intel$ ls public/`
    
    `report_q1.txt`

4. after investigating the contents of these files, we notice that `ops/operative_list.txt` points to `access_codes.dat` for the credentials.

5. using `cat` to show the contents inside the `access_codes.dat` file gives us the flag.

flag - `P3rm1ss10ns_M4tt3r`
