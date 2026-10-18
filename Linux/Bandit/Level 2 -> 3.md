# Level 2 → 3 — Read a filename containing spaces

## **Objective:** Read the file named `--spaces in this filename--`.

**Terminal:**

```bash
bandit2@bandit:~$ ls
--spaces in this filename--
bandit2@bandit:~$ cat "./--spaces in this filename--"
7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME
bandit2@bandit:~$
```

**Steps:**

1. Identified the filename from the challenge.

2. Recognized that the filename contained spaces.

3. Enclosed the entire filename in double quotes so the shell treated it as one argument.

4. Used `cat` to display its contents.

**Password extraction:** The output contained the password for `bandit3`.

**What I learned:**

- Spaces normally separate arguments in shell commands.

- Quotes allow a filename containing spaces to be passed as one argument.

- Tab completion can help avoid typing long filenames incorrectly.
