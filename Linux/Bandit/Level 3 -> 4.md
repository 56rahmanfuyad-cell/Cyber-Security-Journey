## Level 3 → 4 — Find a hidden file

**Objective:** Find the password inside a hidden file in the `inhere` directory.

**Commands:**

```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
bandit3@bandit:~/inhere$
```

**Steps:**

1. Found the `inhere` directory.

2. Entered it using `cd inhere`.

3. Used `ls`, which appeared to show no files.

4. Used `ls -a` to display hidden entries.

5. Found the file named `...Hiding-From-You`.

6. Read it using `cat`.

**Password extraction:** The contents of `...Hiding-From-You` revealed the password for `bandit4`.

**What I learned:**

- Linux hides filenames beginning with `.` from normal `ls` output.

- `ls -a` shows hidden entries.

- `.` means the current directory; `..` means the parent directory.

- The three dots in `...Hiding-From-You` are part of the actual filename.
