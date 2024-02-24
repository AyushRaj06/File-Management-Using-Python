Automate your Desktop File Management and declutter your Downloads Folder. This app will automatically organise & mve your downloads into folders based on file tyep.
![image](https://github.com/AyushRaj06/File-Management-Using-Python/assets/113136467/73b69505-02b2-4eb4-8361-b977f9f11a4e)


To run this in your Linux terminal whenever a download is detected, do the following steps:


Step 1: Installing `inotify-tools` (for monitoring Downloads folder changes)
  
//Run the following code in your terminal
  
sudo apt-get update
sudo apt-get install inotify-tools


Step 2: Create a shell script that runs when a download is detected

//Bash file (monitor_downloads.sh)

#!/bin/bash

while true
do
    inotifywait -r -e modify,create,delete /path/to/your/Downloads/folder && python3 /path/to/your/script.py
done


Step 3: Make the script executable

//Run the following code in your terminal

chmod +x monitor_downloads.sh


Step 4: Run the script

./monitor_downloads.sh
