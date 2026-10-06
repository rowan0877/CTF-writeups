# GHOST7 WRITEUP

1. connect to the ghost7 stage using `ssh ghost7@204.168.229.209 -p 2222`

2. after listing the files in the current directory, we find a file named `transmission.dat`.

3. using `cat transmission.dat` shows that the file contains a hex dump instead of normal readable text.

    `00000000: 5244 4e6a 4d47 517a 587a 4279 5830 5178`
    
    `00000010: 4d77 3d3d 0a`

4. looking at the ASCII representation on the right side of the hex dump, we can see that it contains a Base64 encoded string split across two lines.

    `RDNjMGQzXzByX0Qx`
    
    `Mw==`

5. combine both parts to get the complete Base64 string:

    `RDNjMGQzXzByX0QxMw==`

6. decode the Base64 string using `echo "RDNjMGQzXzByX0QxMw==" | base64 -d`.

7. this gives us the password for the next stage:

    `D3c0d3_0r_D13`

**flag - `D3c0d3_0r_D13`**
