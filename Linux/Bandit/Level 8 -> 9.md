# Level 8 → 9 — Find the line that appears only once

## **Objective:** Find the only line in `data.txt` that occurs only once.

**Terminal:**

```bash
bandit8@bandit:~$ ls
data.txt
#bandit8@bandit:~$ head data.txt
#93zS64a8V2Lb9UEh2Jflq30EJwZ8qkZ8
#.................................
#1uO2FE90IVExrUXcUeTxrNeGny2OoXLL
#K4roE2HAD3BqcEXVXz5n0aorOKptGW9U
bandit8@bandit:~$ sort data.txt|uniq -u
EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl
bandit8@bandit:~$ 

```

**Steps:**

1. Checked the current directory with `ls` and found `data.txt`.

2. Used `head data.txt` to view the first 10 lines and understand what the file contained.

3. Used `sort data.txt` to arrange the lines alphabetically, placing identical lines next to each other.

4. Used `uniq -u` to display the line that appears only once.

5. Combined both commands using a pipe (`|`) so the sorted output went directly to `uniq -u`.

**Password extraction:** `sort data.txt | uniq -u` displayed the only line that occurs once, revealing the password for `bandit9`.

**What I learned:**

- `sort` arranges lines alphabetically. It displays the sorted output without changing the original file.

- `uniq -u` displays lines that occur only once among adjacent lines. This is why sorting first is important: identical lines need to be next to each other.

- `|` is called a **pipe**. It takes the output of one command and sends it as input to another command.

- In `sort data.txt | uniq -u`, the `sort` command runs first, and its output is passed directly to `uniq -u`. I don't need to save the sorted output in a separate file.

- A pipe lets me connect commands so they work together to complete a task. Its general structure is `COMMAND1 | COMMAND2`.

***NB: If only uniq -u was used , it will read `data.txt` and print lines that do not have an identical line immediately before or after them.***

***The problem is that `data.txt` isn't sorted. original `data.txt` isn't sorted. Running `sort data.txt` only displayed the sorted output; it didn't change the file itself.
Identical lines might be far apart, so `uniq -u` may treat repeated lines as unique simply because they aren't next to each other.***




