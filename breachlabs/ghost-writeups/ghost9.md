# GHOST9 WRITEUP

1. connect to the ghost9 stage using `ssh ghost9@204.168.229.209 -p 2222`

2. after logging in, we find a file named `ghost-agent.core` in the current directory.

3. the level tells us that an agent process crashed and left a core dump, and that the secrets which were in memory were written to the disk. It also tells us to use `strings`, `file` and `grep`.

4. using `cat ghost-agent.core` just gives us unreadable binary data, so instead we use `strings ghost-agent.core` to extract the readable strings from the file.

5. the output contains a lot of random strings, but we can see some useful information such as `GHOST_REGION`, `AGENT_BUILD`, `LD_LIBRARY_PATH` and `AGENT_TOKEN`.

6. to make it easier to find the token, we use `strings ghost-agent.core | grep _`.

7. this gives us:

    `GHOST_REGION=eu-1`
    
    `AGENT_BUILD=2.3.1`
    
    `LD_LIBRARY_PATH=/opt/ghost/lib`
    
    `GLIBC_2.34`
    
    `AGENT_TOKEN=N01s3_Fl00r`

8. the value of `AGENT_TOKEN` is the password for the next stage.

**flag - `N01s3_Fl00r`**
