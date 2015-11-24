---
layout: default
title:  'Part 6: Analysis of a novel single cell'
---

# Part 6: Analysis of a novel single cell genome
---

Now that you have worked with several single cell genome datasets, you will be able to play around with the analysis you did before for a mystery single cell (dataset3). 
With the knowledge that you have acquired during this course, you can try to:

- make a decent assembly
- assess the completeness of your single cell
- try to identify your cell using rnammer or MEGAN
- try to asses if the dataset suffers from contamination
- find out any interesting features that might be encoded by the genome

In this exercise, you will work with MiSeq data produced from a different Single-cell Amplified Genome (SAG) than G5 in the first part of the tutorial. You can do the assemblies in the same way as the examples shown in Part 3. There is no need to optimize the steps, instead think about what is your first choice of assembler, settings and preprocessing with the experience you have now.

An overview of the steps are listed below:

0. Think about the file/folder structure and naming convention
1. Preprocessing
2. Optimize the assembly (tool, kmers, flags)
3. Run *'Quast'* and *'micomplete'* tools for assembly stats
4. Run Prodigal to predict ORFs
5. Run RNAmmer to predict rRNAs
6. Run Blastn and Blastp of the genes
7. Blast the rRNA genes against Silva database
8. Organize the results


We suggest that you start with question 1 and think of the steps necessary to obtain the answer. 

If you have more time you can play around with the other optional questions and decide where you want to focus. There are also a couple of optional exercises you can try for the different steps you went through. Choose the part you are most interested in.

### Questions
---

**Q7.1** What is the taxonomic affiliation of the SAG?  

Optional exercises

Biologically oriented questions:

**Q7.2** Can you say anything about the metabolism based on the assembled data?  

Bioinformatically oriented questions:

**Q7.3** Did you notice any major differences between the assemblies using different assembler, setting or input data (trimmed/untrimmed reads)? To make this question more specific you can look into the optional exercises below where some assembly optimization options are suggested.  
**Q7.4** Do you think the number of reads are enough to obtain a good assembly or should more sequences be obtained?  

## Optional exercises

Here is a list of optional exercises collected in one place, from the various parts of the tutorial that you went through.

Preprocessing - merging reads

Ray assembly optimization:

Spades assembly optimization:

In this bonus exercise, a different parameter will be introduced, i.e., k-mers. SPAdes in default mode runs with **k-mers of 21, 33, and 55**. 
In this exercise, you will set the **k-mers to 55, 77, and 99**. To set these k-mers, you need to provide this parameter when running SPAdes:

```
-k 55,77,99
```





