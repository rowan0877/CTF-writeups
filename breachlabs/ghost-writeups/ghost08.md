# GHOST8 WRITEUP

1. connect to the ghost8 stage using `ssh ghost8@204.168.229.209 -p 2222`

2. after logging in, we see that the level tells us that `/proc` remembers what the shell forgets. Since there are no useful files in the home directory, we check the running processes using `ps aux | grep ghost8`.

3. the output shows a Python daemon running as `ghost8`:

    `python3 /usr/local/bin/level8-daemon.py`

4. since the level specifically mentions `/proc`, we can inspect the process information through `/proc/<PID>`.

5. we first check the environment of the processes using `cat /proc/<PID>/environ`. Some processes give us `Permission denied`, but we are able to access the environment of process `41`.

6. using `cat /proc/41/environ` gives us:

    `ANALYST_KEY=Pr0c_T3lls_4ll`

7. the value of `ANALYST_KEY` is the password for the next stage.

**flag - `Pr0c_T3lls_4ll`**
