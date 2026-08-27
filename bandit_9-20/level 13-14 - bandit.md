# TASK
#### Find the password for the next level stored in ```/etc/bandit_pass/bandit14``` and can only be read by user ```bandit14```. For this level, you don’t get the next password, but you get a private ```SSH key``` that can be used to log into the next level. Look at the commands that logged you into previous bandit levels, and find out how to use the key for this level.
#### The task also come with a hint: 
```A hint file can be found in the home directory and make sure to read the error messages as they are informative.```
- Password found in the previous level: qQYQiHOBPR8zR61qxYqX45quvihF2uzk
# Solution
- As the hint stated, we first try to view the ```HINT``` file in the home directory.
```bash
bandit13@bandit:~$ ls -la
total 28
drwxr-xr-x   2 root     root     4096 Jun 24 14:59 .
drwxr-xr-x 150 root     root     4096 Jun 24 15:02 ..
-rw-r--r--   1 root     root      220 Feb 13  2026 .bash_logout
-rw-r--r--   1 root     root     3851 Jun 24 14:50 .bashrc
-rw-r--r--   1 root     root      807 Feb 13  2026 .profile
-rw-r-----   1 bandit14 bandit13  467 Jun 24 14:59 HINT
-rw-r-----   1 bandit14 bandit13 2602 Jun 24 14:59 sshkey.private
bandit13@bandit:~$ cat HINT
If you have trouble with this level, note the following:

1) As for all other levels, this level has a website with information:
   https://overthewire.org/wargames/bandit/bandit14.html
2) No, the level is not broken. To verify, see:
   https://status.overthewire.org/
3) The current version of OverTheWire prevents logging in from one
   level to another via localhost. Log out, and see 1)
4) If you get errors, read the error message on your screen.
   We mean it!
```
## Password
## ```(Password)```
