# TASK
#### Find password for the next level retrieved by submitting the password of the current level to port 30000 on localhost.
- Password found in the previous level: aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
# Solution
- The challenge description has specified the machine as ```localhost``` on port ```3000```
```bash
bandit14@bandit:~$ nc localhost 30000

```
- Using the password found in the previous level
```bash
bandit14@bandit:~$ nc localhost 30000
aaWecNkG4FhxJQxz07uiwzVP6bJiYS65
Correct!
pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7
```
## Password
## ```pbLYuZtTg4MgaqfJx8jbA9gKKGqM68A7```
