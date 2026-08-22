# TASK
#### Find the password stored in the file data.txt and is the only line of text that occurs only once
- Password found in the previous level: VR1ljMayciFxbnUokuQmJFw6QC9VKtub
# Solution
- First, we can try using ```cat``` to read the file, and it results in lots of lines
``` bash
9E3UGT9z02VsqTV4nvnLWD5pOCYpeMpu
O5ffmD1gTxN6wqrVj7s4qCGjViq2Eqa6
I8fJN0v9oiPS7HFj6zQJK32Jyn7mYw2Y
U6fRtWGxxx2JgitTcRpI8Eni5yrBX5uN
vUvJ0fcRGiyPVnxkyQvYT0EPmlYIsUMQ
IbdwbkaNWVGPrvL1xQCatdfRxoDKUxma
1QDbI0z3b488UD7pbhxxzAscVKVGJIqi
vV6s2Yby5gSVRdjhpxtCxVCYgXAcxjaR
xmeI3qSdYRGdE1hnvHojftBAH34FmdVh
and so on...
```
- If we use the command ```sort data.txt``` and see that there are lots of repeated line, which look something like this
```bash
0LTDNpAmqqfuE0FlE0ksGf6c0Kraspzs
0LTDNpAmqqfuE0FlE0ksGf6c0Kraspzs
0LTDNpAmqqfuE0FlE0ksGf6c0Kraspzs
0LTDNpAmqqfuE0FlE0ksGf6c0Kraspzs
0LTDNpAmqqfuE0FlE0ksGf6c0Kraspzs
0LTDNpAmqqfuE0FlE0ksGf6c0Kraspzs
1cKKjk7M0Pl2cPUbYgc9W4307bYC0ohF
1cKKjk7M0Pl2cPUbYgc9W4307bYC0ohF
1cKKjk7M0Pl2cPUbYgc9W4307bYC0ohF
1cKKjk7M0Pl2cPUbYgc9W4307bYC0ohF
1cKKjk7M0Pl2cPUbYgc9W4307bYC0ohF
1PesxCa7cihwvCvzBeKAcjKkjUwp7i2z
1PesxCa7cihwvCvzBeKAcjKkjUwp7i2z
1PesxCa7cihwvCvzBeKAcjKkjUwp7i2z
1PesxCa7cihwvCvzBeKAcjKkjUwp7i2z
1PesxCa7cihwvCvzBeKAcjKkjUwp7i2z
and more...
```
- Since the password is stated to ```occur only one```, we can either scrolling through these lines and see which is the one that isn't repeated, or we can use ```uniq -u```
- ```sort data.txt | uniq -u```
- The ```uniq -u``` will display only unique line, which is the password we are looking for.
- Output: ```EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl```
## Password
## ```EjmOSvuAu7sGAHqHVcBDPirRe9T03kxl```
