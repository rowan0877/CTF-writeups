# GHOST6 WRITEUP

1. connect to the ghost6 stage using `ssh ghost6@204.168.229.209 -p 2222` & password: `i wont be mentioning this field anymore`

2. after logging in, the level tells us that KAEL stopped writing secrets to disk and that the shell still remembers them. It also gives us links related to `env`, `base64` and configuration.

3. after checking the current directory using `ls -a`, there are no obvious files containing the password, so we inspect the `.bashrc` file using `cat .bashrc`.

4. at the bottom of the `.bashrc` file we find multiple environment variables containing base64 encoded strings.

    `export API_DIGEST=M252X0wzNGtzXzN2M3J5dGgxbmc=`

    `export RUNTIME_TOKEN=c3lzdGVtX3Rva2VuX2dhbW1hX3Yz`

    `export CACHE_SEED=bm90X2FfcmVhbF9jcmVkZW50aWFs`

5. since the values look like base64, we can decode them using `base64 -d`.

6. decoding the `API_DIGEST` value using `echo "M252X0wzNGtzXzN2M3J5dGgxbmc=" | base64 -d` gives:

    `3nv_L34ks_3v3ryth1ng`

7. the decoded value is the credential needed for the next stage.

**flag - `3nv_L34ks_3v3ryth1ng`**
