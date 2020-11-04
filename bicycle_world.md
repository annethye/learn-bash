
# Bicycle World
Welcome to Bicycle World, the premier text-based bicycle shop! This shop is only accessible to programmers like you, who are familiar with the command line.

In this project, you’ll use the commands you learned to navigate and edit the filesystem of this special shop.

The starting filesystem is shown below. (Bicycle World recently changed owners, who named the main directory bicycle-world-ii.)

![alt text](images/bicycleworld1.png)

### 1. Print the working directory.
```
$ pwd
/home/ccuser/workspace/bicycle-world-ii
```

### 2. List the files and directories in the working directory.
```
$ ls
brands.txt  freight  mountain  racing
```

### 3. Change directories to the freight/ directory.
```
$ cd freight/
```

### 4.
List the files and directories in the working directory.
```
$ ls
messenger  porteur
```

### 5. Change directories to the porteur/ directory.
```
$ cd porteur/
```

### 6. Change directories up two levels to the bicycle-world-ii/ directory.
List the files and directories in the bicycle-world-ii/ directory.
```
$ cd ../..
$ ls
brands.txt  freight  mountain  racing
```

### 7. Change directories to the mountain/downhill/ directory.
```
$ cd mountain/downhill/
```

### 8. Make a file called dirt.txt.
```
$ touch dirt.txt
```

### 9. Make a file called mud.txt.
```
$ touch mud.txt
```

### 10. List the files and directories in the downhill/ directory.
```
$ ls
dirt.txt  heavyweight  lightweight  mud.txt
```

### 11. Downhill biking is dangerous: In the downhill/ directory, make a directory called safety/.
```
$ mkdir safety
```

### 12. Change directories to the bicycle-world-ii/ directory.
```
$ cd ../..
```

### 13. List the contents of lsthe bicycle-world-ii/ directory.
```
$ ls
brands.txt  freight  mountain  racing
```

### 14. The shop is adding a new type of bike! In bicycle-world-ii/, make a directory called bmx/.
```
$ mkdir bmx
```

### 15. Without changing directories from bicycle-world-ii/, make a file in the bmx/ directory called tricks.txt.
```
$ touch bmx/tricks.txt
```

### 16. List all files and directories in the current directory.
```
$ ls
bmx  brands.txt  freight  mountain  racing
```
