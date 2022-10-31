# Week 5 Lab Report: Using the Grep Command in 3 Different Ways
For this lab report, I will be using the `grep` command with 3 different variations. Assume all commands are within the `./technical` directory.

## -r
```
grep -r "oxi" 
.
.
.
911report/chapter-11.txt:                proxies to try to capture or kill Bin Ladin and his lieutenants. As early as
911report/chapter-11.txt:                longer have been dependent on proxies to gather actionable intelligence. 
.
.
.
biomed/1471-2091-2-11.txt:        are not toxic to McNtcp.24 cells [ 18 ] . In contrast,
biomed/1471-2091-2-11.txt:        toxic bile acids were still able to induce apoptosis,
biomed/1471-2091-2-11.txt:        acid cytotoxicity, we conferred active bile acid uptake
.
.
.
government/Env_Prot_Agen/atx1-6.txt:reduction evaluations and toxicity identification evaluations to
government/Env_Prot_Agen/atx1-6.txt:identify the toxic components of an effluent, to aid in the
government/Env_Prot_Agen/atx1-6.txt:development and implementation of toxicity reduction plans, and to
government/Env_Prot_Agen/atx1-6.txt:short-term chronic toxicity test methods manuals for freshwater and
.
.
.
plos/journal.pbio.0030102.txt:        provide an excellent habitat for anaerobic hydrocarbon oxidizers. For example, Cordes et
plos/journal.pbio.0030102.txt:        association of sulfide oxidizers, sulfate reducers, and a host worm is known to be
plos/journal.pbio.0030102.txt:        that certain populations of anaerobic methane oxidizers are specifically associated with
plos/journal.pbio.0030102.txt:        Calyptogena and the giant filamentous sulfide oxidizer
```
When you do not specify the directory, the `-r` command will recursively look through the current directory and all sub-directories for the substring you want to search for.
```
grep -r "oxi" biomed/*
.
.
.
biomed/rr74.txt:        Although we attempted to keep the mice continuously
biomed/rr74.txt:        account for the slight increase in plasma NO metabolites
biomed/rr74.txt:        seen in the hypoxic animals, which is consistent with the
biomed/rr74.txt:        et al. [ 42]. Because the systemic
biomed/rr74.txt:        metabolite levels, if NOS was downregulated in the systemic
biomed/rr74.txt:        et al. [ 38], then the lack of
biomed/rr74.txt:        activity in the systemic circulation. However, those
biomed/rr74.txt:        pattern of NOS expression in vascular beds other than the
biomed/rr74.txt:        upregulation in the murine lung with severe hypoxia-induced
biomed/rr74.txt:        warrants further study.
biomed/rr74.txt:        eNOS = endothelial nitric oxide synthase; iNOS =
```
Once you specify a directory, the computer recursively searches for files within the directory and any sub-directories it has for the search term. It's useful if you want to perform a general search of all files within a directory without having to go to each subdirectory every time.

```
grep -r "oxi" government
.
.
.
government/Post_Rate_Comm/Cohenetal_Cost_Function.txt:U.S. they account for approximately six percent. Poste Italiane
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:By "physical terrain" we mean the physical proximity of the
government/Post_Rate_Comm/Cohenetal_CreamSkimming.txt:no higher than approximately 7 cents per piece in order to compete
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:per address that encompass approximately 90 percent of the routes
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:approximately twice that of the most costly areas. Thus, the volume
government/Post_Rate_Comm/Cohenetal_DeliveryCost.txt:22 Approximately 30 percent of rural routes serve non-rural
```
You do not need to use the `/` to specify a path either, as long as you know the directory you are trying to search, using the `-r` variant of `grep` will allow you to search for a substring within a directory and its sub-directories. The substring you are looking for will be highlighted as well, allowing you to see where it was found more easily.
## -n
The `-n` variant of the `grep` command allows you to find the specific line where the search term is found in each file.
```
grep -n "oxide" biomed/*
.
.
.
biomed/rr167.txt:285:          was dissolved in 100% dimethyl sulfoxide (DMSO), which
biomed/rr167.txt:713:        dimethyl sulfoxide; EC
biomed/rr172.txt:75:          the collected smoke particulates in dimethyl sulfoxide
biomed/rr172.txt:97:          carbon dioxide and 95% air at 37°C. Primary cultures of
biomed/rr191.txt:89:          inhibitors (dimethyl sulphoxide) or with media that
biomed/rr191.txt:120:          reconstituted in dimethyl sulphoxide as 1 mM, 50 mM, 50
biomed/rr74.txt:146:          Hematocrit and nitric oxide metabolite
biomed/rr74.txt:223:          Nitric oxide metabolites
biomed/rr74.txt:418:        eNOS = endothelial nitric oxide synthase; iNOS =
biomed/rr74.txt:419:        inducible nitric oxide synthase; nNOS = neuronal nitric
biomed/rr74.txt:420:        oxide synthase; NO = nitric oxide; NOS = nitric oxide
```
You can quickly find the exact line where the substring was found in each file. To do this, you need to specify the directory you are searching in so that you are not stuck in the terminal for a long time. 
```
grep -n "oxi" government/*
grep: government/About_LSC: Is a directory
grep: government/Alcohol_Problems: Is a directory
grep: government/Env_Prot_Agen: Is a directory
grep: government/Gen_Account_Office: Is a directory
grep: government/Media: Is a directory
grep: government/Post_Rate_Comm: Is a directory
```
You also need to use this command in a directory where there are files since this command cannot search through the current directory and sub-directories recursively.
```
grep -n "oxi" government/About_LSC/*
government/About_LSC/Comments_on_semiannual.txt:335:during the March ABA/NLADA Equal Justice Conference. Approximately
government/About_LSC/Special_report_to_congress.txt:215:deemed questionable approximately 34 percent of both open and
government/About_LSC/Special_report_to_congress.txt:346:approximately $10.5 million in federal funds under the Violence
government/About_LSC/Special_report_to_congress.txt:349:will receive approximately $11.5 million in VAWA funding.
government/About_LSC/Special_report_to_congress.txt:430:from their submission to LSC approximately 17,000 of the
government/About_LSC/Special_report_to_congress.txt:614:approximately 80 percent of poor Americans do not have the
government/About_LSC/State_Planning_Report.txt:1431:approximately 2,500 volunteer lawyers. It conducts numerous CLE
government/About_LSC/State_Planning_Report.txt:1761:primary sources: the state, IOLTA and LSC. Approximately two
government/About_LSC/Strategic_report.txt:474:reports showed that users had viewed approximately 15,500 pages.
government/About_LSC/Strategic_report.txt:835:One of the best ways to help the approximately 80 percent of
government/About_LSC/commission_report.txt:596:34,898 job openings and approximately 4,000 employers. The FY 1998
government/About_LSC/commission_report.txt:600:openings were certified and approximately 2,300 employers. April
government/About_LSC/diversity_priorities.txt:15:On May 31 and June 1, 2001, approximately fifty equal justice
```
Here is where the `-n` command works when you specify the directory, a sub-directory, and a file path. It will be useful to find the specific line where a file contains the substring so that you can access the file and jump to that line right away.
## -c
The `-c` variant of the `grep` command counts how many times the specified search term pops up in every file, even if it does not show up at all.
```
grep -c "oxide" biomed/*
.
.
.
biomed/gb-2003-4-7-r42.txt:0
biomed/gb-2003-4-7-r43.txt:0
biomed/gb-2003-4-7-r46.txt:0
biomed/gb-2003-4-8-r50.txt:0
biomed/gb-2003-4-8-r51.txt:0
biomed/gb-2003-4-9-r57.txt:0
biomed/gb-2003-4-9-r58.txt:0
biomed/gb-2003-4-9-r60.txt:0
biomed/rr166.txt:0
biomed/rr167.txt:2
biomed/rr171.txt:0
biomed/rr172.txt:2
biomed/rr191.txt:2
biomed/rr196.txt:0
biomed/rr37.txt:0
biomed/rr73.txt:0
biomed/rr74.txt:5
```
Like the `-n` variant, you need to specify the directory, any potential sub-directories, and the file path so that the terminal is not stuck for a long time. You can use this as an anti-plagiarism tool to see whether an existing idea was taken and used in some kind of report.
```
grep -c "nitric oxide" biomed/*
biomed/1468-6708-3-1.txt:0
biomed/1468-6708-3-10.txt:0
biomed/1468-6708-3-3.txt:0
biomed/1468-6708-3-4.txt:0
biomed/1468-6708-3-7.txt:0
biomed/1471-2091-2-10.txt:0
biomed/1471-2091-2-11.txt:0
biomed/1471-2091-2-12.txt:0
biomed/1471-2091-2-13.txt:0
biomed/1471-2091-2-16.txt:0
biomed/1471-2091-2-5.txt:1
.
.
.
```
The `-c` variant will still show files that do not contain the substring at all. It can be useful to know what files don't have the search term so that you can avoid looking through those files, but at the same time it will be annoying to sift through them when you have hundreds of files that do not contain the substring.
```
grep -c "oxi" plos/*
.
.
.
plos/journal.pbio.0020348.txt:18
plos/journal.pbio.0020350.txt:1
plos/journal.pbio.0020353.txt:1
plos/journal.pbio.0020354.txt:1
plos/journal.pbio.0020394.txt:0
plos/journal.pbio.0020400.txt:64
plos/journal.pbio.0020401.txt:20
.
.
.
```
Searching in the `plos` directory, there is a file that has a lot of instances of the substring, so the `-c` variant is helpful for trying to find files that uses the search term many times.
