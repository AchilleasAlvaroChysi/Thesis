# Malware Detection based on Behavioral Graphs

## B.Sc. thesis 

Author: Alvaro Chysi 

Supervisor: Stavros D. Nikolopoulos

In this Thesis we developed an algorithm to detect unknown samples as malware or benign and classifying them into know malware families.

### Files Explanation

Each file is a jupyter notebook and each notebook includes a full circle of experiments testing for different aspects. More specifically.

* [Malware Detection](https://github.com/AchilleasAlvaroChysi/Thesis/blob/master/Malware%20Detection.ipynb) is the __main__ notebook where the
experiments concerning max flows are conducted. 

* [Metrics on Grg](https://github.com/AchilleasAlvaroChysi/Thesis/blob/master/Metrics%20on%20Grg.ipynb) is the notebook where we test the 
dataset on the similarity metrics we use in Malware detection.

* [Networkx Trial](https://github.com/AchilleasAlvaroChysi/Thesis/blob/master/Networkx%20Trial.ipynb) a notebook were we apply networkx 
on our dataset graphs.

* [Page Rank and Other](https://github.com/AchilleasAlvaroChysi/Thesis/blob/master/PGRnk%20and%20other.ipynb) is a notebook were we applied
network similarity methods on our behavioral graphs.

### Our Dataset 

The dataset contains approximately 2600 samples, categorized and separated in 48 malware families and 35 benign families.
Based on the work of [I.Polenakis and S.D.Nikolopoulos] (https://link.springer.com/content/pdf/10.1007%2Fs11416-016-0267-1.pdf) our graphs 
are represented as a 30 by 30 graph, with each node labeled as a group of system calls. 

The graphs vary in size (\# of edges) even within the same family.

Every family is given 2 names separated by ',' (comma). E.g. `Banker,Bankos`. 

The categorization and classification is done by previous 
works mainly by [Babic et al.](https://dl.acm.org/doi/10.5555/2032305.2032315) who, however, stay on the System Call Dependency Graph level,
while our work abstracts them to Group Relation Graphs.

### Our Idea

We applied `Max Flow` algorithms to our Grgs(see [Polenakis](https://link.springer.com/content/pdf/10.1007%2Fs11416-016-0267-1.pdf)), 
creating a new object, the Flow maps. 

Next we applied similarity metrics (Cosine similarity, Bray Curtis etc.) comparing, in a five-fold test system, unknown samples with known
specimen, deciding if the sample is malware or benign.

### System requirements. 

* Python v3.7
* Networkx v2.4
