# Task
#### Find the password for the next level located in a file called ```--spaces in this filename``` in the home directory
- Password found in the previous level: PK8fYLZg2hnHSz83plBL1iEPKdD3QToB
# Solution
- Like the previous level, we first use the command ``` ls -la ``` to view all the files in the folder.
- We can see that there is a file named ```--spaces in this filename--```
- This filename contains spaces between the name, so obviously ```cat ./--spaces in the filename``` will not work. To deal with it, we can use ```./``` and ```\``` in our command, which look something like this
```cat ./--spaces\ in\ this\ filename--```
## The password found: ```7ZZ2LFrykP2zEyvBl4m3clcL7tGYJPME```
