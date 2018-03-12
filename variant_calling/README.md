# Variant Calling Recipes
The recipes in this directory revolve around tools for variant calling.

For all examples that follow, replace the name after the colon with the extension name of the container you want. For example
```
singularity pull shub://mbhall88/Singularity_recipes:mccortex
```
This will pull the Singularity.mccortex recipe. If you wanted to pull the (hypothetical) Singularity.foo container, then you would run
```
singularity pull shub://mbhall88/Singularity_recipes:foo
```
By the default the containers will have a name such as `mbhall88-Singularity_recipes-master-mccortex.simg`. To name it something more succinct, run
```
singularity pull --name customname.simg shub://mbhall88/Singularity_recipes:mccortex
```
You don't necessarily have to pull the container onto your machine - you can execute from the Singularity Hub with
```
singularity exec shub://mbhall88/Singularity_recipes mccortex31 --help
```
But this takes much longer to run than pulling the container and then executing it locally.

For a full list of usage examples, check out the [Singularity Hub usage docs](https://www.singularity-hub.org/collections/685/usage).

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
