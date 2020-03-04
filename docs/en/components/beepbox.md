# Beepbox

## Languages

> This page can be read in the following languages:
>  
> [English](https://en.beeping.land/componets/beepbox/) | [Spanish](https://es.beeping.land/componets/beepbox/)

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

    To perform this last step you need to have installed
   **Homebrew** on your Mac. In case you don't have it
    installed, you can see how it is installed in the
    following web page: https://docs.brew.sh/Installation

- Compile Beepbox

``` bash
$ make clean
$ make
```

- You can find in binary in the directory ./bin

## Downloads

**Beepbox** is a binary that we can download for the following Operating Systems:

- MacOS

So, we leave the download list for each of the Operating Systems:

* [Beepbox for MacOs](https://github.com/beeping-io/beepbox/releases/download/1.0.0/BeepBox-MacOs.zip)

## How does it work

- Download the **beepbox** file for your operating system

- Unzip the file you just downloaded

- Execute the following command to see the help section:

``` bash
$ ./BeepBox
```

This is the result that we will get:

``` bash
************************************************************
*  BeepBox App                                             *
*  Apache License 2.0                                      *
*   -- BeepBox v1.0.0 [20191213] --                        *
************************************************************

Usage: BeepBox --key key --output filename

Options:

  --key                 key       Key identifier (5 characters) to encode in output audio 
                                  (e.g. 01234)
                                  Short name: -k
  --output              filename  Filename of output audio file that will be written 
                                  (.wav)
                                  Short name: -o

```

## Troubleshooting

!!! error "Security"

   It is possible that when executing the file the Operating System
    warn us that its execution is not safe, since it has been
    downloaded from internet. In this case you have to give permissions
    to the file so that it can be executed in our
    OS.

### Security issues

**MacOs**

To solve this problem from a Mac you must follow the following steps:

- Go to "System Preferences"

- Go to "Security and Privacy"

- From the "General" tab you can give permissions to **BeepBox**

## Create a beep

To create a beep we must execute the following command:

``` bash
$ ./BeepBox --key qa020 --output ultrasound.wav
```

This will generate a file called **ultrasound.wav** that when executed will contain an ultrasound.

This ultrasound carries the identifier that we have sent to the component through the --key parameter, so in this case the **Beep** will transpose the **qa020** identifier.

!!! info "Identifier"

    The identifier must be a **String** of **5 characters** that can contain
    any **lowercase letter** or **number**. The component itself will not accept another
    type of format at the moment.

## Links

Here you have a series of links related to BeepBox:

- [Tutorial: Your first Beep](/tutorials/beeps/)

- [Compile "Core System" of Beepbox](/components/core/)

## Quote

!!! quote "Buddha"
    All that we are is the result of what we have thought.
