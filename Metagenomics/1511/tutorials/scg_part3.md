---
layout: default
title:  Part 3: Single cell genome assembly using SPAdes
---

# Part 3: Single cell genome assembly

<p>
In this part of the course, you will start doing assemblies of 'real' (but reduced) single cell genome datasets. We will compare two single cell specific assemblers, namely Spades and IDBA-UD, and one 'general-purpose' assembler called Ray (which were introduced by Kasia). The idea is that you will be able to compare the results of these different assemblers on two kinds of datasets (HiSeq and MiSeq), as well as different pre-treatments ('trimming'). You will also have a chance to explore how to decide which assembly is the best ('assembly metrics'), as there is no simple asnwer to this question.
Out of the total 12 assemblies we like you to compare, we suggest one person does only 3 on one of the datasets and pre-treatments. This way you can focus and skip handling too many folders and files. Assembly is also relatively time-consuming (although we have prepared reduced datasets for the tutorial to keep the times reasonable). So if you work as a group of 4 you can collect the results in one summary table we will look at. You will find a list of these tables below.
</p>

<!--- 
If you can complete these 12 assemblies and have time remaining, you can do Part 7 as a bonus exercise. 
Note that Part 6 is for running assemblies using MiSeq data. 
Note that you will have to fill in the results from the exercises in Tables 1 to 4 
--->

Actual tables to be filled in are provided in Google Docs and the links can be found below. 
You should talk to each other to form the groups and split the work. Do not worry if you miss something, we will collect result from all groups and discuss it together.  

[Group 1:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdGRKMXJwdF9jVDMzX2lGMkdJSDdOcnc&usp=sharing)  
[Group 2:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdC0tdzFySDFyaDNIdEh4M01xMXFQb3c&usp=sharing)  
[Group 3:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdHhwdUdUWUxBbnd0eC15WkJhS29iV3c&usp=sharing)  
[Group 4:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdFZRcXBjN0lrMGV5NmNuRnUzV2RkT0E&usp=sharing)  
[Group 5:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdEhkV3hIejJaMDZrWDFqd29XNTZFbmc&usp=sharing)  
[Group 6:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdFZDQzhLamJocHI0M0ZBQ0dMUDRrSFE&usp=sharing)  
[Group 7:](https://docs.google.com/spreadsheet/ccc?key=0AuNHyFPCsxthdDU2OUk4ank4c1A1VVhhbjZPaldtN2c&usp=sharing)  
[Group 8:](https://docs.google.com/spreadsheets/d/1Q3QBvPYzQ1kFHjWu0O5Jf1wgSH-9sxMrcndoLlNW92Y/edit?usp=sharing)  















<!---
Next, make symbolic links of sequences in that folder:

```sh
ln -s /proj/g2015028/nobackup/single_cell_exercises/sequences/dataset1/G5_Hiseq_R1_001.fastq .
ln -s /proj/g2015028/nobackup/single_cell_exercises/sequences/dataset1/G5_Hiseq_R2_001.fastq .
ln -s /proj/g2015028/nobackup/single_cell_exercises/sequences/dataset2/G5_Miseq_R1_001.fastq .
ln -s /proj/g2015028/nobackup/single_cell_exercises/sequences/dataset2/G5_Miseq_R2_001.fastq .
```

Now you are almost ready to run assemblies! But before you can start assemblies, you need to load SPAdes module first.  
To load the SPAdes assembler, type:

```sh
module load bioinfo-tools
module load spades/3.1.1
```  
--->  


<!--- 
Notes for next year's workshop
- Uppmax support at the beginning of the workshop (troubleshooting, node reservation, technical support - cables etc) => not enough ethernet socket
- Having MEGAN and Artemis installed locally instead of on Milou (15-30min for sorting out computer problems/ software installation, unless we have dedicated computers/terminals). 
Students are to pre-install the tools on their computers if they will use their own laptops.
- table of contents
- useful Linux commands such as:
pwd to check current working directory
tab completion
arrow up for previous command
- define learning objectives
- include pre-course materials about fasta/q formats, basic unix commands (count number of reads in fasta or fastq files as checks).
- Longer introductory lecture on basics such as NGS data
- flowchart of steps involved in generating single cell genome data to help visualize how we got the data (overview of what part they are involved in)
- check points (completeness estimates - distribution of marker genes, chimera generation, MEGAN summary, Artemis)
- extra day for binning (together with metagenomic workshop)
- guest lectures (national/international) prior to hands-on workshops
--->
