# Lab Report 3

The command I have chosen is "find". The find command is used when searching for files and directories in a specified location as well as its subdirectories.

1)The first command is "-type"

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

another use of this can look as such:

~~~
$ find ./technical/government -type d
~~~
which will produce: 
~~~
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/government/Media
~~~


Overall the "-find d" command is useful when trying to find specific directories. By specifying the type of file you are looking for you can easily filter your searches and make it easier to locate the files you are interested in. 

another use of -type command is "-type f":
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

Overall the "-find" commands are useful when trying to find specific files or directories. By specifying the type of file you are looking for you can easily filter your searches and make it easier to locate the files you are interested in. 

Link to [source](https://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/)

2)Another useful command is -maxdepth

this command can be written as: 
~~~
$ find <path> -maxdepth <number>
~~~
this commands purpose is to limit the depth of your search.

a use of it can be seen here:
~~~
$ find ./technical/government -maxdepth 2 -iname "*do*"
~~~
this will produce the following: 
~~~
./technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
./technical/government/Media/Donald_Hilliker.txt
./technical/government/Media/Targeting_Domestic_Violence.txt
./technical/government/Media/Domestic_Violence_Ruling.txt
./technical/government/Media/Domestic_violence_aid.txt
./technical/government/Media/fight_domestic_abuse.txt
./technical/government/Media/Do-it-yourself_divorce.txt
~~~
here I specified my path to be ./technical/government and wanted the maxdepth to be 2. Specifying the max depth to be 2 will limit the search to a depth of two directories following your specified path. Adding -iname "*do*" will also narrow your search to find all directories of maxdepth 2 with the word "do" in them.

another use of this command can be seen here where instead of finding the max depth we are finding the minimum depth: 
~~~
$ find ./technical/government -mindepth 1 -iname "*c*"
~~~
this is very similar to maxdepth and can be useful if you want to exclude files or directories that are located too close to the root directory or if you want to focus on files or directories that are nested deeper in the directory tree.

this will produce the following: 
~~~
./technical/government/About_LSC
./technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
./technical/government/About_LSC/Strategic_report.txt
./technical/government/About_LSC/Comments_on_semiannual.txt
./technical/government/About_LSC/Special_report_to_congress.txt
./technical/government/About_LSC/CONFIG_STANDARDS.txt
./technical/government/About_LSC/commission_report.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
./technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
./technical/government/About_LSC/Protocol_Regarding_Access.txt
./technical/government/About_LSC/ODonnell_et_al_v_LSCdecision.txt
./technical/government/About_LSC/conference_highlights.txt
./technical/government/About_LSC/State_Planning_Special_Report.txt
./technical/government/Env_Prot_Agen/section-by-section_summary.txt
./technical/government/Env_Prot_Agen/ctf7-10.txt
./technical/government/Env_Prot_Agen/ctf1-6.txt
./technical/government/Env_Prot_Agen/ro_clear_skies_book.txt
./technical/government/Env_Prot_Agen/ctm4-10.txt
./technical/government/Env_Prot_Agen/tech_sectiong.txt
./technical/government/Env_Prot_Agen/tech_adden.txt
./technical/government/Alcohol_Problems
./technical/government/Alcohol_Problems/DraftRecom-PDF.txt
./technical/government/Gen_Account_Office
./technical/government/Gen_Account_Office/Testimony_cg00010t.txt
./technical/government/Gen_Account_Office/Oct15-1999_gg00026t.txt
./technical/government/Gen_Account_Office/Oct15-2001_d0224.txt
./technical/government/Gen_Account_Office/InternalControl_ai00021p.txt
./technical/government/Gen_Account_Office/Paper_Walker11-2002_acpro122.txt
./technical/government/Post_Rate_Comm
./technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt
./technical/government/Post_Rate_Comm/Mitchell_spyros-first-class.txt
./technical/government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt
./technical/government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt
./technical/government/Post_Rate_Comm/Mitchell_RMVancouver.txt
./technical/government/Post_Rate_Comm/Gleiman_gca2000.txt
./technical/government/Post_Rate_Comm/Cohenetal_Cost_Function.txt
./technical/government/Post_Rate_Comm/Redacted_Study.txt
./technical/government/Post_Rate_Comm/Mitchell_6-17-Mit.txt
./technical/government/Post_Rate_Comm/Cohenetal_comparison.txt
./technical/government/Post_Rate_Comm/Cohenetal_Scale.txt
./technical/government/Post_Rate_Comm/Cohenetal_RuralDelivery.txt
./technical/government/Post_Rate_Comm/ReportToCongress2002WEB.txt
./technical/government/Post_Rate_Comm/WolakSpeech_usps.txt
./technical/government/Media/Federal_agency.txt
./technical/government/Media/balance_scales_of_justice.txt
./technical/government/Media/Legal-aid_chief.txt
./technical/government/Media/Funding_cuts_force.txt
./technical/government/Media/Free_legal_service.txt
./technical/government/Media/Owning_a_Piece.txt
./technical/government/Media/Targeting_Domestic_Violence.txt
./technical/government/Media/City_Council_Budget.txt
./technical/government/Media/Supporting_Legal_Center.txt
./technical/government/Media/Lindsays_legacy.txt
./technical/government/Media/New_funding_sources.txt
./technical/government/Media/Legal_Aid_in_Clay_County.txt
./technical/government/Media/Domestic_Violence_Ruling.txt
./technical/government/Media/Law_Award_from_College.txt
./technical/government/Media/Law_Schools.txt
./technical/government/Media/Justice_for_all.txt
./technical/government/Media/agency_expands.txt
./technical/government/Media/not_accessible_to_disabled.txt
./technical/government/Media/Campaign_Pays.txt
./technical/government/Media/New_Online_Resources.txt
./technical/government/Media/Poor_Lacking_Legal_Aid.txt
./technical/government/Media/Workers_aid_center.txt
./technical/government/Media/Too_Crucial_to_Take_Cut.txt
./technical/government/Media/Pro_Bono_Services.txt
./technical/government/Media/AP_LawSchoolDebts.txt
./technical/government/Media/Eviction_law.txt
./technical/government/Media/Law-school_grads.txt
./technical/government/Media/Disaster_center.txt
./technical/government/Media/Kiosks_for_court_forms.txt
./technical/government/Media/Fire_Victims_Sue.txt
./technical/government/Media/Terrorist_Attack.txt
./technical/government/Media/Butler_Co_attorneys.txt
./technical/government/Media/BergenCountyRecord.txt
./technical/government/Media/Court_Keeps_Judge_From.txt
./technical/government/Media/Coup_Reshapes_Legal_Aid.txt
./technical/government/Media/Avoids_Budget_Cut.txt
./technical/government/Media/grants_fail_to_come.txt
./technical/government/Media/Lockyer_Warns.txt
./technical/government/Media/Using_Tech_Tools.txt
./technical/government/Media/Boone_legal_service.txt
./technical/government/Media/Making_a_case.txt
./technical/government/Media/Commercial_Appeal.txt
./technical/government/Media/Justice_requests.txt
./technical/government/Media/Free_Legal_Assistance.txt
./technical/government/Media/Local_Attorneys.txt
./technical/government/Media/Texas_Supreme_Court.txt
./technical/government/Media/Civil_Matters.txt
./technical/government/Media/Low-income_children.txt
./technical/government/Media/The_Columbian.txt
./technical/government/Media/Higher_court.txt
./technical/government/Media/Service_Agency.txt
./technical/government/Media/Crains_New_York_Business.txt
./technical/government/Media/residents_sue_city.txt
./technical/government/Media/Legal_Aid_Society.txt
./technical/government/Media/Major_Changes.txt
./technical/government/Media/All_May_Have_Justice.txt
./technical/government/Media/Domestic_violence_aid.txt
./technical/government/Media/Advocate_for_Poor.txt
./technical/government/Media/fight_domestic_abuse.txt
./technical/government/Media/CommercialAppealMemphis2.txt
./technical/government/Media/Weak_economy.txt
./technical/government/Media/Valley_Needing_Legal_Services.txt
./technical/government/Media/Legal_services_for_poor.txt
./technical/government/Media/Do-it-yourself_divorce.txt
./technical/government/Media/Politician_Practices.txt
./technical/government/Media/NJ_Legal_Services.txt
./technical/government/Media/Legal_Aid_campaign.txt
~~~
Similiar to maxdepth, mindepth is still limiting the depth of your search but rather narrowing it to all the directories with a minimum number of directories based on the number you provide.

Overall the purpose of maxdepth and mindepth followed by a number, is to limit the depth of the search to that number of levels of subdirectories. This is useful for narrowing your search to find specific files of your interest. 


Link to [source](https://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/)

3)Another command is "-name"

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
Another example of using the name command is:
~~~
$ find ./technical/911report -name "*13*"
~~~
which will produce:
~~~
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
~~~
Overall the name is very useful when working with large files and wanting to quickly search for specific files with certain characteristics.

Link to [source](https://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/)

4)Another similar command to name is "-iname" which can look like this:
~~~
$ find ./technical  -iname "*ar*"
~~~

this will produce the following: 
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


Another use of iname can be seen here:
~~~
find ./technical/government -iname "a*"
~~~
in here I am going into another path and finding all files that contain an a.

this will produce:

~~~
./technical/government/About_LSC
./technical/government/Env_Prot_Agen/atx1-6.txt
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office/ai00134.txt
./technical/government/Gen_Account_Office/ai9868.txt
./technical/government/Gen_Account_Office/ai2132.txt
./technical/government/Media/Anthem_Payout.txt
./technical/government/Media/Abuse_penalties.txt
./technical/government/Media/agency_expands.txt
./technical/government/Media/Annual_Fee.txt
./technical/government/Media/AP_LawSchoolDebts.txt
./technical/government/Media/Avoids_Budget_Cut.txt
./technical/government/Media/Assuring_Underprivileged.txt
./technical/government/Media/Attorney_gives_his_time.txt
./technical/government/Media/All_May_Have_Justice.txt
./technical/government/Media/Advocate_for_Poor.txt
./technical/government/Media/A_Perk_of_Age.txt
./technical/government/Media/A_helping_hand.txt
./technical/government/Media/Aid_Gets_7_Million.txt
~~~

Overall the name and iname command are very useful and similar when working with large files and wanting to quickly search for specific files with certain characteristics. iname is more beneficial when wanting to not be case sensitive.

Link to [source](https://www.thegeekstuff.com/2009/03/15-practical-linux-find-command-examples/)



