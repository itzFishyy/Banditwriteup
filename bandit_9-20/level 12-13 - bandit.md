# TASK
#### Find the password for the next level stored in the file ```data.txt```, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under ```/tmp``` in which you can work. Use ```mkdir``` with a hard to guess directory name. Or better, use the command ```mktemp -d```. Then copy the datafile using ```cp```, and rename it using ```mv``` 
- Password found in the previous level: GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
# Solution
- Like the task suggest, we first create a directory with a random name using ```mktemp -d```, which give us this output:
```/tmp/tmp.OPwcmwtxi8```. Then we us ```cp``` and ```cd``` to copy the file to the temporary directory and navigate into it. We can now view the directory and see that ```data.txt``` is here.
```bash
bandit12@bandit:~$ cp data.txt /tmp/tmp.OPwcmwtxi8
bandit12@bandit:~$ cd /tmp/tmp.OPwcmwtxi8
bandit12@bandit:/tmp/tmp.OPwcmwtxi8$ ls -la
total 4
drwx------   2 bandit12 bandit12   60 Aug 25 08:16 .
drwxrwx-wt 117 root     root     2940 Aug 25 08:21 ..
-rw-r-----   1 bandit12 bandit12 2641 Aug 25 08:21 data.txt
```
- The orginal file is stated to a hexdump that has been repeatedly compressed, so we will use ```xxd -r data.txt compressed_file``` to create another file with ```gzip compressed data``` file type and contain the data.txt's contents.
- To use ```gzip```, we must rename the file into anything with ```.gz``` using ```mv``` for ```gzip``` to work. And once we decompressed the file, it will show this output
```bash
gzip: compressed_file: unknown suffix -- ignored
bandit12@bandit:/tmp/tmp.OPwcmwtxi8e$ mv compressed_file fishyy.gz
bandit12@bandit:/tmp/tmp.OPwcmwtxi8e$ gzip -d fishyy.gz
bandit12@bandit:/tmp/tmp.OPwcmwtxi8e$ file fishyy
fishyy: bzip2 compressed data, block size = 900k
```
- Now, the file is still a compressed bzip2 file ```bzip2 compressed data```, so we repeat the previous step to decompress it.
```bash
bandit12@bandit:/tmp/tmp.OPwcmwtxi8$ mv fishyy fishyy.bz2
bandit12@bandit:/tmp/tmp.OPwcmwtxi8$ bzip2 -d fishyy.bz2
bandit12@bandit:/tmp/tmp.OPwcmwtxi8$ file fishyy
fishyy: gzip compressed data, was "data4.bin", last modified: Wed Jun 24 14:58:46 2026, max compression, from Unix, original size modulo 2^32 20480
```

## Password
## ```(Password)```
