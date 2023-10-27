# Bandit
Write-up for the wargame Bandit
To start the game usage of SSH client is necessary. I used an online SSH client https://app.shellngn.com to log into the game.

LEVEL 0:

The username, host and password are already provided on the website of the bandit game.

Username: bandit0

Password: bandit0

LEVEL 0 -> LEVEL 1:

1) After logging onto level 0, it says that there is a file in the directory called ‘readme’. 
2) To list directory contents, ‘ls’ is the required command to find all the files in the directory and ‘readme’ came as the output.
3) for printing content of files, I used the ‘cat’ command which printed the content of the file which was the required password for level 2.
   
Username: bandit1

Password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

![image](https://github.com/Snapskillz123/Bandit/assets/149099858/cdfc419c-0797-43c3-a967-4565b8e4e415)


 LEVEL 1 -> LEVEL 2:

1)	After logging onto level 1, there is a file called ‘-‘ which needs to be read for obtaining the required password.
2)	I used the ‘ls’ command to read all the files in the directory and ‘-‘ came up.
3)	I tried to then print the content of the files using ‘cat –‘ command but no output came.
4)	I had learnt on Google that a ‘<’ operator needs to be used to read dash files.
5)	I used the command ‘cat<-‘ and the desired file content got printed.
   
Username: bandit2

Password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

![image](https://github.com/Snapskillz123/Bandit/assets/149099858/a2d4a0e0-8266-4c76-8768-07bf598a3218)


LEVEL 2 -> LEVEL 3:
1)	After logging into level 2, the file to be read is ‘spaces in this filename’.
2)	I used ‘ls’ command to obtain the file ‘spaces in this filename’.
3)	I then used the ‘cat’ command to read the content of the file ‘spaces in this filename’.
4)	The content printed was the password for the next level.
   
Username: bandit3

Password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/bfab661e-9452-4bfc-9dc2-053950cc266f)


LEVEL 3 -> LEVEL 4:
1)	After logging into level 3, the file to be read is hidden in the directory ‘inhere’.
2)	I used ‘ls’ command to list the directories present and ‘inhere’ came up.
3)	I then used ‘cd’ (command to change working directory) and went into the ‘inhere’ directory.
4)	Then I entered ls -a (lists all files including hidden files) to find the required file and ‘.hidden’ came up.
5)	I then used ‘cat’ to print the contents of the hidden file and the required password came as the output.

Username: bandit4

Password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe


 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/e92b6b99-d2c3-42f6-9cdc-5df46027eede)


LEVEL 4 -> LEVEL 5:
1)	After logging into level 4, there is only one human readable file in the directory ‘inhere’.
2)	I listed the directory ‘inhere’ with ‘ls’.
3)	I then went into the directory ‘inhere’ with ‘cd inhere/’ and listed all the files in the directory.
4)	Since all the files had a name format -file0x, I applied a simple for loop to print the type of data of each file in the directory. With the help of the website https://www.redhat.com/sysadmin/bash-scripting-loops I learnt how to apply the for loop.
5)	Since -file07 was the only file with readable text, I read the contents of the file with ‘cat <-file07’ since it starts with dash.

Username: bandit5

Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/c18ebf97-65b5-4123-bc8d-9d0fd3a3155e)


LEVEL 5 -> LEVEL 6:
1)	¬¬After logging into the next level, I that the password is located in a file in the ‘inhere’ directory with the properties: human readable, 1033 bytes in size, not executable.
2)	I used the ‘ls’ command to list the directories.
3)	I then went into the ‘inhere’ directory using the ‘cd’ command.
4)	Using the manual provided, I learnt the different properties of the ‘find’ command and I noted down the properties I needed to use. ‘-type’ to find the type of file to search, ‘-size’ to find a file of a particular size. ‘-executable’ to check if the file is executable or not.
5)	I used the command ‘find -type f -size 1033c ! -executable’ because we need to search for a regular file, a file of size 1033 bytes (c=1 byte) and file that is not executable.
6)	After running the command it shows a file ‘./maybehere07/.file2’ that fits these criteria.
7)	I then read the contents of the file to find the required password for the next level.

Username: bandit6

Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

 
![image](https://github.com/Snapskillz123/Bandit/assets/149099858/92223b24-e7c8-450e-b848-23acde790476)


LEVEL 6 -> LEVEL 7:

1)	After logging onto the level, I saw that the password is located on the server with the properties: owned by user bandit7, owned by group bandit6 and 33 bytes in size.
2)	Using the manual, I applied the commands ‘-user’, ‘-group’, ‘-size’ for the ‘find’ command. I also used the ‘/’ to obtain the data from the root folder.
3)	I used the command ‘find / -user bandit7 -group bandit6 -size 33c’
4)	I got an unfavourable output, so using the website https://www.cyberciti.biz/faq/bash-find-exclude-all-permission-denied-messages/  I learnt I had to use the command ‘2>/dev/null’ which redirects the error messages so I don’t have to view them.
5)	I then used the command ‘find / -user bandit7 -group bandit6 -size 33c 2>/dev/null’ to fix the problem.
6)	After running the command the file ‘/var/lib/dpkg/info/bandit7.password’ came as the output.
7)	I then printed the contents of the file and obtained the required password.

Username: bandit7

Password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/5a15d0ec-a18b-42ca-8315-d66f68ab2767)


![image](https://github.com/Snapskillz123/Bandit/assets/149099858/94802516-8b08-4693-a55b-8c91aeed5a31)

 




LEVEL 7 -> LEVEL 8:
1)	After logging into the level, I see that the required password is stored in a file ‘data.txt’ next to the word ‘millionth’.
2)	I then ran the command ‘ls’ to list the files available and ‘data.txt’ is seen.
3)	I then run the command ‘cat data.txt | grep millionth’ because grep function is used to print lines that match a certain pattern. ‘|’ operator is used to join to commands together.
4)	The required password then appears next to the word ‘millionth’ in the output.


Username: bandit8

Password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP

 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/203fcc32-c367-493f-97cc-cc1fdcbe676e)


LEVEL 8 -> LEVEL 9:

1)	After logging into the next level. I see that the password lie in the file ‘data.txt’. It is in a line that occurs only once in the file.
2)	I first run ‘ls’ to list the files and ‘data.txt’ shows up.
3)	I then go through the provided manual and find that the ‘uniq’ and ‘sort’ functions could be useful. Sort function lists the lines of a file in an orderly fashion and by default it puts the file in alphabetical order. Uniq function deletes lines that are duplicated. I had to use sort and uniq because uniq deletes duplicate lines only if they are next to each other and sort puts similar lines next to each other.
4)	I then run the command ‘sort data.txt | uniq -u’.
5)	-u is to print only unique lines.
6)	The required password then shows up after running the command.

 	Username: bandit9

	Password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t

![image](https://github.com/Snapskillz123/Bandit/assets/149099858/293d8524-fdcf-4f16-9cf1-a83605f584cc)
	 

LEVEL 9 -> LEVEL 10:

1)	After logging into the level, I see that the file is in ‘data.txt’, along with a few human readable strings, preceded by ‘=’ characters.
2)	I then run the command ‘ls’ to list the files and data.txt comes up.
3)	I since the password is a string and is around multiple other strings, I realise that the ‘strings’ function is required and to read the file ‘cat’ function is also required. The ‘grep’ function is required as well to find strings matching the pattern ‘=’.
4)	I then ran the command ‘cat data.txt | strings | grep ‘=’. The output I got was strings with ‘=’ in the middle of the string as well which were not needed.
5)	To find strings with ‘=’ at the start of the string, from the website: https://www.linuxquestions.org/questions/linux-newbie-8/what-does-symbol-%5E-do-in-bash-831914/
I learnt that ‘^’ character can be used like a ‘startsWith’ function.
6)	So I ran the command ‘cat data.txt | strings | grep ^= and I got a few strings pointing to the password.

Username: bandit10

Password: G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/674296fd-66c0-40c6-8797-926897630bd5)

LEVEL 10 -> LEVEL 11:

1)	I log on to the next level, and I see that the password is stored on ‘data.txt’ and the password is in base64 encoded data.
2)	I then run the ‘ls’ command to list the files present and ‘data.txt’ pops up.
3)	From the manual, I learned that the ‘base64’ command can be used to decode base64 text. 
4)	I then run the command ‘cat data.txt | base64 -d’.
5)	-d is the base64 command format for decoding.
6)	I then get the required password after decoding the base64 text.

Username: bandit11

Password: 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

 
![image](https://github.com/Snapskillz123/Bandit/assets/149099858/ae40dfde-0e7b-4197-a97e-010daabe9b10)


LEVEL 11 -> LEVEL 12:

1)	After logging into the level, I see that the next password is stored in the file ‘data.txt’ and the alphabets of the string has been rotated by 13 positions.
2)	I then ran the command ‘ls’ to list the available files and ‘data.txt’ pops up.
3)	I then ran ‘cat data.txt’ to read the content of the file and some gibberish appears which is in rot13 form.
4)	I converted the rot 13 into a regular string using the website https://rot13.com and got the required password.

Username: bandit12

Password: JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

 ![image](https://github.com/Snapskillz123/Bandit/assets/149099858/59eea7e1-dadd-4fc1-9951-08b9254193eb)

 

LEVEL 12 -> LEVEL 13:

1)  After logging into the level, I see that data.txt file has hexdump content that has been repeatedly been compressed and the password is in it.
2)  i run the command 'mkdir /tmp/cpy' to create a directory and then I used 'cp data.txt /tmp/cpy' to copy the file into my new directory.
3)  I then use 'cd /tmp/cpy' to go into my directory and then run 'ls' to check if the file is in my directory.
4)  i then use the command 'xxd -r data.txt > pswrd' to do a reverse hexdump and save the result in a file named 'pswrd'. xxd is used to create a hexdump or to decode a hexdump.
5)  I then used the 'file' command to check the type of file that 'pswrd' was.
6)  I then ran 'mv pswrd pswrd.gz' to change the filename into the preferred file extentions as it is a gzip compressed data.
7)  I then run 'gunzip' command on the file to decompress it. gunzip is used to decompress gzip files.
8)  Repeat step 5 to 7 with the respective file name. For repetition of 6), use the correct decompression command for the type of file that is there. for tar archive, use it with xvf which basically extracts, verboses and puts the data into a new file.
9)  once we get an ascii text file, print the contents of the file using 'cat'.

Username: bandit13

Password: wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw

![image](https://github.com/Snapskillz123/Bandit/assets/149099858/3bc2d339-31a6-422d-a713-d199c6a6d4ca)

![image](https://github.com/Snapskillz123/Bandit/assets/149099858/d7586d51-cd36-466f-a13c-4c9ae86d124e)

I used a few sites for reference for this question:

https://github.com/s4shaNull/OverTheWire-Bandit-Writeup

https://askubuntu.com/questions/1159845/what-is-tar-xvf

Level 13 -> 14

1) I log on to the next level and see that the password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. The required data is a private SSH key that is to be used to log on to the next level.
2) I run the command 'ls' to list the files available and 'sshkey.private' comes up.
3) I then realised I needed to log in to the file, so I used the 'ssh' command along with '-i' to select a file from which the identity for public key authentication is read. 'bandit14@localhost' is also required because we are logging on as bandit14 and as 'localhost' because I am logging in from my laptop.
4) The required SSH key comes up.
 
6) 






