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

another use of -type command is:
~~~
$ find ./technical -type f
~~~
this will print out the following:
~~~
./technical/plos/journal.pbio.0020306.txt
./technical/plos/journal.pbio.0030129.txt
./technical/plos/journal.pbio.0020307.txt
./technical/plos/pmed.0020180.txt
./technical/plos/pmed.0020194.txt
./technical/plos/pmed.0020157.txt
./technical/plos/journal.pbio.0020105.txt
./technical/plos/pmed.0020023.txt
./technical/plos/journal.pbio.0020071.txt
./technical/plos/pmed.0020235.txt
.
.
.
./technical/biomed/bcr567.txt
./technical/biomed/gb-2002-3-10-research0055.txt
./technical/biomed/1471-2121-2-3.txt
./technical/biomed/1471-213X-1-11.txt
./technical/biomed/1472-684X-1-5.txt
./technical/biomed/1476-4598-1-6.txt
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
~~~

(There are more files but to save space these are a few that will be printed.)

