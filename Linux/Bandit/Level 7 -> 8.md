# Level 7 → 8 — Search for a word in a large file

## **Objective:** Find the password in `data.txt`, on the same line as the word `millionth`.

**Command:**

```bash
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ grep millionth data.txt
millionth	VR1ljMayciFxbnUokuQmJFw6QC9VKtub
```

**Steps:**

1. Checked the current directory with `ls` and found `data.txt`.

2. Recognized that searching a large file manually would be inefficient.

3. Used `grep` to search for the word `millionth`.

4. Examined the matching line printed by the command.

**Password extraction:** `grep` printed the entire line containing `millionth`. The password appeared next to that word, so I extracted the password from the output.

**What I learned:**

- `grep` searches text for a specified pattern.

- Its basic structure is `grep SEARCH_WORD FILE`.

- By default, it prints the entire matching line, not just the matching word.

- It is useful for searching large text files efficiently.
