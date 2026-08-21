# TASK
#### Find the password for the next level, which is stored somewhere on the server and has all of the following properties:
#### - Owned by user bandit7
#### - Owned by group bandit6
#### - 33 bytes in size

- Password found in the previous level: pXa26xhMWaC2SvDotA4r9EgZkulOeSBW
# Solution
- Based on the given properties, we can try to use ```find``` like this
```bash
find /* -user bandit7 -size 33c -group bandit6
```
- However, the output will contain a lot of files with the ```Permission denied``` messages
```bash
find: ‘/boot/efi’: Permission denied
find: ‘/boot/lost+found’: Permission denied
find: ‘/dev/mqueue’: Permission denied
find: ‘/dev/shm’: Permission denied
find: ‘/drifter/drifter14_src/axTLS’: Permission denied
find: ‘/etc/xinetd.d’: Permission denied
find: ‘/etc/credstore.encrypted’: Permission denied
find: ‘/etc/credstore’: Permission denied
find: ‘/etc/multipath’: Permission denied
find: ‘/etc/polkit-1/rules.d’: Permission denied
find: ‘/etc/stunnel’: Permission denied
find: ‘/etc/sudoers.d’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/home/ubuntu’: Permission denied
and so on...
```
- Instead of looking for the password just by scrolling, we can add ```2>/dev/null``` to hide those ```Permission denied``` messages
```bash
find -user bandit7 -size 33c -group bandit6 2>/dev/null
```
- Output: ```./var/lib/dpkg/info/bandit7.password```
- Then, use ```cat``` with the path above and get the password for the next level.
## Password
## ```Bmnnvf82KzQlfxgAI2d1zYbr1u9pr3E3```
