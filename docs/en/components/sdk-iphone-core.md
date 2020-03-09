# Core - iPhone SDK

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.land/componets/sdk-iphone-core/) | [Spanish](https://docs-es.beeping.land/componets/sdk-iphone-core/)

## Compile ( MacOs )

The iPhone SDK has a dependency on the **Core System** which is a library called **libBeepingCoreUniversal.a**.

This library is compiled in the **iPhone SDK** component repository in the root folder

!!! info "libBeepingCoreUniversal.a"

    This library for now supports the following
    operating systems:
    MacOS

To compile this library you must follow the following steps:

- [Fork the repository](https://github.com/beeping-io/beeping-core)

- Make a clone of the repository

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beeping-core
```

- Enter the beepbox directory

``` bash
$ cd beeping-core/sdk
$ make clean
$ make
```

- At this point you have the library **libBeepingCoreUniversal.a** compiled

## Install ( MacOs )

The installation of this library for now must be done manually.

Then we leave you the following steps that you must follow:

``` bash
$ cp -f libBeepingCoreUniversal.a [IPHONE_SDK_PATH]/
```

!!! info "Library Link"

    By default this library is already linked to
    the SDK project, which should not be done
    just open the iPhone SDK to work with the code
    source.

## Quote

!!! quote "Benjamin Franklin"
    Well done is better than well said.