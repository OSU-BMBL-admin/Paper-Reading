# Paper-Reading
This is a repository for the lab members to share the paper collections and summaries. 
``` markdown
MetaQUBIC is a QUBIC derived biculstering-based C package specifically designed to analysis metagenomic and metatranscriptomic data from read alignment to gene module detection along with the enrichment analysis.

Meta-Qubic consists of three main steps: <b>(i)</b> Gene mapping and catalog 
construction, <b>(ii)</b> hGEM generation and filtering, and <b>(iii)</b> biclustering and enrichment analyses. See details in <b>Figure 1</b>.
\
\
<center><img src="http://bmbl.sdstate.edu/metaqubic/Tutorial/Figure1.jpg" alt="The MetaQUBIC pipeline" height="80%" width="85%">

<b>Figure 1.</b> The MetaQUBIC pipeline</center>\
\
<b>Citation: </b> -

*All copyrights reserved by <a href="https://www.researchgate.net/profile/Qin_Ma3">Dr. Qin Ma</a> and <a href="https://www.sdstate.edu/agronomy-horticulture-plant-science/bioinformatics-and-mathematical-biosciences-lab">BMBL</a>

***

## Content
- [1. Introduction and installation]
    + [1.1 Environment]
    + [1.2 Built-in tools]
    + [1.3 Installation]
- [2. Input data preperation]
- [3. The general pipeline (from fastq to enrichment analysis)]
    + [3.1 Part 1 - Gene mapping and catalog construction]
    + [3.2 Part 2 - hGEM generation and filtering]
    + [3.3 Part 3 - Biclustering and enrichment analyses]
- [4. Advance executions]
    + [4.1 Execution-1 (using index files)]
    + [4.2 Execution-2 (update hGEM vs new hGEM)]
    + [4.3 Execution-3 (starting from biclustering)]
    + [4.4 Execution-4 (various enrichment analyses)]
    + [4.5 Execution-5 (link to HUManN2)]  
- [5. Parameter control]
- [6. File format examples]
- [7. Acknowledgement]
- [8. References]




***

## 1. Introduction and installation 

### 1.1 Environment

MetaQUBIC is an integrated C package requires a basic <b>UNIX/Linux environment</b>. The gcc compiler with <b>version 4.8.5 or higher</b> is required to be pririor installed. More details can be found <a href="https://gcc.gnu.org/wiki/InstallingGCC">here</a>. <b>Currently, MetaQUBIC does not support Mac or Windows system.</b>
\
\
Our experimental test performed for mapping 735 datasets to the 9M genes reference were proceeded on the <a href="https://www.xsede.org/"><b>XSEDE</b></a> PSC cluster which used an overall RAM of <b>128GB</b>. Higher RAM showed less effect to the running time, while it is still required for larger dataset (more samples or genes) analysis to prevent memory overflow. Due to the large memory requirement, we recommend users run MetaQUBIC on a high-performance computer (HPC), such as XSEDE, rather than local computers.

### 1.2 Built-in tools

All third-party tools used in MetaQUBIC pipeline has been integrated in the package and will be installed automatically alone with the installation of MetaQUBIC. (See [Installation] below.)

  - <a href="http://bowtie-bio.sourceforge.net/bowtie2/index.shtml">Bowtie2</a> (version 2.3.4.3): an aligning tool for sequence mapping;
  - <a href="http://www.htslib.org/doc/">Samtools</a> (version 1.9): for sam to bam format transfer and alignement result assembly;
  - <a href="https://bedtools.readthedocs.io/en/latest/">Bedtools</a> (version 2.16.1): for coverage analysis;
  - <a href="https://www.python.org/">Python</a> (version 2.7.10): coding environment;
  - <a href="https://github.com/scipy/scipy">scipy package</a> (version 0.13.0b1): a python library for hypergeometric calculation;
  - <a href="http://bioconductor.org/packages/devel/bioc/html/QUBIC.html">QUBIC</a> (version 1.9.1): a biclustering tool for gene module detection.
  ```
