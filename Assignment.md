#                  Linux Assignment
## Q1.Create a directory named "MyFiles" in your home directory. Navigate into this directory and list its contents.

```bash 

cd home

 sudo mkdir MyFiles

 cd MyFiles

 ls -l

```
**Output**

shrikant@shrikant:/home$ sudo mkdir MyFiles

shrikant@shrikant:/home$ cd MyFiles

shrikant@shrikant:/home/MyFiles$ ls -l

total0


shrikant@shrikant:/home/MyFiles$ 

![Alt text](<assets/Screenshot from 2024-02-01 23-10-21.png>)

## Q2.	Copy a file named "document.txt" from your home directory to the "MyFiles" directory. Move the file to a subdirectory named "Documents" within "MyFiles."
```bash

```
Output:

![Alt text](<Screenshot from 2024-02-02 11-39-12.png>)

## Q3.	Create an empty file named "notes.txt" in the "MyFiles" directory. Afterward, delete the file.
```bash
touch 
```
Output:shrikant@shrikant:/home/MyFiles$ touch notes.txt

shrikant@shrikant:/home/MyFiles$ ls -lrth
total 12K

-rw-rw-r-- 1 shrikant shrikant  408 Feb  3 13:02 my_notes.txt

-rw-rw-r-- 1 shrikant shrikant    0 Feb  3 13:31 notes.txt

shrikant@shrikant:/home/MyFiles$ rm notes.txt

shrikant@shrikant:/home/MyFiles$ ls -lrth
total 12K

-rw-rw-r-- 1 shrikant shrikant  554 Feb  3 12:55 conf_files.txt
-rw-rw-r-- 1 shrikant shrikant  408 Feb  3 13:02 my_notes.txt
shrikant@shrikant:/home/MyFiles$ 


![Alt text](image-6.png)

## Q4.	Create a hard link named "hardlink.txt" for the file "document.txt" within the "Documents" subdirectory. Also, create a symbolic link named "symlink.txt" in the same location.
```bash
```
Output:
![Alt text](<Screenshot from 2024-02-02 12-14-45.png>)
## Q5.	In the "MyFiles" directory, use a single command to list all files that start with the letter "a" and have a ".txt" extension.
```bash
```
OutPut:
![Alt text](<Screenshot from 2024-02-02 19-19-20-1.png>)

## Q6.	Rename all files in the "Documents" subdirectory of "MyFiles" with a ".bak" extension. Ensure the original file names are preserved.
```bash
cd /home/MyFiles
```
```bash
sudo vim rename.sh
```
```bash
#!/bin/bash

rename_extension=".bak"

for file in *; do
    if [ -f "$file" ]; then
        rename_file="$file$rename_extension"
        cp "$file" "$rename_file"
        echo "Renamed File $file as $rename_file"
    fi
done
```
```bash 
cd Documents

```
```bash
touch aa.txt ab.txt abc.txt
```
```bash
sudo bash ../rename.sh
```
Output:
shrikant@shrikant:/home/MyFiles/Documents$ sudo touch aa.txt ab.txt abc.txt 

shrikant@shrikant:/home/MyFiles/Documents$ sudo bash ../rename.sh


Renamed File aa.txt as aa.txt.bak

Renamed File aa.txt.bak as aa.txt.bak.bak

Renamed File abc.txt as abc.txt.bak

Renamed File abc.txt.bak as abc.txt.bak.bak

shrikant@shrikant:/home/MyFiles/Documents$ 

![Alt text](image-7.png)

## Q7.	Use a wildcard character to copy all files from the "Documents" subdirectory of "MyFiles" to another directory named "Backup."
```bash
cd /home/MyFiles 
```
```bash
sudo mkdir backup
cd
```
```bash
sudo cp /home/MyFiles/Document/* /home/MyFiles/backup/
```
Output:
shrikant@shrikant:/$ cd /home/MyFiles

shrikant@shrikant:/home/MyFiles$ sudo mkdir backup

shrikant@shrikant:/home/MyFiles$ cd

shrikant@shrikant:~$ sudo cp /home/MyFiles/Documents/* /home/MyFiles/backup

shrikant@shrikant:~$ cd /home/MyFiles/backup/

shrikant@shrikant:/home/MyFiles/backup$ ls

aa.txt		abc.txt.bak.bak  document.txt.bak      Symlink.txt

aa.txt.bak	ab.txt		 document.txt.bak.bak  Symlink.txt.bak

aa.txt.bak.bak	ab.txt.bak	 hardlink.txt	       Symlink.txt.bak.bak

abc.txt		ab.txt.bak.bak	 hardlink.txt.bak

abc.txt.bak	document.txt	 hardlink.txt.bak.bak

shrikant@shrikant:/home/MyFiles/backup$ cd

shrikant@shrikant:~$ cd /home/MyFiles/Documents/

shrikant@shrikant:/home/MyFiles/Documents$ ls

aa.txt		abc.txt.bak.bak  document.txt.bak      Symlink.txt

aa.txt.bak	ab.txt		 document.txt.bak.bak  Symlink.txt.bak

aa.txt.bak.bak	ab.txt.bak	 hardlink.txt	       Symlink.txt.bak.bak

abc.txt		ab.txt.bak.bak	 hardlink.txt.bak

abc.txt.bak	document.txt	 hardlink.txt.bak.bak

shrikant@shrikant:/home/MyFiles/Documents$ 

![Alt text](image-8.png)

## Q8.	Execute the ls command to list files in the current directory. Save the output to a file named "file_list.txt." Then, use a pipe to filter the output through grep to display only files with a ".txt" extension.
```bash
sudo su
```
```bash
cd /home/MyFiles/
```
```bash
touch file_list.txt
```
```bash
cd Document
```
```bash
chmod +rwx a.txt b
```
```bash 
cd..
```
```bash
chmod +rwx file_list.txt
```
```bash
cd Document
```
```bash
grep '\.txt$' file_list.txt

```
Output:
shrikant@shrikant:~$ sudo su

root@shrikant:/home/shrikant# cd /home/MyFiles

root@shrikant:/home/MyFiles# touch file_list.txt

root@shrikant:/home/MyFiles# cd Documents

root@shrikant:/home/MyFiles/Documents# chmod +rwx aa.txt

root@shrikant:/home/MyFiles/Documents# cd ..

root@shrikant:/home/MyFiles# chmod +rwx file_list.txt

root@shrikant:/home/MyFiles# cd Documents

root@shrikant:/home/MyFiles/Documents# grep '\.txt$' file_list.txt

grep: file_list.txt: No such file or directory

root@shrikant:/home/MyFiles/Documents# grep '\.txt$' file_list.txt

grep: file_list.txt: No such file or directory
root@shrikant:/home/MyFiles/Documents# cd ..

root@shrikant:/home/MyFiles# ls

aa.txt   a.txt   conf_files.txt  file_list.txt  raaz.txt   shreshth.txt

abc.txt  backup  Documents       my_notes.txt   rename.sh

![Alt text](image-9.png)

## Q9.	Create a new text file named "my_notes.txt" using the touch command. Open the file in the Vim editor, add some text, and save the changes.
```bash
```
outut:
![Alt text](<Screenshot from 2024-02-02 19-19-20.png>)
## Q10.	Run the date command and store the output in a variable named "current_date." Display the value of the variable and append it to the "my_notes.txt" file.
```
```
OutPut:

shrikant@shrikant:~$ current_date=$(date)

shrikant@shrikant:~$ echo "Current Date:$current_date"

Current Date:Saturday 03 February 2024 10:14:32 AM IST

shrikant@shrikant:~$ echo "$current_date">>my.notes.txt

shrikant@shrikant:~$ 

![Alt text](image-2.png)


## Q11.	Edit the Bash startup script (e.g., .bashrc) to set an environment variable named "CUSTOM_PATH" to a specific directory path. Ensure the variable is available in new shell sessions.
```bash 
nano ~/.bashrc

source ~/.bashrc

```
OutPut:
shrikant@shrikant:~$ nano ~/.bashrc

shrikant@shrikant:~$ source ~/.bashrc

shrikant@shrikant:~$ 

![Alt text](image-3.png)


## Q12.	Use the echo command to add a new line of text to the "my_notes.txt" file without overwriting existing content. Verify that the new text is appended.
```bash
echo "This is a new line of text." >> my_notes.txt

cat my_notes.txt

```
OutPut:

shrikant@shrikant:~$ echo "This is a new line of text." >> my_notes.txt

shrikant@shrikant:~$ cat my_notes.txt

Hello Sir

Have a nice Day!

This is a new line of text.

shrikant@shrikant:~$ 

![Alt text](image-4.png)


## Q13.	List all files in the "/etc" directory, filter the output to include only those containing the word "conf," and save the result to a file named "conf_files.txt."
```bash
ls /etc | grep 'conf' > conf_files.txt

vim conf_files.txt

```
Output:
adduser.conf
apg.conf
appstream.conf
avrdude.conf
brltty.conf
ca-certificates.conf
ca-certificates.conf.dpkg-old
dconf
debconf.conf
deluser.conf
e2scrub.conf
fprintd.conf
fuse.conf
gai.conf
hdparm.conf
host.conf
insserv.conf.d
kernel-img.conf
kerneloops.conf
ld.so.conf
ld.so.conf.d
libao.conf
![Alt text](image-5.png)


## Q14.	Open the "my_notes.txt" file in Vim. Use Vim's search and replace functionality to replace all occurrences of the word "important" with "critical." Save the changes.
```bash
cd /home/MyFiles

sudo vim my_notes.txt

%s/important/critical/g
```

## Q15.	Create a new user account named "john_doe." Set the user's home directory to "/home/john_doe" and assign the user to the "users" group.
```bash
sudo useradd -m -d /home/john_doe -g users john_doe
```

## Q16.	Add the user "john_doe" to the sudoers file, allowing them superuser privileges. Confirm that "john_doe" can execute commands with sudo.
```bash
sudo visudo
```


Inside visudo file write below content and save it and exit.

```bash
john_doe ALL=(ALL:ALL) ALL
```
Write any desire path
```bash
sudo ls /Desktop
sudo su
```
OutPut:

## Q17.	Modify the user account "john_doe" to change the default shell to "/bin/bash" and set the account's expiration date to one month from today.
```bash
sudo chsh -s /bin/bash john_doe
sudo chage -E $(date -d "+1 month" +"%Y-%m-%d") john_doe
```
outPut:
## Q18.	Create a new group named "development_team." Add "john_doe" to this group and verify the group's existence.
```bash
sudo groupadd development_team
sudo usermod -aG development_team john_doe
getent group development_team
```
## Q19.	Remove "john_doe" from the "users" group and add them to the "development_team" group. Confirm the changes.
```bash
sudo gpasswd -d john_doe users
sudo usermod -aG development_team john_doe
groups john_doe

```
## Q20.	Delete the user account "john_doe" and ensure that their home directory is also removed.
```bash
sudo userdel -r john_doe
groups jhon_doe

```
## Q21.	Delete the group "development_team" and ensure that all users previously belonging to the group are appropriately handled.
```bash 
getent group development_team
sudo usermod -g users jhon_doe
sudo groupdel development_team
getent group development_team
```
## Q22.	Implement a password policy that requires users to change their passwords every 90 days. Apply this policy to all existing and new user accounts.
```bash
sudo chage -M 90 -m 0 -W 7 -I 30 -E -1 $(cut -d: -f1 /etc/passwd)
sudo vim /etc/login.defs
```
Inside this file add max pass day as 90 and min pass day as 0
```bash
PASS_MAX_DAYS   90
PASS_MIN_DAYS   0
```
## Q23.	Manually lock the user account "john_doe." Attempt to log in as "john_doe" to confirm that the account is locked. Then, unlock the account.
```bash
sudo passwd -l john_doe
su - john_doe
sudo passwd -u john_doe
```
## Q24.	Use the id command to display detailed information about the "john_doe" user, including user ID, group ID, and supplementary groups.
```bash
id john_doe
```
```bash
id -u john_doe
id -g john_doe
```
```bash
id -G john_doe
```
## Q25.	Configure the password aging for the user "john_doe" to enforce a maximum password age of 60 days. Confirm that the changes take effect.
```bash
sudo chage -M 60 john_doe
```
```bash
sudo chage -l john_doe
```

output

                                                          
