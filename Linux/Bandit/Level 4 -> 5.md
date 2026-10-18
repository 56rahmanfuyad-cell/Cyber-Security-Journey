# Level 4 → 5 — Find the human-readable file

## **Objective:** Find the only human-readable file among the files in `inhere`.

**Terminal:** 

```bash
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file02  -file04  -file06  -file08
-file01  -file03  -file05  -file07  -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG

```

**Steps:**

1. Entered the `inhere` directory.

2. Listed the files, which were named `-file00` through `-file09`.

3. Used `file ./*` to identify the type of each file.

4. Examined the results and found that `./-file07` was identified as `ASCII text`.

5. Used `cat ./-file07` to read its contents.

**Password extraction:** The contents of `-file07` revealed the password for `bandit5`.

**What I learned:**

- `file` identifies the type of data a file contains.

- The `*` is a **glob wildcard** — it matches *every* filename in that directory. The shell expands it before the command runs, Without the star I'd have to type each filename by hand.In other words, `./` pins one to the current directory, and `*` says "all of them."

- `ASCII text` indicates ordinary text that can be read.

- `./-file07` explicitly refers to a filename beginning with a hyphen.
