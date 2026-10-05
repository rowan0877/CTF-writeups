# GHOST1 — Writeup

1. Connect to the `ghost1` stage using:

   ```bash
   ssh ghost1@204.168.229.209 -p 2222
   ```

   **Password:** Please refer to the GHOST0 writeup.

2. List the files in the current directory using the `ls` command.

3. You will find four files named `-`, `--help`, `file name`, and `MANIFEST`.

4. Use `cat ./<filename>` to view the contents of files with unusual filenames, especially those beginning with `-`.

5. Three of the files — `-`, `--help`, and `file name` — display random strings.

6. Through trial and error, we find that the flag for the next stage is hidden inside one of these files.

   **Flag:** `D4shIsN0tAFl4g`
