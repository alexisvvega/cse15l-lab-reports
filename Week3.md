# Lab Report 3

The command I have chosen is "find". The find command is used when searching for files and directories in a specified location as well as its subdirectories.

1. The first command is "-type"

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

f stands for the regular files, and is also the default behavior when no -type option is specified. Using "-type f" will search for all the regular files and display them.

Overall the "-find" command is useful when trying to find specific files or directories. By specifying the type of file you are looking for you can easily filter your searches and make it easier to locate the files you are interested in. 

Link to [source](https://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/)

2. The next command is "-name"

~~~
$ find ./technical -name <search of choice> 
~~~

a use of this command can look like this:
~~~
$ find ./technical -name "biomed"
~~~

which will produce this: 

~~~
./technical/biomed
~~~
The name command will search for the files and directories in a specific location with a specific name. It takes in a file in this case ./technical and returns a list of all files or directories in the specified location that match the specified name.
You can also use this command with " * " which allows for a wider use of searching. 

For example using 
~~~
$  find ./technical/biomed -name "*research*"
~~~

will find all the files within the path ./technical/biomed that contain the word research. This will produce the following output:

~~~
./technical/biomed/gb-2001-2-4-research0010.txt
./technical/biomed/gb-2001-2-4-research0011.txt
./technical/biomed/gb-2002-3-9-research0043.txt
./technical/biomed/gb-2001-2-7-research0025.txt
./technical/biomed/gb-2002-3-7-research0032.txt
./technical/biomed/gb-2001-2-4-research0012.txt
./technical/biomed/gb-2001-2-7-research0024.txt
./technical/biomed/gb-2001-2-3-research0008.txt
./technical/biomed/gb-2002-3-9-research0046.txt
./technical/biomed/gb-2002-3-7-research0037.txt
./technical/biomed/gb-2001-2-8-research0027.txt
./technical/biomed/gb-2001-2-11-research0046.txt
./technical/biomed/gb-2001-2-8-research0032.txt
./technical/biomed/gb-2002-3-7-research0036.txt
./technical/biomed/gb-2002-3-9-research0051.txt
./technical/biomed/gb-2002-3-9-research0045.txt
./technical/biomed/gb-2001-2-8-research0030.txt
./technical/biomed/gb-2001-2-4-research0014.txt
./technical/biomed/gb-2001-2-11-research0045.txt
./technical/biomed/gb-2002-3-7-research0035.txt
./technical/biomed/gb-2001-2-8-research0031.txt
./technical/biomed/gb-2002-3-9-research0044.txt
./technical/biomed/gb-2002-3-2-research0008.txt
./technical/biomed/gb-2002-3-11-research0059.txt
./technical/biomed/gb-2002-3-11-research0065.txt
./technical/biomed/gb-2001-2-10-research0041.txt
./technical/biomed/gb-2002-3-8-research0040.txt
./technical/biomed/gb-2001-2-9-research0035.txt
./technical/biomed/gb-2002-3-12-research0085.txt
./technical/biomed/gb-2002-3-2-research0009.txt
./technical/biomed/gb-2002-3-12-research0087.txt
./technical/biomed/gb-2002-3-12-research0078.txt
./technical/biomed/gb-2001-2-6-research0018.txt
./technical/biomed/gb-2001-2-9-research0037.txt
./technical/biomed/gb-2001-2-10-research0042.txt
./technical/biomed/gb-2002-3-12-research0079.txt
./technical/biomed/gb-2002-3-12-research0086.txt
./technical/biomed/gb-2002-3-12-research0082.txt
./technical/biomed/gb-2001-2-6-research0021.txt
./technical/biomed/gb-2001-2-6-research0020.txt
./technical/biomed/gb-2002-3-12-research0083.txt
./technical/biomed/gb-2002-3-11-research0062.txt
./technical/biomed/gb-2002-3-11-research0060.txt
./technical/biomed/gb-2002-3-12-research0081.txt
./technical/biomed/gb-2002-3-12-research0080.txt
./technical/biomed/gb-2002-3-11-research0061.txt
./technical/biomed/gb-2002-3-12-research0072.txt
./technical/biomed/gb-2002-3-12-research0071.txt
./technical/biomed/gb-2000-1-1-research002.txt
./technical/biomed/gb-2001-3-1-research0005.txt
./technical/biomed/gb-2002-3-5-research0024.txt
./technical/biomed/gb-2002-3-5-research0025.txt
./technical/biomed/gb-2001-3-1-research0004.txt
./technical/biomed/gb-2001-2-2-research0004.txt
./technical/biomed/gb-2002-3-5-research0021.txt
./technical/biomed/gb-2002-3-5-research0020.txt
./technical/biomed/gb-2001-3-1-research0001.txt
./technical/biomed/gb-2002-3-12-research0075.txt
./technical/biomed/gb-2002-3-12-research0088.txt
./technical/biomed/gb-2002-3-12-research0077.txt
./technical/biomed/gb-2002-3-5-research0022.txt
./technical/biomed/gb-2002-3-5-research0023.txt
./technical/biomed/gb-2002-3-6-research0029.txt
./technical/biomed/gb-2002-3-9-research0049.txt
./technical/biomed/gb-2002-3-9-research0048.txt
./technical/biomed/gb-2002-3-10-research0052.txt
./technical/biomed/gb-2001-2-12-research0055.txt
./technical/biomed/gb-2002-3-4-research0019.txt
./technical/biomed/gb-2002-3-4-research0018.txt
./technical/biomed/gb-2001-2-12-research0054.txt
./technical/biomed/gb-2002-3-10-research0053.txt
./technical/biomed/gb-2002-3-3-research0012.txt
./technical/biomed/gb-2000-1-2-research0003.txt
./technical/biomed/gb-2002-3-8-research0039.txt
./technical/biomed/gb-2001-2-12-research0051.txt
./technical/biomed/gb-2002-3-8-research0038.txt
./technical/biomed/gb-2002-3-10-research0056.txt
./technical/biomed/gb-2002-3-3-research0011.txt
./technical/biomed/gb-2002-3-10-research0054.txt
./technical/biomed/gb-2001-2-12-research0053.txt
./technical/biomed/gb-2001-2-3-research0007.txt
./technical/biomed/gb-2002-3-10-research0055.txt
~~~
another use of the name command can look like this:
~~~
$ find ./technical  -iname "*ar*"
~~~

which will produce this: 
~~~
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
./technical/government/About_LSC/Protocol_Regarding_Access.txt
./technical/government/Env_Prot_Agen/section-by-section_summary.txt
./technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
./technical/government/Gen_Account_Office/GovernmentAuditingStandards_yb2002ed.txt
./technical/government/Post_Rate_Comm/Cohenetal_comparison.txt
./technical/government/Media/Good_guys_reward.txt
./technical/government/Media/Targeting_Domestic_Violence.txt
./technical/government/Media/Barnes_new_job.txt
./technical/government/Media/Law_Award_from_College.txt
./technical/government/Media/Raising_the_Bar.txt
./technical/government/Media/Barnes_pro_bono.txt
./technical/government/Media/Paralegal_Honored.txt
./technical/government/Media/FortWorthStarTelegram.txt
./technical/government/Media/Lockyer_Warns.txt
./technical/government/Media/Barnes_Volunteers.txt
./technical/government/Media/Marylands_Legal_Aid.txt
./technical/government/Media/Library_Lawyers.txt
./technical/government/Media/Hard_to_Get.txt
./technical/government/Media/Barr_sharpening_ax.txt
./technical/government/Media/Farm_workers.txt
./technical/biomed/gb-2001-2-4-research0010.txt
./technical/biomed/ar331.txt
./technical/biomed/ar319.txt
./technical/biomed/gb-2001-2-4-research0011.txt
./technical/biomed/ar79.txt
./technical/biomed/gb-2002-3-9-research0043.txt
./technical/biomed/gb-2001-2-7-research0025.txt
./technical/biomed/ar130.txt
./technical/biomed/ar118.txt
./technical/biomed/gb-2002-3-7-research0032.txt
./technical/biomed/gb-2001-2-4-research0012.txt
./technical/biomed/gb-2001-2-7-research0024.txt
./technical/biomed/gb-2001-2-3-research0008.txt
./technical/biomed/ar93.txt
./technical/biomed/ar68.txt
./technical/biomed/gb-2002-3-9-research0046.txt
./technical/biomed/gb-2002-3-7-research0037.txt
./technical/biomed/gb-2001-2-8-research0027.txt
./technical/biomed/gb-2001-2-11-research0046.txt
./technical/biomed/ar120.txt
./technical/biomed/gb-2001-2-8-research0032.txt
./technical/biomed/gb-2002-3-7-research0036.txt
./technical/biomed/ar297.txt
./technical/biomed/gb-2002-3-9-research0051.txt
./technical/biomed/gb-2002-3-9-research0045.txt
./technical/biomed/gb-2001-2-8-research0030.txt
./technical/biomed/ar321.txt
./technical/biomed/ar309.txt
./technical/biomed/gb-2001-2-4-research0014.txt
./technical/biomed/gb-2001-2-11-research0045.txt
./technical/biomed/gb-2002-3-7-research0035.txt
./technical/biomed/gb-2001-2-8-research0031.txt
./technical/biomed/gb-2002-3-9-research0044.txt
./technical/biomed/gb-2002-3-2-research0008.txt
./technical/biomed/gb-2002-3-11-research0059.txt
./technical/biomed/gb-2002-3-11-research0065.txt
./technical/biomed/ar795.txt
./technical/biomed/ar408.txt
./technical/biomed/ar409.txt
./technical/biomed/gb-2001-2-10-research0041.txt
./technical/biomed/gb-2002-3-8-research0040.txt
./technical/biomed/gb-2001-2-9-research0035.txt
./technical/biomed/gb-2002-3-12-research0085.txt
./technical/biomed/gb-2002-3-2-research0009.txt
./technical/biomed/gb-2002-3-6-software0001.txt
./technical/biomed/gb-2002-3-12-research0087.txt
./technical/biomed/gb-2002-3-12-research0078.txt
./technical/biomed/gb-2001-2-6-research0018.txt
./technical/biomed/gb-2001-2-9-research0037.txt
./technical/biomed/ar422.txt
./technical/biomed/gb-2001-2-10-research0042.txt
./technical/biomed/ar387.txt
./technical/biomed/gb-2002-3-12-research0079.txt
./technical/biomed/gb-2002-3-12-research0086.txt
./technical/biomed/gb-2002-3-12-research0082.txt
./technical/biomed/ar778.txt
./technical/biomed/ar750.txt
./technical/biomed/gb-2001-2-6-research0021.txt
./technical/biomed/ar624.txt
./technical/biomed/ar383.txt
./technical/biomed/ar619.txt
./technical/biomed/gb-2001-2-6-research0020.txt
./technical/biomed/ar745.txt
./technical/biomed/ar792.txt
./technical/biomed/gb-2002-3-12-research0083.txt
./technical/biomed/gb-2002-3-11-research0062.txt
./technical/biomed/gb-2002-3-11-research0060.txt
./technical/biomed/gb-2002-3-12-research0081.txt
./technical/biomed/ar430.txt
./technical/biomed/ar140.txt
./technical/biomed/gb-2002-3-12-research0080.txt
./technical/biomed/gb-2002-3-11-research0061.txt
./technical/biomed/gb-2002-3-12-research0072.txt
./technical/biomed/ar429.txt
./technical/biomed/ar774.txt
./technical/biomed/gb-2002-3-12-research0071.txt
./technical/biomed/gb-2000-1-1-research002.txt
./technical/biomed/gb-2001-3-1-research0005.txt
./technical/biomed/gb-2002-3-5-research0024.txt
./technical/biomed/gb-2002-3-5-research0025.txt
./technical/biomed/gb-2001-3-1-research0004.txt
./technical/biomed/ar615.txt
./technical/biomed/ar601.txt
./technical/biomed/gb-2001-2-2-research0004.txt
./technical/biomed/gb-2002-3-5-research0021.txt
./technical/biomed/ar407.txt
./technical/biomed/gb-2002-3-5-research0020.txt
./technical/biomed/gb-2001-3-1-research0001.txt
./technical/biomed/gb-2002-3-12-research0075.txt
./technical/biomed/ar799.txt
./technical/biomed/gb-2002-3-12-research0088.txt
./technical/biomed/gb-2002-3-12-research0077.txt
./technical/biomed/ar612.txt
./technical/biomed/gb-2002-3-5-research0022.txt
./technical/biomed/gb-2002-3-5-research0023.txt
./technical/biomed/ar149.txt
./technical/biomed/gb-2002-3-6-research0029.txt
./technical/biomed/gb-2002-3-9-research0049.txt
./technical/biomed/gb-2002-3-9-research0048.txt
./technical/biomed/gb-2002-3-10-research0052.txt
./technical/biomed/gb-2001-2-12-research0055.txt
./technical/biomed/gb-2002-3-4-research0019.txt
./technical/biomed/gb-2002-3-4-research0018.txt
./technical/biomed/gb-2001-2-12-research0054.txt
./technical/biomed/ar104.txt
./technical/biomed/gb-2002-3-10-research0053.txt
./technical/biomed/gb-2002-3-3-research0012.txt
./technical/biomed/gb-2000-1-2-research0003.txt
./technical/biomed/gb-2002-3-8-research0039.txt
./technical/biomed/gb-2001-2-12-research0051.txt
./technical/biomed/gb-2002-3-8-research0038.txt
./technical/biomed/gb-2002-3-10-research0056.txt
./technical/biomed/gb-2002-3-3-research0011.txt
./technical/biomed/gb-2002-3-10-research0054.txt
./technical/biomed/gb-2001-2-12-research0053.txt
./technical/biomed/ar328.txt
./technical/biomed/gb-2001-2-3-research0007.txt
./technical/biomed/gb-2002-3-10-research0055.txt
~~~

the iname command is similar to the name command where it will search for the files and directories in a specific location with a specific name however unlike name itself, iname is case sensitive and will find all files with "ar" in it, upper and lowercase. 

Overall the name and iname command are very useful when working with large files and wanting to quickly search for specific files with certain characteristics.

Link to [source](https://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/)

3. Another command is -maxdepth 
~~~
$ find ./technical maxdepth 3
~~~

