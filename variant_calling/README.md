# Variant Calling Recipes
The recipes in this directory revolve around tools for variant calling.

---

## McCortex
This container holds an installation of [McCortex](https://github.com/mcveanlab/mccortex) (version 0.2).

McCortex is a tool for population *de novo* assembly and variant calling. Note
the installation of McCortex in this container has been built with a maximum
container size of 31. If you would like a different kmer size you can clone the
recipe file and [build with the appropriate flag](https://github.com/mcveanlab/mccortex#build).

To run McCortex you need to first pull the container and then
execute the container with the name of any of the tools, following by their
normal CLI parameters/options/arguments.

```
singularity pull --name mccortex.simg shub://mbhall88/Singularity_recipes:mccortex
singularity exec mccortex.simg mccortex31 --help
```
