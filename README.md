# CrisprIaDesign

This repository hosts the machine learning scripts and interactive notebooks used to generate the Weissman lab's next-generation CRISPRi and CRISPRa library designs, as detailed in [Horlbeck et al., eLife 2016](https://elifesciences.org/content/5/e19760). While the pre-designed sgRNAs for human and mouse protein-coding genes are available in the original publication, this toolkit is specifically designed for creating custom libraries targeting novel loci, non-coding genes, or organisms outside of human and mouse.

The repository provides step-by-step walkthroughs to apply the exact quantitative models used for the CRISPRi-v2 and CRISPRa-v2 libraries, enabling researchers to predict sgRNA activity and construct new genome-scale libraries for their specific research needs.

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Quick Start Guide](#quick-start-guide)
- [Usage Workflow](#usage-workflow)
- [Required Data Files](#required-data-files)
- [Citation](#citation)

## Prerequisites

Before using this toolkit, ensure you have the following installed:

- **Python:** Version 2.7
- **Jupyter Notebook:** For running interactive scripts.
- **External Tools:**
  - [ViennaRNA](https://www.tbi.univie.ac.at/RNA/)
  - [Bowtie](http://bowtie-bio.sourceforge.net/index.shtml) (Version 1.x, not Bowtie2)

## Installation

1. **Clone the repository:**
   bash
   git clone https://github.com/your-username/CrisprIaDesign.git
   cd CrisprIaDesign
   

2. **Install Python dependencies:**
   bash
   pip install biopython scipy numpy pandas scikit-learn pysam bxpython
   
   *Note: You may need to install `bxpython` specifically as version 0.5.0.*

3. **Install ScreenProcessing:**
   This is a required dependency from the Weissman lab. Install it from the official repository:
   bash
   git clone https://github.com/mhorlbeck/ScreenProcessing.git
   cd ScreenProcessing
   python setup.py install
   cd ..
   

## Project Structure

The repository contains two primary Jupyter notebooks that guide you through the library design process:

- **`Library_design_walkthrough.ipynb`**: The core walkthrough. It details how to apply the established machine learning models to design sgRNAs for your specific loci of interest.
- **`CRISPRiaDesign_example_notebook.ipynb`**: An extended example demonstrating de novo machine learning, predicting sgRNA activity, and constructing genome-scale libraries from scratch.

## Quick Start Guide

To replicate the exact library design process used for the CRISPRi-v2 and CRISPRa-v2 libraries:

1. Launch Jupyter Notebook:
   bash
   jupyter notebook
   
2. Open `Library_design_walkthrough.ipynb`.
3. Follow the step-by-step instructions within the notebook to load data, run predictions, and generate your library.

## Required Data Files

To run the scripts, you will need to download several large genomic data files. The specific files used for the human libraries are linked below, but you can adapt the process for any organism/assembly.

**Important:** The files required for the `Library_design_walkthrough` are conveniently available in a single archive [here](https://ucsf.box.com/s/s4ds471in2ngjer7okavzf5cqf2ebrqj).

1. **Genome Sequence:**
   - Source: UCSC Genome Browser
   - Format: FASTA
   - Example: [hg19](http://hgdownload.cse.ucsc.edu/goldenPath/hg19/bigZips/)

2. **TSS Annotation:**
   - Source: FANTOM5
   - Format: BED
   - Example: [TSS_human](http://fantom.gsc.riken.jp/5/datafiles/phase1.3/extra/TSS_classifier/)

3. **Chromatin Data:**
   - Source: ENCODE Project
   - Format: BigWig
   - Examples:
     - [MNase-seq](https://www.encodeproject.org/files/ENCFF000VNN/)
     - [DNase-seq](https://www.encodeproject.org/files/ENCFF000SVL/)
     - [FAIRE-seq](https://www.encodeproject.org/files/ENCFF000TLU/)

4. **Gene Annotation:**
   - Source: Ensembl (Release 74 used for original libraries)
   - Format: GTF

5. **Gene Aliases:**
   - Source: HGNC
   - Format: Table

## Citation

If you use the code or methodology from this repository, please cite the original publication:

> Horlbeck, M. A., et al. (2016). Compact and highly active next-generation libraries for CRISPR-mediated gene repression and activation. *eLife*, 5, e19760. [DOI: 10.7554/eLife.19760](https://doi.org/10.7554/eLife.19760)
