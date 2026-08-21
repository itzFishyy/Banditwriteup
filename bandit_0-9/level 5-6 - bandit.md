# TASK
#### Find the password stored in a file somewhere under the inhere directory and has all of the following properties:
#### - human-readable
#### - 1033 bytes in size
#### - not executable
- Password found in the previous level: 6C7h9GD8M6ai5nr7wo1RonrzFjj9yIrG
# Solution
- Like the previous level (4-5), we to enter the ```inhere``` directory with ```cd inhere``` and list all the files in there.
```bash
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Jun 24 14:59 .
drwxr-xr-x  3 root root    4096 Jun 24 14:59 ..
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere00
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere01
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere02
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere03
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere04
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere05
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere06
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere07
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere08
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere09
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere10
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere11
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere12
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere13
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere14
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere15
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere16
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere17
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere18
drwxr-x---  2 root bandit5 4096 Jun 24 14:59 maybehere19
```
- With the given conditions, we can use the following command to find the correct file
```bash
find . -type f -size 1033c ! -executable
```
- The ```-type f``` can reduce the range of results to only regular files, ```-size 1033c``` to looking for the file that are 1033 bytes in size and ```! -executable``` is to exclude the executables, as ```!``` means ```NOT```. Here is the output
```bash
./maybehere07/.file2
```
- With that, we can finally use ```cat``` and find the password
## Password
## ```pXa26xhMWaC2SvDotA4r9EgZkulOeSBW```
