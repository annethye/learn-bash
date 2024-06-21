# Attica
Attica, a clothing store, has asked you to help them configure their environment.

### 1. Print the working directory.
```
$ pwd
/home/ccuser/workspace/clothing
```

### 2. Create and open a file in nano called hello.txt.
```
$ nano hello.txt
```

### 3. Save the string, “Hello, I am nano” in hello.txt.

Save the file, exit nano
```
ctrl + O
enter
ctrl + x
```
and clear the terminal.
```
$ clear
```
### 4. Use nano to open the bash profile.
```
$ nano ~/.bash_profile
```

### 5. In the bash profile, add a greeting with the word “Hello” using the echo command. Save the file, exit nano, and clear the terminal.
```
$ nano ~/.bash_profile
```
```
$ clear
```

### 6. Use the source command to make the greeting available in the current session.

You should see the greeting you created.
```
$ source ~/.bash_profile
Hello Sunshine!
```

### 7. Open the bash profile, and create two aliases. The first alias should be p for the pwd command and ll for the ls -la command.

Save the file, exit nano, and clear the terminal.
```
alias p='pwd'
alias ll='ls -la'
```

### 8. Use the source command to make the aliases available in the current session.
```
$ source ~/.bash_profile
Hello Sunshine!
```

### 9. Test out the aliases you created for the pwd and ls -la command.
```
$ p
/home/ccuser/workspace/clothing
$ ll
total 4
drwxr-xr-x 2 ccuser ccuser 152 Jun 14 22:16 .
drwxr-xr-x 1 ccuser ccuser  22 Jun 14 22:16 ..
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 dresses.txt
-rw-r--r-- 1 ccuser ccuser  17 Jun 14 16:14 hello.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 jackets.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 pants.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 scarves.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 shirts.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 socks.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 14 16:12 sweaters.txt
```

### 10. Open the bash profile and create and export the USER environment variable, setting it equal to your name.

Save the file, exit nano, and clear the terminal.
```
```

### 11. Use the source command to make the aliases available in the current session.
```
```

### 12. Echo the USER variable.
```
```

### 13. Open the bash profile and create and export the PS1 environment variable, setting it equal to ">> ".

Save the file, exit nano, and clear the terminal.
```
```

### 14. Use the source command to make the prompt available in the current session.
```
```

### 15. Test out the prompt by typing the two aliases you created earlier.
```
```

### 16. Echo the HOME variable.
```
```

### 17. Echo the PATH variable.
```
```

### 18. Return a list of environment variables.
```
```