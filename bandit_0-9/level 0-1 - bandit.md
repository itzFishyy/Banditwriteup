# Task
#### Find the password in a file called readme that located in the home directory
- Password of the previous level: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
# Solution:
- Using the ``` ls -la ``` command to view all the files in the folder
- Notice that there is a file named ```-```
- However, using ```cat -``` will give us nothing since ```cat``` treat ```-``` like a standard input (Stdin)
- To read it, we can simply add ```./```, which will look something like this
``` cat./-```
#### The password/Output
```PK8fYLZg2hnHSz83plBL1iEPKdD3QToB```
