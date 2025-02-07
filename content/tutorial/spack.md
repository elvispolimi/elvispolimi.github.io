+++
title = "Build your toolchain"
aliases = ["howto"]
date = "2025-02-06"
author = "Elvis Lab"
showMetadata = false
+++

This tutorial show how it is possible to use `spack` to build your toolchain from scratch and how to use `module` to manage the software.
These tools operate in userspace, making them suitable to work both on your local machine and on an HPC center.
Actually on CINECA it is the preffered way of building software.
We assume a Linux operating system.

### Start from `spack`

From a suitable working directory (e.g. `/opt`), you need to clone and initialize spack from its repository.
Please, note that `spack` will install all the software within the repository folder.
To grab it, you can issue the following commands in a terminal:
```bash
$ git clone https://github.com/spack/spack.git
$ source spack/share/spack/setup-env.sh
```

Most of the `spack` package are compiled from sources.
For this reason it is important to let it know the available system compilers, by issuing the following command:
```bash
$ spack compiler find
```
The output of this command list the found compilers in the current environment

### Choose your compiler

It is better to build our toolchain starting from a C/C++ compiler to improve consistency and solve compatibility issues.
For example, the system `gcc` shipped in Fedora is usually not supported by `cuda` because it is new.
The locate the available packages, you can issue the following command `spack list <value>`. It will provide in output all the packages with the string "<value>".

It is possible to configure how `spack` will materialize, i.e. compile, the target software.
The command `spack info <package>` will show all versions and variants, i.e. configure options.
The command `spack spec <package>` will show how spack will materialize the package, listing all depedendencies.
It will use symbol `[+]` to tell if the dependency will be provided by a spack package, the symbol `[e]` to tell if it uses the depedency found on the system.

For example, in this tutorial we use `gcc` 13, with `binutils`, `grphite` and the languages C,C++,fortran.
To reach this goal we issue the following command:
```bash
$ spack install gcc@13 binutils=true graphite=true languages=c,c++,fortran
```
You can use the symbol `@` to specify the version.
Moreover, if the variant is a bolean you can use the symbol `+` for true value and the symbol `~` for false value.
By using this short notation the previous command becomes `spack install gcc@13+binutils+graphite languages=c,c++,fortran`.

Now that we have our shiny new compiler, we need to load it and let `spark` know that it can use it compile additional stuff, by issuing the commands:
```bash
$ spack load gcc@13
$ spack compiler find
```

If you target gcc, you must also install its runtime, by issuing the command:
```bash
$ spack install gcc-runtime %gcc@13
```
You can specify the compiler used by using the symbol `%`.

### Build the dependencies

With the new compiler you can build all the libraries and additional compilers that you need.
For example, if you want to install boost with all the components, you can issue the following command:
```bash
$ spack install boost@1.87.0+atomic+chrono+container+context+contract+date_time+exception+fiber+filesystem+graph+graph_parallel+icu+iostreams+json+locale+log+math+program_options+random+regex+serialization+shared+signals+system+timer+type_erasure+url+wave %gcc@13
```

In the `install` command you can also specify the target CPU architecture.
By default it will target the machine where `spack` is running, but you can specify it with the `target` variant, e.g. `taregt=haswell`.
`spack` is a collection of python scripts to drive the configuration and compilation steps.
If you need a specific compilation flag, you can customize it.
The python file for all the packages are stored in `spack/var/spack/repos/builtin/packages`, and named `package.py`.

Please note that `spack` use an hash value as naming convention, to let two different configuaration of a package coexist.
For this reason, you can use the command `spack find -l` to show the hash.
Then, you can find out how the package has been compiled by issuing the command `spack spec \<hash>`.

To remove a package you can use the command `spack uninstall <package>`.
However, `spack` will refuse to uninstall a package if it is a dependency of another package.
You can use the flag `--dependents` to remove also that dependencies.

### Manage software

While `spack` is awesome to compile software, its interface to manage the software is slightly cumbersome.
For this reason we use environmental modules to manage it.
At first we need to install module using spack and then connect it with `spack`:
```bash
$ spack install environment-modules
$ spack module tcl refresh
$ spack config add modules:default:enable:[tcl]
```

Then, we need to load the package and initialize the environment:
```bash
$ spack load environment-modules
$ source $(spack location -i environment-modules)/init/bash
```

### Enabling the software at the terminal start-up

You can append the following lines at the `~/.bashrc` file:
```bash
$ source /opt/dgadioli/spack/share/spack/setup-env.sh
$ spack load environment-modules
$ source $(spack location -i environment-modules)/init/bash
```


### References

Slides [spack.pdf](/slides/spack.pdf) [spack.md](/slides/spack.md)
