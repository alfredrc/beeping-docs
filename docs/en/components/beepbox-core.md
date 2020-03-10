# Core - Beepbox

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.land/componets/beepbox-core/) | [Spanish](https://docs-es.beeping.land/componets/beepbox-core/)

## Compile ( MacOs )

This binary has a dependency on the **Core System** which is a library called **libBeepingCore.a**.

This library is compiled in the **BeepBox** component repository in the ./lib folder

!!! info "libBeepingCore.a"

    This library for now supports the following
    operating systems:
    MacOS

To compile this library you must follow the following steps:

- [Fork the repository](https://github.com/beeping-io/beeping-core)

[![Fork](/assets/images/shoots/core-fork.jpg)](/assets/images/shoots/core-fork.jpg)

- Make a clone of the repository

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beeping-core
```

- Enter the beepbox directory

``` bash
$ cd beeping-core/beepbox
$ make clean
$ make
```

- At this point you have the library **libBeepingCore.a** compiled

## Install ( MacOs )

The installation of this library for now must be done manually.

Then we leave you the following steps that you must follow:

``` bash
$ cp -f libBeepingCore.a [BEEPBOX_PATH]/lib
$ cp -f *.h [BEEPBOX_PATH]/lib/include
```

## Quote

!!! quote "Coco Chanel"
    In order to be irreplaceable one must always be different.