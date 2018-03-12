# Nanopore Recipes
The recipes in this directory revolve around tools for analysising nanopore
data.  

For all examples that follow, replace the name after the colon with the extension
name of the container you want. For example  

```sh
singularity pull shub://mbhall88/Singularity_recipes:nanoporeqc
```

This will pull the `Singularity.nanoporeqc` recipe. If you wanted to pull the
(hypothetical) `Singularity.foo` container, then you would run

```sh
singularity pull shub://mbhall88/Singularity_recipes:foo
```

---

By the default the containers will have a name such as `mbhall88-Singularity_recipes-master-nanoporeqc.simg`.
To name it something more succinct, run

```sh
singularity pull --name customname.simg shub://mbhall88/Singularity_recipes:nanoporeqc
```

You don't necessarily have to pull the container onto your machine - you can
execute from the Singularity Hub with

```sh
singularity exec shub://mbhall88/Singularity_recipes pistis --help
```

But this takes much longer to run than pulling the container and then
executing it locally.  

For a full list of usage examples, check out the [Singularity Hub usage docs](https://www.singularity-hub.org/collections/685/usage).  

---

## nanoporeqc
This container holds a set of tools that I use for quality control of nanopore
data.

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

```sh
singularity pull --name nanoporeqc.simg shub://mbhall88/Singularity_recipes:nanoporeqc
singularity exec nanoporeqc.simg filtlong --help
```
