# Task
#### Find the password in a file called ```readme``` located in the home directory
- Password found in the previous level: 6y2kwnwK6grgvwvpvLaa2T1cpFEKOhNR
# Solution:
- Use the ``` ls -la ``` command to view all the files in the folder
- Notice that there is a file named ```-```
- However, using ```cat -``` will give us nothing since ```cat``` treats ```-``` like a standard input (stdin)
- To read it, we can simply add ```./```, which will look something like this
``` cat./-```
## The password found: ```PK8fYLZg2hnHSz83plBL1iEPKdD3QToB```
