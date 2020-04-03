# Assembly Recipes

[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/685)
The recipes in this directory revolve around tools for genome assembly.

[TOC]: #

# Table of Contents
- [[canu][canu]](#canu)
- [[haslr][haslr]](#haslr)
- [polish](#polish)
- [[racon][racon]](#racon)



## canu

<https://github.com/marbl/canu>

```sh
uri="library://mbhall88/default/canu"
singularity exec "$uri" canu --help
```

## haslr

<https://github.com/vpc-ccg/haslr>

```shell
uri="library://mbhall88/default/haslr"
singularity exec "$uri" haslr.py --help
```

## polish

This container holds a set of tools for polishing genome assemblies.

```sh
singularity pull --force --name polish.simg shub://mbhall88/Singularity_recipes:polish
singularity exec polish.simg pilon --help
```

#### Tools

The tools in this container are:
* [pilon](https://github.com/broadinstitute/pilon/wiki) for automatically improving
  draft assemblies and finding variation among strains, including large event detection.
* [ngm](https://cibiv.github.io/NextGenMap/) for fast and accurate read mapping in
  highly polymorphic genomes.
* [samtools](http://www.htslib.org/doc/samtools.html) - utilities for SAM format.
* [centrifuge](https://github.com/infphilo/centrifuge) - classifier for metagenomic
  sequences.
* [nanopolish](https://github.com/jts/nanopolish) can calculate an improved consensus
  sequence for a draft genome assembly, detect base modifications, call SNPs and indels
  with respect to a reference genome and more.

To run any of these programs you need to first pull the container and then execute the
container with the name of any of the tools, following by their normal CLI
parameters/options/arguments.

## racon

<https://github.com/lbcb-sci/racon>

```shell
uri="library://mbhall88/default/racon"
singularity exec "$uri" racon --help
```
