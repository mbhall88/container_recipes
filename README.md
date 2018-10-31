# Singularity Recipes

[![https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg](https://www.singularity-hub.org/static/img/hosted-singularity--hub-%23e32929.svg)](https://singularity-hub.org/collections/685)
This repository is for all of my Singularity recipes and is linked to Singularity
Hub where they are built and available.

To find out more information about the different recipes, go into the directory
and read through the documentation there.

## Table of Contents
* [Nanopore](https://github.com/mbhall88/Singularity_recipes/tree/master/nanopore) -
Containers for software packages/tools relating to analysis of Oxford Nanopore
Technologies sequencing data.
* [Variant Calling](https://github.com/mbhall88/Singularity_recipes/tree/master/variant_calling) -
Containers for variant calling software.
* [Assembly](https://github.com/mbhall88/Singularity_recipes/tree/master/assembly) -
Containers for genome assembly software.

---

For all recipes in the subdirectories, replace the name after the colon with the extension name of the container you want. For example
```
singularity pull shub://mbhall88/Singularity_recipes:nanoporeqc
```
This will pull the [`Singularity.nanoporeqc` recipe](https://github.com/mbhall88/Singularity_recipes/blob/master/nanopore/Singularity.nanoporeqc). If you wanted to pull the (hypothetical) `Singularity.foo` container, then you would run
```
singularity pull shub://mbhall88/Singularity_recipes:foo
```
By default the containers will have a name such as `mbhall88-Singularity_recipes-master-foo.simg`. To name it something more succinct, run
```
singularity pull --force --name customname.simg shub://mbhall88/Singularity_recipes:foo
```
Note: The `--force` option will override any container that exists in that location with the same name. If you are trying to pull a container to update a pre-existing one, then the `--force` flag is necessary.

You don't necessarily have to pull the container onto your machine - you can execute from the Singularity Hub with
```
singularity exec shub://mbhall88/Singularity_recipes:mccortex mccortex31 --help
```
But this takes much longer to run than pulling the container and then executing it locally.

For a full list of usage examples, check out the [Singularity Hub usage docs](https://www.singularity-hub.org/collections/685/usage).

---

# Template
I have also included a template `Singularity.template` which can be used for
building up your own recipes.
