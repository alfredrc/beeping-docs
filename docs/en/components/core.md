# Core System

## Languages

> This page can be read in the following languages:
>  
> [English](https://en.beeping.land/componets/core/) | [Spanish](https://es.beeping.land/componets/core/)

## Introducción

As we have commented in the introduction of this section, the **Core System** are libraries that are written in C ++ that are responsible for encrypting and decrypting the data that is transported by ultrasound.

These libraries are written in C ++ and are **Open Source**, so they can be compiled and modified by any engineer.

## Repositories

A single repository was unified with these libraries, although they have an effect on different components. That means that each of the components of Beeping may need one or more of one of these libraries as dependencies.

You can find all these libraries in the following repository:

* [Core System](https://github.com/beeping-io/beeping-core)

Within this repository you will see that there is a qualification per component that is affected by the **Core System** that contains within each folder the necessary source code for each of the components used in **Beeping** technology.

## Components

Here is a list of the components that are affected by the **Core System** and where to find the corresponding source code:

* [Beepbox](https://github.com/beeping-io/beeping-core/beepbox)
* [iPhone SDK](https://github.com/beeping-io/beeping-core/sdk-iphone)
* [Android SDK](https://github.com/beeping-io/beeping-core/sdk-android)

## Beepbox

### MacOs

This binary has a dependency on the **Core System** which is a library called **libBeepingCore.a**.

This library is compiled in the **BeepBox** component repository in the ./lib folder

!!! info "libBeepingCore.a"

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
$ cd beeping-core/beepbox
$ make clean
$ make
```

- At this point you have the library **libBeepingCore.a** compiled

### MacOs installation

The installation of this library for now must be done manually.

Then we leave you the following steps that you must follow:

``` bash
$ cp -f libBeepingCore.a [BEEPBOX_PATH]/lib
$ cp -f *.h [BEEPBOX_PATH]/lib/include
```

## Quote

!!! quote "Mother Teresa"
    The most technologically efficient machine that man has ever invented is the book.
