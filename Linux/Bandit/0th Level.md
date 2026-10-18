# Level o-- Connect to Bandit

## Objective : Log in to the Bandit Server

Terminal:

```bash
fuyad@Fuyadslappy:~/CSJ/Linux$ ssh -p 2220 bandit0@bandit.labs.overthewire.org
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

backend: gibson-0
bandit0@bandit.labs.overthewire.org's password: 

```

**Steps:**

1. Opened the terminal on my Ubuntu computer.

2. Used SSH to connect to the remote Bandit server.

3. Accepted the server's fingerprint prompt on the first connection.

4. Logged in with the initial username and password: `bandit0`.

**Password extraction:** No password was extracted from a file in this introductory step. The initial password was provided by the challenge instructions.

**What I learned:**

- `ssh` connects to a remote computer.

- `-p 2220` specifies the port.

- My local Ubuntu and the Bandit server are two different systems.
