## Level 5 → 6 — Find a file by its properties

**Objective:** Find a file somewhere under `inhere` that is:

- Human-readable.

- Exactly 1,033 bytes.

- Not executable.

**Terminal:**

```bash
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere04  maybehere08  maybehere12  maybehere16
maybehere01  maybehere05  maybehere09  maybehere13  maybehere17
maybehere02  maybehere06  maybehere10  maybehere14  maybehere18
maybehere03  maybehere07  maybehere11  maybehere15  maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ file ./maybehere07/.file2
./maybehere07/.file2: ASCII text, with very long lines (1000)
bandit5@bandit:~/inhere$ ls -l ./maybehere07/.file2
-rw-r----- 1 root bandit5 1033 Sep 26 21:54 ./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
pXa26xhMWaC2SvDotA4r9EgZkulOeSBW

```

**Steps:**

1. Entered the `inhere` directory.

2. Used `find . -type f -size 1033c` to search recursively for regular files exactly 1,033 bytes in size.

3. The search identified `./maybehere07/.file2`.

4. Used `file` to check its contents and found that it was ASCII text.

5. Used `ls -l` to inspect its permissions.

6. Confirmed that its permissions contained no `x` character, meaning it was not executable.

7. Read the file using `cat`.

**Password extraction:** The contents of `./maybehere07/.file2` revealed the password for `bandit6`.

**What I learned:**

- `find .` searches from the current directory downward.

- `-type f` selects regular files.

- `-size 1033c` selects files exactly 1,033 bytes in size; `c` means bytes.

- `ls -l` shows permissions, owner, group and size.

- `r` means read, `w` means write and `x` means execute.
