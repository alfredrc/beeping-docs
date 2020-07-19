# Beepbox

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/components/beepbox/) | [Spanish](https://docs-es.beeping.io/components/beepbox/)

> **Current version**: 1.1.0

## Introduction

**Beepbox** is the **Beeping** component that aims to encrypt data within an audio file. This audio file (as explained above) we call it **Beep**.

**Beepbox** is a binary written in C ++ that can be downloaded from our Github repository for different operating systems.

## Repository

Then we leave the link of the repository of this component:

* [Beepbox](https://github.com/beeping-io/beepbox)

## Compile

The **Beepbox** source code can be compiled in the following Operating Systems:

- MacOS

To compile the code we must follow the following steps:

- [Fork the repository](https://github.com/beeping-io/beepbox)

[![Fork](/assets/images/shoots/beepbox-fork.jpg)](/assets/images/shoots/beepbox-fork.jpg)

- Make a clone of the repository

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beepbox
```

- Enter the beepbox directory

``` bash
$ cd beepbox
```

- Install dependencies

``` bash
$ brew install libsndfile
```

!!! info "Brew"

    To perform this last step you need to have installed **Homebrew** on your Mac. 
    In case you don't have it installed, you can see how it is 
    installed in the following web page: https://docs.brew.sh/Installation

- Compile Beepbox

``` bash
$ make clean
$ make
```

- You can find in binary in the directory ./bin

## Links

Here you have a series of links related to BeepBox:

- [Tutorial: Create a Beep](/tutorials/beeps/)

- [Compile "Core System" of Beepbox](/components/core/)

## Quote

!!! quote "Buddha"
    All that we are is the result of what we have thought.
