# Lab Report 3

The command I have chosen is "find". The find command is used when searching for files and directories in a specified location as well as its subdirectories.

1.The first command is "-type"

~~~
$ find ./technical -type <specifier> 
~~~
a use of this command can look like this:

~~~
$ find ./technical -type d
~~~
this will print out the following:
~~~
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
./technical/plos
./technical/biomed
./technical/911report
~~~
d stands for directories, so "-type d" searches for all the directories in the home directory.

