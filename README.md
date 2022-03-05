# CNVeM

Copy number variations (CNVs) are widely known to be an important mediator for diseases
and traits. The development of high-throughput sequencing (HTS) technologies has provided 
great opportunities to identify CNV regions in mammalian genomes. In a typical
experiment, millions of short reads obtained from a genome of interest are mapped to a
reference genome. The mapping information can be used to identify CNV regions. One
important challenge in analyzing the mapping information is the large fraction of reads that
can be mapped to multiple positions. Most existing methods either only consider reads that
can be uniquely mapped to the reference genome or randomly place a read to one of its
mapping positions. Therefore, these methods have low power to detect CNVs located within
repeated sequences. In this study, we propose a probabilistic model, CNVeM, that utilizes
the inherent uncertainty of read mapping. We use maximum likelihood to estimate locations
and copy numbers of copied regions and implement an expectation-maximization (EM)
algorithm. One important contribution of our model is that we can distinguish between
regions in the reference genome that differ from each other by as little as 0.1%. As our
model aims to predict the copy number of each nucleotide, we can predict the CNV
boundaries with high resolution. We apply our method to simulated datasets and achieve
higher accuracy compared to CNVnator. Moreover, we apply our method to real data from
which we detected known CNVs. To our knowledge, this is the first attempt to predict CNVs
at nucleotide resolution and to utilize uncertainty of read mapping.



**Running code:**

Open the Colab notebook and upload all input files in colab environment as below
![image](https://user-images.githubusercontent.com/69287552/156901639-d3b3d455-39a1-47fa-a53d-3c59efb86e67.png)
next run all from the menu bar as below


![image](https://user-images.githubusercontent.com/69287552/156901667-6448678c-98c1-411d-bca5-c07a7edceb91.png)

then give the following as input:

>>-e20 -B4 -idata.csv -s4 –F137655983 –L137875956 -p10

 (to run CNVeM for 20 rounds of EM iteration with 4 being min lenth of min boundaries, data.csv is input file, sample size is 4, 137655983 is first and F137655983 is last snp and 10 snps)




**Manual**(can get by passing **-h** as input)

Analysis options:

  ex:	Rounds of EM 

  Bx:	determine best boundaries x is minimum length	

  R:	use LogR Ratio for EM

  G:	model genotyping error

  Px:	prior 

  Tx:	threshold x individuals with prob >x are called as carriers

  F:	Fist SNP to be considered

  L:	Last SNP to be considered

  Qx:	set maximim percentage of missing data per SNP


The Dataset:

  ix:	inputfile 

  sx:	Sample Size 

  px:	Number of SNPs

  b:	Inputfile for multiple CNV-borders

  m:	Mapfile for SNPs

  O:	Only one hybridization intensity is in the datafile

  cx:	Number of columns with irrelevant info


Output

  S:	silent EM off

  A:	Calculate distributions of hybridization intensity

  h:	Help-this output


Subsampling

  ux:	number of subsampled snps  

  rx:	subsampled sample size 

  nx:	number of subsamples taken 

  fx:	frequency of  the CNV in resampled datasets 


