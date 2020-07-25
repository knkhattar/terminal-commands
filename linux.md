

# OS Update or Upgrade 
>> Sudo apt-get update  //Just updates the list   
>> Sudo apt-get upgrade  //Actually installs the update   

# System Info

Du //Prints amount of disk usage   


# Ubantu Shortcuts
Lock Screen  : Super + L 

Logout : Ctrl Alt Delete 

Quit Application Ctrl+Q  

Open Terminal : Ctrl + Alt + T 

# Software Installation

* apt for debian packages (specific versions)
* snap for cross distribution pacakges

## Java

sudo apt update 

sudo apt install openjdk-8-jdk 

## Eclipse 

sudo snap install --classic eclipse 

## Maven 

sudo apt update 

sudo apt install openjdk-8-jdk 

 

# User Management 

ssh username@ip/asks for password 

logout or exit //exists shell 

passwd //Change passwd 

who //Lists logged in users 

System Info 

uname ľa //prints system information 

date //prints date 

Dir and File Navigation 

mkdir graphics 

rmdir emptydir Remove directory (must be empty) 

cp file1 web-docs //Copy file into directory 

cp file1 file1.bak //Make backup of file1 

bash xyz.sh //runs the script 

rm *.tmp //Remove all file 

mv old.html new.html Move or rename files 

tar -cf subdir.tar subdir //Create an archive called subdir.tar of a directory 

tar -xvf subdir.tar //Extract files from an archive file 

grep <str><files> //e.g. grep "bad word" * - Find which files contain a certain word 

chmod <opt> <file> 

ps <opt> kill <opt> <ID> 

Software installations, execution 

# MISC 

du 

Prints amount of disk usage 

 

Vi Editor Commands 

 

# Sample File Creation 

Vi MyFirstFile 

I to insert mode 

Type content 

:wq 

 Saving and Closing the file 

Shift+zz - Save the file and quit 

:w - Save the file but keep it open 

:q - Quit without saving 

:wq - Save the file and quit 

# Moving within a file 

k - Move cursor up 

j - Move cursor down 

h - Move cursor left 

l - Move cursor right 

# Log Search 

ls -lh // Display filesize in human readable format (e.g. KB, MB etc.,) 

Tail 

# Prints last few lines in a file 



 

Chmod 

-rwxrwxrwx - OwnerGroupOthers - read write execute 

chmod -R 765 example.txt 

set the permission to be read, write, and execute (7 from our list) for the owner; read and write (6 from our list) for the group; and read and execute (5 from our list) for the others we’d need to use the digits 765 with the chmod command 

 

groups xyz 

which groups a user xyz is a member of. 

Ps -  

lists running processes 

 

Snap commands 

Sudo snap list 

Sudo snap info micok8s 

Microk8s.disable dashboard dns 

Snap version 

Snap remove microk8s --purge 
