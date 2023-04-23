# Lab Report 1

To begin logging in to your course-specified account on ieng6 you will need to begin by installing Visual Studio Code. 
You can use this link [here](https://code.visualstudio.com/) and follow the instructions to download it to your operting system.

Once you have downloaded VScode, you should be able to open a window that looks like this:

![Image](Installing.png)

To begin connecting you have to open a New Terminal. Within this terminal you will input the following: $ ssh cs15lsp23zz@ieng6.ucsd.edu , substituting the zz with the letters specified in your course specific account (you do not need to include the $ when typing it into your terminal).

![Image](LoggingIn.png)

Doing the following should produce a message asking you if you want to continue, accept it. 

~~~
ssh cs15lsp23zz@ieng6@ucsd.edu
The authenticty of host 'ieng6.ucsd.edu (128.ucsd.edu)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
~~~


Accepting by typing yes as well as following the next instruction of entering your password should result in your terminal producing something like this: 

![Image](Connecting.png)

The terminal is now connected to a computer in the CSE basement!

Now that the terminal is connected you are able to run some commands! Running the commands should produce something like this:

![Image](Trying.png)

The ls command shows you what is inside the directory, the pwd command prints out the working directory and the cat command concatenates the text from the file. 

![Image](test2.png)
![Image](MoreTests.png)

For example here I used ls to see what was inside my directory and called cat hello.txt to see what was in the file. There are many other ls commands too such as the command 'ls-f' which lists all entries in the directory in order. The -l option uses a long format similar to 'ls -la' and adds a long listing format with information on its size, last time modified as well as other stuff associated with the file or directory.

The different commands you try will produce different outcomes. So try a bunch and see what happens!

