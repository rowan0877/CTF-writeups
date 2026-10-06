# GHOST2 — Writeup

1. Connect to the `ghost2` stage using:

   ```bash
   ssh ghost2@204.168.229.209 -p 2222
   ```

2. Upon listing the contents of the current workspace, we find a folder named `investigation`.

3. Inside the `investigation` folder, we find two files named `report.txt` and `summary.txt`.

4. Using `ls -a` to list all existing and hidden contents reveals a hidden folder named `.sources`.

5. This folder contains three hidden files:

   ```text
   .source_alpha
   .source_beta
   .source_omega
   ```

6. `.source_alpha` and `.source_beta` contain random strings, but `.source_omega` reveals the flag.

   **Flag:** `H1dd3nInSh4dow`
