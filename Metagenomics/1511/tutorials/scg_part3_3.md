---
layout: default
title:  Part 3: Single cell genome assembly using SPAdes
---

# Part 3: Single cell genome assembly

## 3.1a. Assemble your data Using SPAdes

Make a folder for SPAdes assemblies: 

```sh
mkdir spades_assemblies
#cd spades_assemblies
```

You have to run SPAdes with 3 different flags and report the assembly time in the spreadsheet:
* with ```--sc``` only
* with ```--careful``` only
* with both ```--sc --careful```

To run SPAdes with --sc and --careful flags (our default assembly setting), type:  

* if you work with the **raw** reads  
>```sh
>time spades.py --sc --careful -t 8 -m 24 \
>-1 G5_${sample}_R1_001.fastq \
>-2 G5_${sample}_R2_001.fastq \
>-o spades_assemblies/G5_${sample}_sc_careful
>```

* if you work with the **merged** reads  
>```sh
>time spades.py --sc --careful -t 8 -m 24  \
>-1 merged_reads/G5_${sample}_merge_1.fastq.gz \
>-2 merged_reads/G5_${sample}_merge_2.fastq.gz \
>-s G5_${sample}_merged.fastq.gz \
>-o spades_assemblies/G5_${sample}_SeqPrep_sc_careful
>```

>You are now providing 3 input files to the assembler; 2 unmerged read pairs and 1 merged reads. After this assembly is done, 

Repeat the assemblies again but omitting *'--sc'* or *'--careful'* flags as in the previous exercises. 
Name the next two assemblies as *G5_Hiseq_SeqPrep_careful* and *G5_Hiseq_SeqPrep_sc*.

*Notice: Those previous commands will launch SPAdes assembly but also check how long the assembly takes. After the assembly has completed, check the time it took for the program to run. You should look at the 'real' time. 
Record the time in the spreadsheet table.
In general, typing the command ```time``` before other commands will help you check how long the computation took.*

**Using '--sc' flag**  
SPAdes can handle single-cell genomic data that is known to be highly biased in terms of sequence coverage along the length of the genome. 
In order for SPAdes to be able to handle biased sequence coverage, you need to supply the *'--sc'* flag when running the assembly.


**Using '--careful' flag**  
This flag uses *'bowtie'* tool to map the reads back to the contigs and check for errors due to bad quality sequences and correct these errors. 
This results in longer assembly times than not using the *'--careful'* flag.

## 3.1a. Assemble your data Using IDBA-UD

>```sh
fq2fa --merge G5_Hiseq_trimmed_1P.fq G5_Hiseq_trimmed_2P.fq G5_Hiseq_idba.fa
fq2fa --merge ../raw/G5_Hiseq_R1_001.fq ../raw/G5_Hiseq_R2_001.fq ../raw/G5_Hiseq_idba.fa

time idba_ud -r raw/G5_Hiseq_idba.fa -o raw/idba_test --maxk 124 
time idba_ud -r trimmed/G5_Hiseq_idba.fa -o trimmed/idba_test --maxk 124
>``

## 3.1a. Assemble your data Using Ray

>```sh
time mpirun -n 8 Ray -k 31 -p raw/G5_Hiseq_R1_001.fq raw/G5_Hiseq_R2_001.fq -o raw/ray_k31 &> raw/ray.log & 
time mpirun -n 8 Ray -k 31 -p trimmed/G5_Hiseq_trimmed_1P.fq trimmed/G5_Hiseq_trimmed_2P.fq -o trimmed/ray_k31 &> trimmed/ray.log & 

>``