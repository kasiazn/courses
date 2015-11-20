---
layout: default
title:  Part 3: Single cell genome assembly using SPAdes
---

# Part 3: Single cell genome assembly

## 3.2. Pre-processing

Before assembly you can do several pre-processing steps. Here we will focus on quality trimming of the reads with Trimmomatic. Another step you can do if your library setup results in overlapping reads it merging. An example of how to do that is described [here](scg_part3_merging). Considering that all of the assemblers we use can take in paired reads, and some of them (Spades) actually do not recommend using the qualities that the merging result in, consider this an extra part you can have a look at in case it might be interesting for you.

**Trimming reads with Trimmomatic** 

Trimmomatic is a sliding window quality trimming

(check the command)

```sh
java -jar $TRIMMOMATIC_HOME/trimmomatic.jar PE -phred33 \
-basein raw/G5_Hiseq_R1_001.fq -baseout trimmed/G5_Hiseq_trimmed.fq \
ILLUMINACLIP:$TRIMMOMATIC_HOME/adapters/NexteraPE-PE.fa:2:30:10 \
LEADING:3 TRAILING:3 SLIDINGWINDOW:4:15 MINLEN:36
```