# TASK
#### Find the password stored in the only human-readable file in the inhere directory.
- Password found in the previous level: xzTXq1rDJQVVAzdv5cHq1TQytTWufAMq
# Solution
- First, use the ```cd inhere``` command to access the ```inhere``` directory
- Then list all the files in the ```inhere``` with ```ls -la```
```bash
total 48
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file00
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file01
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file02
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file03
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file04
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file05
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file06
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file07
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file08
-rw-r----- 1 bandit5 bandit4   33 Jun 24 14:59 -file09
drwxr-xr-x 2 root    root    4096 Jun 24 14:59 .
drwxr-xr-x 3 root    root    4096 Jun 24 14:59 ..
```
- We can use ```cat``` to each file individually to see which one contain the password that we are looking for, but doing that would be time-comsumming and quite inefficient. So instead, we can use ```file ./*``` to see the file type. The output would look something like this
```bash
/-file00: data
./-file01: data
./-file02: OpenPGP Secret Key
./-file03: data
./-file04: data
./-file05: data
./-file06: Non-ISO extended-ASCII text, with NEL line terminators
./-file07: ASCII text
./-file08: data
./-file09: data
```
- Notice that the ```-file07``` is an ASCII text, we then use ```cat ./-file07``` and find the password for the next level
- <img width="580" height="60" alt="image" src="https://github.com/user-attachments/assets/efd336fe-53a4-4da1-a249-6cba66ac1f4d" />

## Password
## ```6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG```
