# Level 6 → 7 — Search the entire server

## **Objective:** Find a file somewhere on the server that is:

- Owned by user `bandit7`.

- Owned by group `bandit6`.

- Exactly 33 bytes in size.

**Terminal:**

```bash
#find: ‘/var/lib/snapd/void’: Permission denied
#find: ‘/var/lib/chrony’: Permission denied
#/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3
```

**Steps:**

1. Recognized that the challenge said the file was somewhere on the server, not necessarily inside my home directory.

2. Started the search from `/`, the root of the filesystem.

3. Used `-type f` to select regular files.

4. Used `-user bandit7` to filter for files owned by `bandit7`.

5. Used `-group bandit6` to filter for files belonging to group `bandit6`.

6. Used `-size 33c` to select files exactly 33 bytes in size.

7. Used `2>/dev/null` to suppress error messages, such as permission-denied messages.

8. The search returned this path:

```text
/var/lib/dpkg/info/bandit7.password
```

9. Read the identified file:

```bash
cat /var/lib/dpkg/info/bandit7.password
```

**Password extraction:** `cat` displayed the contents of the file, revealing the password for `bandit7`.

**What I learned:**

- `/` represents the root of the entire filesystem.

- `find /` searches throughout the filesystem, subject to access restrictions.

- `-user` filters by owner.

- `-group` filters by group.

- Multiple `find` conditions must all match the same file.

- `2>/dev/null` redirects standard error to `/dev/null`, hiding error messages.

***NB : Why “Permission denied” appeared:***

`/` ***means the root directory, the top level of the filesystem...not the root user. I used*** `find /` ***to search from that top level, but I was logged in as*** `bandit6`***, not as the*** `root` ***user (administrator). Therefore, I didn't have permission to access every directory.*** 

***Adding*** `2>/dev/null` ***hides these error messages.*** ***So technically this particular command is not mendatory to clear this level.***

***These errors did not mean that the entire command had failed. `find` continued searching other accessible locations and successfully found the matching file*** 


