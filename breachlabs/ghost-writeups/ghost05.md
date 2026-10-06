# GHOST5 WRITEUP

1. connect to the ghost5 level using ssh

2. read the `README` file using `cat README` which tells us that there is a service running on the machine and that `ss` and `netstat` are not available. It also says that we can use `nc` and `curl`.

3. use `nmap localhost -p-` to scan all the ports and find the open ports.

4. since the README says there are two ports involved, we can try connecting to the open ports using `nc`.

5. connecting to port `30100` using `nc localhost 30100` gives us a message saying that the authentication token is `GHOST` and that the secure channel is on port `30101`.

6. connect to port `30101` using `nc localhost 30101` and send `AUTHENTICATE: GHOST`.

7. the service then gives us the credential `P0rts_N3v3r_L13`.

flag - `P0rts_N3v3r_L13`
