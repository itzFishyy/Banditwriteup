# TASK
#### Find the password for the next level stored in the file ```data.txt```, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under ```/tmp``` in which you can work. Use ```mkdir``` with a hard to guess directory name. Or better, use the command ```mktemp -d```. Then copy the datafile using ```cp```, and rename it using ```mv``` 
- Password found in the previous level: GROozWPO8QyN0mGrjUkID0WCYkZiQxrN
# Solution
- Like the task suggest, we first create a directory with a random name using ```mktemp -d```, which give us this output:
```/tmp/tmp.9O0mlDEvXZ```. Then we us ```cp``` and ```cd``` to copy the file to the temporary directory and navigate into it. We can now view the directory and see that ```data.txt``` is here.
```bash
bandit12@bandit:~$ cp data.txt /tmp/tmp.9O0mlDEvXZ
bandit12@bandit:~$ cd /tmp/tmp.9O0mlDEvXZ
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ ls -la
total 4
drwx------   2 bandit12 bandit12   60 Aug 25 08:16 .
drwxrwx-wt 117 root     root     2940 Aug 25 08:21 ..
-rw-r-----   1 bandit12 bandit12 2641 Aug 25 08:21 data.txt
```
- The orginal file is stated to be a hexdump that has been repeatedly compressed, so we will use ```xxd -r data.txt compressed_file``` to create another file with ```gzip compressed data``` file type and contain the data.txt's contents.
- To use ```gzip```, we must rename the file into anything with ```.gz``` using ```mv``` for ```gzip``` to work. And once we decompressed the file, it will show this output
```bash
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv compressed_file arandomname.gz
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ gzip -d arandomname.gz
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file arandomname
arandomname: bzip2 compressed data, block size = 900k
```
- Now, the file is still a compressed bzip2 file ```bzip2 compressed data```, so we repeat the previous step to decompress it.
```bash
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv arandomname starwalker.bz2
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ bzip2 -d starwalker.bz2
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file starwalker
starwalker: gzip compressed data, was "data4.bin", last modified: Wed Jun 24 14:58:46 2026, max compression, from Unix, original size modulo 2^32 20480
```
- Repeat the same cycle for the next ```gzip compressed data```
```bash
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv starwalker calamitas.gz
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ gzip -d calamitas.gz
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file calamitas
calamitas: POSIX tar archive (GNU)
```
- Now, the output ```POSIX tar archive (GNU)``` has shown that the file is now a ```tar archive```, we can now extract the file with ```tar```, and remember to rename the file since it only work with a name end with ```.tar```.
- We can either use ```tar -xvf``` to show list of files being extracted on the screen.
```bash
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv calamitas supremecalamitas.tar
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ tar -xvf supremecalamitas.tar
data5.bin
```
## Keep repeating this cycle
- If the file type is ```bzip2 compressed data```, use ```bzip2```
- If the file type is```gzip compressed data```, use ```gzip```
- If the file type is```POSIX tar archive (GNU)```, use ```tar -xvf``` (so we can see the file that are being extracted and continue the cycle)
```bash
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv data5.bin data36.tar
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ tar -xvf data36.tar
data6.bin
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv data6.bin data_cai.bz2
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ bzip2 -d data_cai.bz2
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file data_cai
data_cai: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv data_cai bluearchieve.tar
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ tar -xvf bluearchieve.tar
data8.bin
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Wed Jun 24 14:58:46 2026, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ mv data8.bin gzipcompressed.gz
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ gzip -d gzipcompressed.gz
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ file gzipcompressed
gzipcompressed: ASCII text
```
- Eventually, we notice that the file is now an ASCII text, which is the password we made along the way.
- Output
```bash
bandit12@bandit:/tmp/tmp.9O0mlDEvXZ$ cat gzipcompressed
The password is qQYQiHOBPR8zR61qxYqX45quvihF2uzk
```
## IMPORTANT NOTE (I guess)
- After doing some research, i just found out that we don't need to rename the file extension to filename.tar to use ```tar```, but im just gonna leave it there lmao.
## Password
## ```qQYQiHOBPR8zR61qxYqX45quvihF2uzk```
