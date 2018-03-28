# Nanopore Recipes
[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/685)
The recipes in this directory revolve around tools for analysing nanopore
data.

---

## nanoporeqc
This container holds a set of tools that I use for quality control of nanopore
data.

```sh
singularity pull --force --name nanoporeqc.simg shub://mbhall88/Singularity_recipes:nanoporeqc
singularity exec nanoporeqc.simg filtlong --help
```

#### Tools
The tools in this container are:
  * [pistis](https://github.com/mbhall88/pistis) for plotting.
  * [porechop](https://github.com/rrwick/Porechop) for finding and removing adapters from Oxford Nanopore reads.
  * [filtlong](https://github.com/rrwick/Filtlong) for filtering long reads by quality.
  * [NanoLyse](https://github.com/wdecoster/nanolyse) to remove reads that map to lambda phage.
  * [NanoStat](https://github.com/wdecoster/nanostat) to calculate various statistics from a long read sequencing dataset in fastq, bam or albacore sequencing summary format.
  * [minimap2](https://github.com/lh3/minimap2) for aligning long reads to a reference.
  * [samtools](http://www.htslib.org/doc/samtools.html) - utilities for SAM format.
  * [centrifuge](https://github.com/infphilo/centrifuge) - classifier for metagenomic seqeunces.

To run any of these programs you need to first pull the container and then
execute the container with the name of any of the tools, following by their
normal CLI parameters/options/arguments.

---

## fast5
This container holds a C++ header-only library for reading Oxford Nanopore Fast5
files [developed by Jared Simpson's lab](https://github.com/mateidavid/fast5).
Of specific interest here is access to the python wrapper `f5pack` which
facilitates packing and unpacking (compression) of nanopore data.

```sh
singularity pull --force --name fast5.simg shub://mbhall88/Singularity_recipes:fast5
singularity exec fast5.simg f5pack --help
```
