# Lingua Franca - An Offline Project
Lingua Franca, a translation service, has asked you to help them manage their file system and configure their environment.

## Navigating the File System
The file structure for this project consists of language files ending in .txt grouped under various sub-directories taking the name of continents. There is a separate sub-directory called todo which also contains language files grouped under continent names.

For example, a top-level view would give you this:

```
africa/  asia/  europe/  northamerica/  southamerica/  spanish.txt  todo/
```

A sub-directory view would give you the following. This is the asia subdirectory:

```
arabic.txt  hebrew.txt  hindi.txt  japanese.txt  korean.txt  malay.txt
```

The todo sub-directory view would appear like this:
```
africa/  asia/  europe/
```

### 1. Navigate to the lingua-franca/ project directory in your own file system.
```
$ cd /home/anne/lingua-franca
```

### 2. Print the working directory.
```
$ pwd
/home/anne/lingua-franca
```

### 3. List the content of the current working directory.
```
$ ls
africa/  asia/  europe/  northamerica/  southamerica/  spanish.txt  todo/
```

### 4. Make a new directory called world in the current directory.
```
$ mkdir world
```

### 5. Create a new file, esperanto.txt in the world directory and list the content of the world directory.
```
$ touch world/esperanto.txt
$ ls world
esperanto.txt
```

## Viewing and Changing the File System

### 6. List all the contents of the current working directory based on the following constraints:

- content must include hidden files and directories
- content must appear in long format
- content must be sorted based on the time they were last modified.

Which directory would appear first?   
The last file/directory touched was world, so it appears first.
```
$ ls -alt
total 12
drwxr-xr-x 1 anne 197609 0 Jun 11 13:58 world/
drwxr-xr-x 1 anne 197609 0 Jun 11 13:58 ./
drwxr-xr-x 1 anne 197609 0 Jun 11 13:27 ../
drwxr-xr-x 1 anne 197609 0 Jun 11 13:24 todo/
drwxr-xr-x 1 anne 197609 0 Jun 11 13:24 southamerica/
drwxr-xr-x 1 anne 197609 0 Jun 11 13:24 northamerica/
drwxr-xr-x 1 anne 197609 0 Jun 11 13:24 europe/
drwxr-xr-x 1 anne 197609 0 Jun 11 13:24 asia/
drwxr-xr-x 1 anne 197609 0 Jun 11 13:24 africa/
-rw-r--r-- 1 anne 197609 0 Jun 11 13:24 spanish.txt
```

### 7. List the content of the europe directory. Notice that a file, chinese.txt doesn't belong there. Move that file to the correct directory, asia.
```
$ ls europe
chinese.txt  english.txt  french.txt  german.txt  italian.txt  portuguese.txt  russian.txt
$ mv europe/chinese.txt asia
```

### 8. List the current working directory. Notice that the file spanish.txt needs to be categorized somewhere. 
Copy it to the following directories: europe, northamerica, and southamerica. Then remove it from the current directory.
```
$ ls
africa/  asia/  europe/  northamerica/  southamerica/  spanish.txt  todo/  world/
$ cp spanish.txt europe/
$ cp spanish.txt southamerica/
$ cp spanish.txt northamerica/
$ rm spanish.txt
```
Notice that you can copy multiple files into a single directory, but you cannot copy a single file to multiple directories.

### 9. A directory called todo contains subdirectories of continents with language files in them. List the contents of the directory.
```
$ ls todo/*
todo/africa:
afrihili.txt

todo/asia:
bengali.txt  punjabi.txt

todo/europe:
yiddish.txt
```

### 10. Copy these files to their appropriate locations under the current top-level directory.
```
$ cp todo/africa/* africa/
$ cp todo/asia/* asia
$ cp todo/europe/* europe/
```

### 11. Then remove all the files and directories of todo/ excluding the todo directory in one step.
```
$ rm -r todo/*
```

## Redirecting Input and Output

### 12. List all the files in the asia/ directory and save it in a file, asian_language_files.txt in the todo/ directory.
```
$ ls asia > todo/asian_languages_files.txt
```
```
$ cat todo/asian_languages_files.txt
arabic.txt
bengali.txt
chinese.txt
hebrew.txt
hindi.txt
japanese.txt
korean.txt
malay.txt
punjabi.txt
```

### 13. Instead of writing the contents of a file with a file editor, echo the statement "Welkom by die Lingua Franca vertaaldienste." into the file afrikaans.txt in the africa directory.
```
$ echo "Welkom by die Lingua Franca vertaaldienste." > africa/afrikaans.txt
```
```
$ cat africa/afrikaans.txt
Welkom by die Lingua Franca vertaaldienste.
```

### 14. Some of the files in our project which end with the suffix, .txt, have no content in them. List the files, across all the continent directories, that end with .txt that have no content and save the listing in a file, empty_files.txt, in the todo/ directory.
When a file as no content the word count is zero. So let's count the words in all .txt files in the immediate subdirectories and pipe the output to grep, which in turn filters lines containing the character 0 and writes them to the file emptyfile.txt.
```
 wc -w */*.txt | grep 0 > todo/emptyfile.txts 
```

### 15. Display the content of todo/empty_files.txt to list all the empty files across all the continent directories.
```
$ cat todo/emptyfile.txt
  0 africa/afrihili.txt
  0 asia/bengali.txt
  0 asia/chinese.txt
  0 asia/hebrew.txt
  0 asia/hindi.txt
  0 asia/japanese.txt
  0 asia/punjabi.txt
  0 europe/french.txt
  0 europe/german.txt
  0 europe/italian.txt
  0 europe/russian.txt
  0 europe/spanish.txt
  0 europe/yiddish.txt
  0 northamerica/french.txt
  0 northamerica/spanish.txt
  0 southamerica/spanish.txt
  0 world/esperanto.txt
```

### 16. The name of our translation service is Lingua Franca, however some of the files mistakenly spell it as Lingua-Franca. Replace the string 'Lingua-Franca' with 'Lingua Franca' in all occurrences in all the .txt files.
First check how many occurences there are of Lingua-Franca across all text files:
```
$ grep -l 'Lingua-Franca' */*.txt | wc -l
6
$ grep -l 'Lingua-Franca' */*.txt
asia/arabic.txt
asia/malay.txt
europe/english.txt
europe/portuguese.txt
northamerica/english.txt
southamerica/portuguese.txt
```
Using the option `-l` prints the name of the file containing at least one match. `*/*.txt` matches text files one level deep.
We could also use `grep -Rl --include="*.txt" 'Lingua-Franca' .` where the option `-R` recursively searches through all directories and subfolders.

Now let's replace Lingua-Franca with Lingua Franca, using the `-i` option to edit the file directly and the `-g` option to replace every instance.
```
$ sed -i 's/Lingua-Franca/Lingua Franca/g' */*.txt
```
Let's confirm that all instances of Lingua-Franca have been replaced.
```
$ grep -Rl 'Lingua-Franca' */*.txt | wc -l
0
```

## Task Group 4: Configuring the Environment
### 17. Create and open the bash profile with your favorite editor.
```
$ nano ~/.bash_profile
```

### 18. In the bash profile, add a greeting of your choice.
```
echo "Hello and Welcome to Lingua Franca"
```
<kbd>Ctrl + O</kbd> to save, <kbd>enter</kbd> to confirm, <kbd>Ctrl + X</kbd> to exit and `clear` the terminal window.

### 19. Make the greeting available in the current session.
Source the bash profile.
```
$ source ~/.bash_profile
Hello and Welcome to Lingua Franca
```

### 20. Create Aliases
Open the bash profile:
```
nano ~/.bash_profile
```
and create three aliases:
- md for the mkdir command
- d for date
- hy for history
```
alias md='mkdir'
alias d='date'
alias hy='history'
```
<kbd>Ctrl + O</kbd> to save, <kbd>enter</kbd> to confirm, <kbd>Ctrl + X</kbd> to exit and `clear` the terminal window.


### 21. Source the bash profile to make the aliases available in the current session.
```
source ~/.bash_profile
Hello and Welcome to Lingua Franca
```

### 22. Test out the aliases you created for the mkdir, date, and history commands. 
Create the directory translations/ and list the content.
```
$ md translations
$ ls
africa/  asia/  europe/  northamerica/  southamerica/  todo/  translations/  world/
$ d
Fri Jul 11 15:16:38 UTC 2025
$ hy
    1  md translations
    2  ls
    3  d
    4  hy
```

### 23. Change the command line promt
Open the bash profile.  
```
nano ~/.bash_profile
```
Create and export the PS1 environment variable, setting it equal to a prompt of your choice.
Remember to leave a space after your prompt.
```
export PS1="Lingua Franca >> "
```
<kbd>Ctrl + O</kbd> to save, <kbd>enter</kbd> to confirm, <kbd>Ctrl + X</kbd> to exit and `clear` the terminal window.


### 24. Make the new prompt available in the current session.
Source the bash profile.
```
# source ~/.bash_profile
Lingua Franca >> 
```

### 25.  Test out the prompt by typing the names of the aliases you created. 
Remember to list the directory created from the mkdir alias.
```
$ md oceania
$ ls
africa/  asia/  europe/  northamerica/  oceania/  southamerica/  todo/  translations/  world/
$ d
Fri Jul 11 15:19:38 UTC 2025
$ hy
    1  md translations
    2  ls
    3  d
    4  hy
    5  nano ~/.bash_profile 
    6  clear
    7  source ~/.bash_profile
    8  md oceania
    9  ls
    10 d
    11 hy
```

### 26. Return a list of environment variables
```
Lingua Franca >> env
LANG=da_DK.UTF-8
TZ=Europe/Copenhagen
HOSTNAME=ubuntu-vbox
PWD=/home/anne/lingua-franca
HOME=/home/anne
TERM=xterm-256color
SHLVL=1
PATH=/home/anne/.local/bin:/home/anne/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
PS1='Lingua Franca >> '
_=/usr/bin/env

```
We can see that the PS1 variable has been changed.