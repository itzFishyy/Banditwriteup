# CHALLENGE DESCRIPTION
#### The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
#### Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.
- Password found in the previous level: pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
# Solution
- The solution for this challenge is quite similar to ```level 14-15```, which is submit the current password to a specific port of ```30001``` on ```localhost```, so i first try to use ```nc``` like the previous level.
- However, the output gave me nothing at all, as ```nc``` does not support ```SSL/TLS``` connections at all. So i try again with ```ncat``` instead.
```bash
bandit15@bandit:~$ nc localhost 30001
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
bandit15@bandit:~$ ncat --ssl localhost 30001
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
Correct!
kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V
```
## Password
## ```kS0Hf0u5HiXFwKMKFqXvPdOTNGGa0X8V```
