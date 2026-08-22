# TASK
#### Find the password for the next level stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
- Password found in the previous level: pYfOY6HwUsDj5rL9UvyhU7MCmv8vN5Ro
# Solution
- With the given description, we can use the command below to get the password
```cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'```
- This command combine ```cat``` with ```tr```. The ```tr 'A-Za-z' 'N-ZA-Mn-za-m'``` is an implemention of ```ROT13``` (Roate13). While ```'A-Za-z'``` define the searching spaces and look for and tell ```tr```to find uppercase letters from A to Z followed by every lowercase one, ```'N-ZA-Mn-za-m'```define the replacement mapping for the input and the replacement.
- Output
```bash
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
```
## Password
## ```GROozWPO8QyN0mGrjUkID0WCYkZiQxrN```
