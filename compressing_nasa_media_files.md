# Compressing NASA’s Media Files 
For your college Astronomy class, you and your team are planning to discuss the history of NASA’s space missions. To make your presentation stand out, you had the amazing idea to interview Neil, a family friend who works at NASA. Neil happily agrees and offers to send you an unreleased collection of photos, videos, and audio to use on your school project.

Neil has consolidated this media into a zip archive file and hosted it on an internal NASA server. He said there’s a 95.98% chance that you will be able to download it without any problems, and it can only be downloaded once. You are responsible for sharing them with your teammates. He warns you that these files are raw and unedited, so they should be compressed before sending them to your peers.

To complete this project, you will be:
- Using a network command to check the status of the server that hosts the zip file
- Downloading and extracting a zip file
- Organizing files based on their type
- Compressing files using gzip, bzip2, and xz
- Archiving files using tar

## Project Setup
Before we get started, make sure you are in your Linux environment, whether you are in a VirtualBox or access Linux natively. Open up the Terminal app.

We need to install a utility called iftop to your command line, which allows us to monitor our network. 
```
sudo apt -y install iftop
```
We will use iftop to observe the download progress and ensure we are correctly able to download the zip archive. 

## Project Instructions
### Downloading the Files and Monitoring Network
Open two terminal windows and stack them side by side. Open the first terminal window and use the command below to open a second terminal.
```
gnome-terminal
```

In one of the terminal windows run the following command and leave the window open until you finish downloading the archive file in the other terminal window.
```
sudo iftop
```

In the other terminal, change the terminal working directory to Desktop.
```
$ cd /home/anne/Desktop
```

Check whether the server that hosts the media.zip file is reachable since Neil warned you that it might not be. Send 5 packets to `static-assets.codecademy.com` using the `ping` command with the `-c` count option.
```
$ ping -c 5 static-assets.codecademy.com
PING static-assets.codecademy.com (104.17.183.120) 56(84) bytes of data.
64 bytes from 104.17.183.120 (104.17.183.120): icmp_seq=1 ttl=255 time=110 ms
64 bytes from 104.17.183.120 (104.17.183.120): icmp_seq=2 ttl=255 time=12.5 ms
64 bytes from 104.17.183.120 (104.17.183.120): icmp_seq=3 ttl=255 time=13.7 ms
64 bytes from 104.17.183.120 (104.17.183.120): icmp_seq=4 ttl=255 time=44.4 ms
64 bytes from 104.17.183.120 (104.17.183.120): icmp_seq=5 ttl=255 time=16.7 ms


--- static-assets.codecademy.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4023ms
rtt min/avg/max/mdev = 12.454/39.420/109.877/37.136 ms
```
You will notice network traffic with bandwidth usage being printed out in the terminal window running the iftop command.

Use the `wget` or `curl` command to download media.zip from the url `https://static-assets.codecademy.com/Courses/learn-linux/nasa-media-off-platform-project/media.zip`. Use option `-0` to save the downloaded file with the original file name.

```
$ curl -O "https://static-assets.codecademy.com/Courses/learn-linux/nasa-media-off-platform-project/media.zip"
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current

                                 Dload  Upload   Total   Spent    Left  Speed

100  107M  100  107M    0     0  3738k      0  0:00:29  0:00:29 --:--:-- 1048k
```
While the file is downloading, iftop will show the source address of the file and the bandwidth usage. You may close the iftop terminal when the file is downloaded.

Extract the downloaded archive file to the current Desktop.
```
$ unzip media.zip
Archive:  media.zip
   creating: media/
  inflating: media/Apollo 8 Separation.jpg  
  inflating: media/Apollo 9 Launch.jpg  
  inflating: media/credits.txt       
  inflating: media/Mariner IV.mp4    
  inflating: media/Pathfinder.jpg    
  inflating: media/Ranger 9 Impacts Moon.mp4  
  inflating: media/Saturn Apollo Program Illustration.jpg  
  inflating: media/Saturn Apollo Program.jpg  
  inflating: media/Space Shuttle Highlights.mp4  
  inflating: media/Tsunami Waves Recorded by Voyager 1.mp3  
  inflating: media/Voyager 2 Launches.mp4  
  inflating: media/Voyager in Deep Space.jpg  
```

View the files.
```
$ ls
media  media.zip
```

## Organizing and Compressing Files for Distribution
In this section, we encourage you to use commands like ls to check the progress of the tasks in between instructions. You can also always refer to the man or info pages for any of the commands if you need a reminder on how to place options and arguments for the compression/archiving commands!

### 1. Change directory
Change the terminal working directory to media. View the files in the extracted media directory and take note of the files and their extensions.
```
$ cd media
$ ls
'Apollo 8 Separation.jpg'    'Saturn Apollo Program Illustration.jpg'
'Apollo 9 Launch.jpg'        'Saturn Apollo Program.jpg'
 credits.txt                 'Space Shuttle Highlights.mp4'
'Mariner IV.mp4'             'Tsunami Waves Recorded by Voyager 1.mp3'
 Pathfinder.jpg              'Voyager 2 Launches.mp4'
'Ranger 9 Impacts Moon.mp4'  'Voyager in Deep Space.jpg'
```

### 2. Create new directory and move files
Create a directory called compressed_photos and move all the photos (files with the .jpg extension) to this directory.
```
$ mkdir compressed_photos
$ mv *.jpg compressed_photos/
```

### 3. Compress files
Compress all the files in the compressed_photos directory using the gzip compression command. Option `-r` means recursive.
```
$ gzip -r compressed_photos/
ls compressed_photos/
'Apollo 8 Separation.jpg.gz'  'Saturn Apollo Program Illustration.jpg.gz'
'Apollo 9 Launch.jpg.gz'      'Saturn Apollo Program.jpg.gz'
 Pathfinder.jpg.gz            'Voyager in Deep Space.jpg.gz'
```

### 4. Create compressed tar archive
Let's take a look at our directory.
```
$ ls
 compressed_photos           'Space Shuttle Highlights.mp4'
 credits.txt                 'Tsunami Waves Recorded by Voyager 1.mp3'
'Mariner IV.mp4'             'Voyager 2 Launches.mp4'
'Ranger 9 Impacts Moon.mp4'
```

Create a compressed tar archive named videos.tar.bz2 of all the videos (files with .mp4 extension). Be patient. This might take a while. 
```
$ tar -cjf videos.tar.bz2 *.mp4 --remove-files
```
The option `-c` creates a new archive, `-j` filters the archive through bzip2 compression, `-f` writes output to the file `videos.tar.bz2` and `--remove-files` removes the original files.

Now let's see the result.
```
$ ls
compressed_photos  'Tsunami Waves Recorded by Voyager 1.mp3'
credits.txt         videos.tar.bz2
```

### 5. Compress the audio file
Compress the audio file with the .mp3 extension using the xz compression utility.
```
$ xz *.mp3
$ ls
 compressed_photos  'Tsunami Waves Recorded by Voyager 1.mp3.xz'
 credits.txt         videos.tar.bz2
```

# Conclusion
Terminal commands were used to download files from an online host, several compression tools were used to reduce the size of files, and media files were sorted into directories.