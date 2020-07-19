# Create a beep

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/tutorials/beeps/) | [Spanish](https://docs-es.beeping.io/tutorials/beeps/)

> **Current version**: 1.1.0

## Introduction

**Beepbox** is the **Beeping** component that aims to encrypt data within an audio file. This audio file (as explained above) we call it **Beep**.

## Step by Step

Here are the steps you must follow to create your first **beep**.

!!! info "Beepbox"

    For now **BeepBox** is only compatible with MacOs
    

The first thing we should do is download the binary:

- [Beepbox for MacOs](https://github.com/beeping-io/beepbox/archive/1.1.0.zip)

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
*   -- BeepBox v1.1.0 [20200716] --                        *
************************************************************

Usage: BeepBox [--mode value] --key key [--duration value] [--interval value] --output filename

Options:

  Options:

  --mode                value     Beeping Mode (0:audible, 1:hidden, 2:non-audible,
                                  3:custom)
                                  Short name: -m
                                  Optional (default: 2).
  --key                 key       Key identifier (5 characters) to encode in output audio 
                                  (e.g. 01234)
                                  Short name: -k
  --duration            value     Duration of output file in seconds (>=5.1)
                                  Short name: -d
                                  Optional (default: 5.1).
  --interval            value     Interval in seconds (>=2.5) between two audio marks 
                                  (e.g. 10)
                                  Short name: -i
                                  Optional (default: 2.5).
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

## Problem solving

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

## Param **mode**

This is an optional parameter that by default has the value of 2, which means that the ultrasound is not audible.

There are other possibilities when generating the beep with different values.

You can check these values ​​from the [following page](/components/changelog/#beepbox)

Let's take an example:

``` bash
$ ./BeepBox --mode 0 --key qa020 --output ultrasound.wav
```
This will generate a file called **ultrasound.wav** that when executed will contain an ultrasound audible by the human being.

## Param **duration**

This is an optional parameter that defaults to 5.1 seconds.

We can modify the duration of the beep as follows.

``` bash
$ ./BeepBox --duration 60.0 --key qa020 --output ultrasound.wav
```

This will generate a file called **ultrasound.wav** that when executed will contain a 60 seconds ultrasound.

## Param **interval**

This is an optional parameter that by default has the value of 2.5 seconds.

We can modify the beep mark interval in seconds as follows.

``` bash
$ ./BeepBox --interval 5.1 --duration 60.0 --key qa020 --output ultrasound.wav
```
This will generate a file called **ultrasound.wav** that when executed will contain an 60 seconds ultrasound, which will have a mark per beep every 5.1 seconds.

## Links

Here you have a series of links related to BeepBox:

- [Components: BeepBox](/components/beepbox/)

- [Compile "Core System" de Beepbox](/components/core/)

## Quote

!!! quote "Tim Berners-Lee"
    The Web as I envisaged it, we have not seen it yet. The future is still so much bigger than the past.
