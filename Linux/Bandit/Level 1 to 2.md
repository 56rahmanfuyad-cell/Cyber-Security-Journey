# Level 1 → 2 — Read a file named `-`

## **Objective:** Find the password stored in a file named`-`

Terminal:

```bash
bandit1@bandit:~$ cat -
cat ./-
cat ./-
^C
bandit1@bandit:~$ cat ./-
PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
bandit1@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
fuyad@Fuyadslappy:~$
```

**Steps:**

1. Used `ls` and found a file named `-`.

2. Learned that a standalone `-` can have a special meaning in some commands, such as representing standard input.

3. Accidentally ran `cat -`, which made `cat` wait for keyboard input instead of reading the file.

4. When I typed `cat ./-` without exiting the first command, `cat` echoed my input instead of executing it as a new command.

5. Pressed `Ctrl + C` to interrupt the running command. `^C` appeared, indicating the interrupt keypress. Normally, this should return me to the shell prompt.

6. Pressed `Ctrl + D` to signal the end of input, which allowed `cat` to exit.

7. Used `cat ./-` from the shell prompt to read the actual file named `-`.

**Password extraction:** `cat ./-` displayed the file's contents, revealing the password for `bandit2`.

**What I learned:**

- `.` refers to the current directory.

- `./-` explicitly identifies a file named `-` in the current directory.

- `cat -` reads from standard input, whereas `cat ./-` reads the file named `-`.

- When a program is running in the terminal, typing a command does not execute it unless I return to the shell prompt first.

- `Ctrl + C` interrupts a running process; `Ctrl + D` signals the end of input (EOF) when a program is reading from standard input.

- `^C` is the terminal's representation of the `Ctrl + C` keypress, not an error message.
