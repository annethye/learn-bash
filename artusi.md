# Artusi
Let’s use commands we just learned to manipulate the files and directories of Artusi, an arts supply store.

### 1. Print the working directory.
```bash
$ pwd
/home/ccuser/workspace/artusi
```

### 2. List all contents in the current directory, including hidden files and directories.
```bash
$ ls -a
.  ..  drawing  painting  sculpting
```

### 3. List all contents, in long format.
```bash
$ ls -l
total 0
drwxr-xr-x 4 ccuser ccuser 37 Mar  5  2016 drawing
drwxr-xr-x 4 ccuser ccuser 34 Mar  5  2016 painting
drwxr-xr-x 3 ccuser ccuser 18 Mar  5  2016 sculpting
```

### 4. List all contents, including hidden files and directories, in long format, ordered by the date and time they were last modified.
```bash
$ ls -alt
total 0
drwxr-xr-x 5 ccuser ccuser 54 Jun 14 14:50 .
drwxr-xr-x 1 ccuser ccuser 20 Jun 14 14:50 ..
drwxr-xr-x 4 ccuser ccuser 37 Mar  5  2016 drawing
drwxr-xr-x 4 ccuser ccuser 34 Mar  5  2016 painting
drwxr-xr-x 3 ccuser ccuser 18 Mar  5  2016 sculpting
```

### 5. Change directories to the pencils directory. 
The relative path of the pencils directory is `drawing/pencils/`
```bash
$ cd drawing/pencils/
```

### 6. List all contents in the current working directory, including hidden files and directories.
```bash
$ ls -a
.  ..  color.txt  graphite.txt
```

### 7. Copy the file color.txt to graphite.txt.
Contents of files
```bash
$ cat color.txt 
A colored pencil, coloured pencil (see spelling differences) or pencil crayon is an art medium constructed of a narrow, pigmented core encased in a wooden cylindrical case.
Source: Wikipedia

$ cat graphite.txt 
Graphite pencils are used for both writing and drawing and result in durable markings: though writing is easily removable with an eraser, it is otherwise resistant to moisture, most chemicals, ultraviolet radiation, and natural aging.
Source: Wikipedia
```
Copy color file to graphite file
```bash
$ cp color.txt graphite.txt
```
This results in the following:
```bash
$ cat graphite.txt 
A colored pencil, coloured pencil (see spelling differences) or pencil crayon is an art medium constructed of a narrow, pigmented core encased in a wooden cylindrical case.
Source: Wikipedia
```

### 8. Change directories into the charcoal directory. 
The relative path to the charcoal directory is `../charcoal/`
```bash
$ cd ../charcoal/
```

### 9. Copy the file compressed.txt to vine.txt.
```bash
$ ls
compressed.txt  vine.txt
```
```bash
$ cat compressed.txt
Compressed charcoal (also referred as charcoal sticks) is shaped into a block or form of a stick. Intensity of the shade is determined by hardiness. 
Source: Wiki

$ cat vine.txt
Vine charcoal is a long and thin piece of charcoal stick that is the result of burning sticks or vines in a kiln without air. The removable properties of vine charcoal from dusting and erasing is favored by artists for making preliminary sketches or basic composition. 
Source: Wikipedia$
```
Copy compressed.txt to vine.txt overwrites the second file with the first one.
```bash
$ cp compressed.txt vine.txt
```
```bash
$ cat vine.txt
Compressed charcoal ( also referred as charcoal sticks) is shaped into a block or form of a stick. Intensity of the shade is determined by hardiness. 
Source: Wiki
```

### 10. Copy the file vine.txt to color.txt in the pencils directory. 
The relative path of the latter is `../pencils/color.txt`
```bash
$ cp vine.txt ../pencils/color.txt
```

### 11. From the charcoal directory, change directories to the painting directory. 
The relative path is `../../painting/`
```bash
$ cd ../../painting/
```

### 12. Print the working directory.
```bash
$ pwd
/home/ccuser/workspace/artusi/painting
```

### 13. List all contents, in long format, including the hidden files and directories, ordered by the date and time they were last modified.
```bash
$ ls -alt
total 0
drwxr-xr-x 5 ccuser ccuser 54 Jun 14 16:57 ..
drwxr-xr-x 2 ccuser ccuser 69 Jun 14 14:50 brushes
drwxr-xr-x 4 ccuser ccuser 34 Mar  5  2016 .
drwxr-xr-x 4 ccuser ccuser 40 Mar  5  2016 paint
```

### 14. Change directories to the brushes directory.
```bash
$ cd brushes/
```

### 15. List all contents, in long format, including the hidden files and directories, ordered by the date and time they were last modified.
```bash
$ ls -alt
total 16
drwxr-xr-x 2 ccuser ccuser  69 Jun 14 14:50 .
-rw-r--r-- 1 ccuser ccuser  59 Jun 14 14:50 fan.txt
-rw-r--r-- 1 ccuser ccuser 133 Jun 14 14:50 flat.txt
-rw-r--r-- 1 ccuser ccuser 199 Jun 14 14:50 mop.txt
-rw-r--r-- 1 ccuser ccuser  75 Jun 14 14:50 round.txt
drwxr-xr-x 4 ccuser ccuser  34 Mar  5  2016 ..
```

### 16. Copy the files starting with the letter f from the brushes directory to the paint directory. 
The path to the `paint/` directory is `../paint/`

Without changing directories, list the files and directories of the `paint/` directory.
```bash
$ cp f*.txt ../paint/
$ ls ../paint/
acryllic  fan.txt  flat.txt  watercolor
```

### 17. Change directories to the sculpting directory. 
The relative path is `../../sculpting/`
```bash
$ cd ../../sculpting
```

### 18. List all contents, in long format, including the hidden files and directories, ordered by the date and time they were last modified.
```bash
$ ls -alt
total 0
drwxr-xr-x 5 ccuser ccuser 54 Jun 14 16:57 ..
drwxr-xr-x 3 ccuser ccuser 18 Mar  5  2016 .
drwxr-xr-x 5 ccuser ccuser 49 Mar  5  2016 clay
```

### 19. Change directories into the polymer directory, and list all contents of the directory.
```bash
$ cd clay/polymer/
$ ls
airdry.txt
```

### 20. Move airdry.txt into the ceramic directory. 
The relative path to this directory is `../ceramic/`
```bash
$ mv airdry.txt ../ceramic/
```

### 21. Change directories into the ceramic directory.
```bash
$ cd ../ceramic/
$ pwd
/home/ccuser/workspace/artusi/sculpting/clay/ceramic
```

### 22. List all contents, including hidden files and directories.
```bash
$ ls -a
.  ..  airdry.txt  earthenware.txt  stoneware.txt
```

### 23. Remove earthenware.txt from the current directory.
```bash
$ rm earthenware.txt 
$ ls
airdry.txt  stoneware.txt
```

### 24. Change directories one level up back to the clay directory.
```bash
$ cd ..
$ pwd
/home/ccuser/workspace/artusi/sculpting/clay
```

### 25. Delete the dough directory.
```bash
$ ls
ceramic  dough  polymer
$ rm -rf dough
$ ls
ceramic  polymer
```
`rm -r` deletes the directory and all its contents (even directories nested inside). 

`rm -rf` will forcibly delete everything without individually confirming each piece of content inside the directory.

### 26. Change directories two levels up back to the artusi directory. Print the working directory.
```bash
$ cd ../..
$ pwd
/home/ccuser/workspace/artusi
```