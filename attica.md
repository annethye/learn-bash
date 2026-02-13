# Attica
Attica, a clothing store, has asked you to help them configure their environment.

### 1. Print the working directory.
```bash
$ pwd
/home/ccuser/workspace/clothing
```

### 2. Create and open a file in nano called hello.txt.
```bash
$ nano hello.txt
```

### 3. Save the string, “Hello, I am nano” in hello.txt
```
“Hello, I am nano”
```
Remember to do the following:  
<kbd>Ctrl</kbd> + <kbd>o</kbd> to save file  
<kbd>Enter</kbd> to confirm  
<kbd>Ctrl</kbd> + <kbd>x</kbd> to exit nano  

and clear the terminal.
```bash
$ clear
```

### 4. Use nano to open the bash profile.
```bash
$ nano ~/.bash_profile
```

### 5. In the bash profile, add a greeting with the word “Hello”
```bash
$ nano ~/.bash_profile
```
```bash
echo "Hello Sunshine!"
```
Remember to save file, exit nano and clear the terminal.

### 6. Make the greeting available in the current session.
You should see the greeting you created.
```bash
$ source ~/.bash_profile
Hello Sunshine!
```

### 7. Create two aliases. The first alias should be p for the pwd command and ll for the ls -la command.
```bash
$ nano ~/.bash_profile
```
```bash
echo "Hello Sunshine!"
alias p="pwd"
alias ll="ls -la"
```
Remember to save file, exit nano and clear the terminal.

### 8. Make the aliases available in the current session.
```bash
$ source ~/.bash_profile
Hello Sunshine!
```

### 9. Test out the aliases you created for the pwd and ls -la command.
```bash
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

### 10. Create and export the USER environment variable, setting it equal to your name.
```bash
$ nano ~/.bash_profile
```
```bash
echo "Hello Sunshine!"
alias p="pwd"
alias ll="ls -la"
export USER="Me Myself and I"
```
Remember to save file, exit nano and clear the terminal.
### 11. Make the aliases available in the current session.
```bash
$ source ~/.bash_profile
Hello Sunshine!
```

### 12. Echo the USER variable.
```bash
$ echo $USER
Me Myself and I
```

### 13. Change the PS1 environment variable, setting it equal to ">> ".
```bash
$ nano ~/.bash_profile
```
```bash
echo "Hello Sunshine!"
alias p="pwd"
alias ll="ls -la"
export USER="Me Myself and I"
export PS1=">> "
```
Remember to save file, exit nano and clear the terminal.

### 14. Make the prompt available in the current session.
```bash
$ source ~/.bash_profile
Hello Sunshine!
>> 
```

### 15. Test out the prompt by typing the two aliases you created earlier.
```bash
>> p
/home/ccuser/workspace/clothing
>> ll
total 4
drwxr-xr-x 2 ccuser ccuser 152 Jun 11 10:49 .
drwxr-xr-x 1 ccuser ccuser  22 Jun 11 10:42 ..
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 dresses.txt
-rw-r--r-- 1 ccuser ccuser  19 Jun 11 10:49 hello.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 jackets.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 pants.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 scarves.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 shirts.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 socks.txt
-rw-r--r-- 1 ccuser ccuser   0 Jun 11 10:42 sweaters.txt
```

### 16. Echo the HOME variable.
```bash
>> echo $HOME
/home/ccuser
```

### 17. Echo the PATH variable.
```bash
>> echo $PATH
/home/ccuser/.bin:/home/ccuser/node_modules/.bin:/home/ccuser/.gem/ruby/2.3.0/bin:/home/ccuser/.composer/vendor/bin:/home/ccuser/.bin:/home/ccuser/node_modules/.bin:/home/ccuser/.gem/ruby/2.3.0/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

### 18. Return a list of environment variables.
```bash
>> env
HOSTNAME=3fce011f59b0
GEM_HOME=/home/ccuser/.gem/ruby/2.3.0
TERM=xterm
USER=Me Myself and I
EXPIRES_AT=1749642008
NLTK_DATA=/home/ccuser/.nltk_data
PATH=/home/ccuser/.bin:/home/ccuser/node_modules/.bin:/home/ccuser/.gem/ruby/2.3.0/bin:/home/ccuser/.composer/vendor/bin:/home/ccuser/.bin:/home/ccuser/node_modules/.bin:/home/ccuser/.gem/ruby/2.3.0/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
CODEX_RUNNER_PATH=/var/codecademy/codex/runners
PWD=/home/ccuser/workspace/clothing
MPLBACKEND=agg
LANG=en_US.UTF-8
SESSION_ID=51dcfcc7-4d25-41c0-ba07-e3a523b5c8b8
TZ=Etc/UTC
PS1=>>
SHLVL=1
HOME=/home/ccuser
LOG_LEVEL=2
WORKSPACE_SERVICE_HOST=https://workspace.production-eks.codecademy.com
EIN_IMAGE=default
PYTHONPATH=/var/codecademy/runner_contexts/python:
_=/usr/bin/env
```