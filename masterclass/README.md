# Phylogenetics at the QIB &mdash; training material


date       |         location                    | time 
    ----   |           ----                      | ----
2023.11.13 | **UG55A** (QIB, upper ground floor) | **1400 to 1600**
2023.11.20 | **UG44A** (QIB, upper ground floor) | **1400 to 1600**


This repository contains data sets and links you may find useful when following the lectures. 
Some links will only work if you have access to the NBI/QIB network.

This repository is still under construction, come back later for more material. 

## Read before the lectures

The lectures assume some familiarity with the command line and with resources at the QIB. 
[Check the list of resources available at the QIB (internal link)](https://quadram-institute.atlassian.net/servicedesk/customer/portal/3/article/10059964?src=1311561195)
if you need further training. The binfie team also provides [a list of external training resources](https://quadram-institute.atlassian.net/servicedesk/customer/portal/3/article/6455523).

In particular, although we'll try to accomodate all levels of experience, this is not an introductory course on phylogenetics. 
The following is a list of open resouces I recommend for a overview of modern phylogenetics, in order of relevance for
the lectures:

* [Tutorials on phylogenetic and phylogenomic inference maintained by Michael Matschiner](https://github.com/mmatschiner/tutorials)
* [**Phylogenetics in the Genomic Era**, edited by Celine Scornavacca, Frédéric Delsuc, and Nicolas Galtier](https://hal.science/hal-02535070v3)
* [**Data Integration, Manipulation and Visualization of Phylogenetic Trees**, by Guangchuang Yu](https://yulab-smu.top/treedata-book/), based on the `ggtree` suite of R packages.
* [**Phylogenetic Comparative Methods**, by Luke Harmon)](https://lukejharmon.github.io/pcm/)

And if you are looking for paper textbooks, these are the ones I tend to follow more closely:

* [**Molecular Evolution: A Statistical Approach**, by Ziheng Yang](http://abacus.gene.ucl.ac.uk/MESA/)
* [**Inferring Phylogenies**, by Joseph Felsenstein](https://global.oup.com/academic/product/inferring-phylogenies-9780878931774)

## The data sets

To reduce their sizes, the data sets are compressed with [`XZ`](https://tukaani.org/xz/), and furthermore archived with
[`tar`](https://en.wikipedia.org/wiki/Tar_(computing)) when necessary. Thus if you want to decompress or extract the
contents of a file, the commands on linux are something like (depending on the file suffix):

```console
xz file.xz           # compressed with XZ
tar Jxvf file.txz    # archived and compressed 
tar Jxvf file.tar.xz # same as above ("txz" = "tar.xz")
```

## Phylogenetic tools

Here is a list of software and libraries that might be of interest. We will not discuss all of them during the lectures.

#### python / R

* [cogent3](https://github.com/cogent3/cogent3) Comparative Genomics Toolkit - a python library for analysis of genomic sequence data
* [ggtree](https://bioconductor.org/packages/release/bioc/html/ggtree.html) an R library for tree visualisaion (see
  [book above](https://yulab-smu.top/treedata-book/) for other related libraries)
* [phangorn](https://github.com/KlausVigo/phangorn) for Phylogenetic analysis in R (expands the main phylogenetic library for R 
  [ape](https://github.com/emmanuelparadis/ape)
* [dendropy](https://dendropy.org/), [ETE](https://github.com/etetoolkit/ete), and
  [treeswift](https://github.com/niemasd/TreeSwift) are the main python modules for tree manipulation and visualisation

#### Phylogenetic inference 

* [IQ-TREE](http://www.iqtree.org/) and [RAxML-NG](https://github.com/amkozlov/raxml-ng) are the most popular tools for
  phylogenetic inference by maximum likelihood (ML).
* [phyml](https://github.com/stephaneguindon/phyml), [PAML](http://abacus.gene.ucl.ac.uk/software/paml.html), and
  [phylip](https://phylipweb.github.io/phylip/) are also quite general tree inference software (focus on ML).
* [UShER](https://usher-wiki.readthedocs.io/en/latest/index.html) is a parsimony-based software capable of handling
  large trees, for closely-related sequences (as in SARS-CoV-2)
* [EPA-ng](https://github.com/Pbdas/epa-ng), [RAxML-EPA](http://sco.h-its.org/exelixis/web/software/epa/index.html), and 
  [pplacer](http://matsen.fhcrc.org/pplacer/) for phylogenetic placement.
* [BEAST](https://beast.community/)/[BEAST2](https://www.beast2.org/), [MrBayes](https://nbisweden.github.io/MrBayes/), [PhyloBayes](https://pbil.univ-lyon1.fr/software/phylobayes/),
  and [RevBayes](https://revbayes.github.io/) are the main Bayesian phylogenetic inference software.
* [rapidNJ](https://github.com/somme89/rapidNJ) and [decenttree](https://github.com/iqtree/decenttree) for
  distance-based inference

#### Divergence times, Ancestral inference

* [pastML](https://github.com/evolbioinfo/pastml) Ancestral state reconstruction, with a python module
* [treetime](https://github.com/neherlab/treetime) for divergence times estimation and ancestral state reconstruction
* [chronumental](https://github.com/theosanderson/chronumental) for very large scale divergence times estimation

### Other tools

* [goalign](https://github.com/evolbioinfo/goalign) and [gotree](https://github.com/evolbioinfo/gotree) for tree and sequence manipulation on the command line. 
  See also [phyx](https://github.com/FePhyFoFum/phyx) and [seqmagick](https://github.com/fhcrc/seqmagick).  
* [SNPPar](https://github.com/d-j-e/SNPPar) to find Homoplasic SNPs (using `treetime` or `pastML`)


