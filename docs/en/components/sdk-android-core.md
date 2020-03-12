# Core - Android SDK

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/componets/sdk-android-core/) | [Spanish](https://docs-es.beeping.io/componets/sdk-android-core/)

## Compile ( MacOs )

The Android SDK has a dependency on the **Core System** which is a library called **libbeepingcore.so**.

This library is compiled in the **Android SDK** component repository in the root folder

!!! info "libbeepingcore.so"

    This library for now supports the following
    operating systems:
    MacOS

!!! info "Brew"

    To perform the installation you need to have installed **Homebrew** on your Mac. 
    In case you don't have it installed, you can see how it is 
    installed in the following web page: https://docs.brew.sh/Installation

To compile this library you must follow the following steps:

- [Fork the repository](https://github.com/beeping-io/beeping-core)

[![Fork](/assets/images/shoots/core-fork.jpg)](/assets/images/shoots/core-fork.jpg)

- Make a clone of the repository

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beeping-core
```

- Enter the beeping-core directory

``` bash
$ cd beeping-core/android/
```

- Install Android NDK

``` bash
$ brew cask install android-ndk
```

- Build the library

``` bash
$ sh build.sh
```

- At this point you have the library **libbeepingcore.so** compiled to all the architectures into this directory: ./libs

## Install ( MacOs )

The installation of this library for now must be done manually.

Then we leave you the following steps that you must follow:

``` bash
$ cp -R ./libs/* [ANDROID_SDK_PATH]/AndroidBeepingCore/src/main/jniLibs/
```

!!! info "Library Link"

    By default this library is already linked to
    the SDK project, which should not be done
    just open the Android SDK to work with the code
    source.

## Quote

!!! quote "Muhammad Ali"
    Don’t count the days, make the days count.