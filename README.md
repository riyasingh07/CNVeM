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
