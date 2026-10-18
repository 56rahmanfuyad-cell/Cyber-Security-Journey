# Level 0 → 1 — Read the `readme` file

## **Objective:** Find the next level's password in a file named `readme` in the home directory.

Terminal:

```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
bandit0@bandit:~$
```

**Steps:**

1. Used `ls` to list the files in the current directory.

2. Found a file named `readme`.

3. Used `cat readme` to display its contents.

**Password extraction:** The output of `cat readme` contained the password for `bandit1`.

**What I learned:**

- `ls` lists directory contents.

- `cat` displays file contents.

- A filename can be passed as an argument to a command.

---
