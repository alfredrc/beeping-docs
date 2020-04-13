# Android SDK

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/components/sdk-android/) | [Spanish](https://docs-es.beeping.io/components/sdk-android/)

## Introduction

**Android SDK** is the **Beeping** framework that aims to decrypt the data that a **Beep** sends us from our application.

## Repository

Then we leave the link of the repository of this component:

* [Android SDK](https://github.com/beeping-io/sdk-android)

## Dependencies

- Android SDK

If you do not have the Android SDK installed you can do them from the following links:

- [MacOs](https://dl.google.com/android/repository/sdk-tools-darwin-3859397.zip)

- [Linux](https://dl.google.com/android/repository/sdk-tools-linux-3859397.zip)

- [Windows](https://dl.google.com/android/repository/sdk-tools-windows-3859397.zip)

Once you download the Androis SDK you must add the environment variable:

``` bash
export ANDROID_HOME=[ANDROIS_SDK_FOLDER]
```

For example, from MacOs I have added the following line in my .bash_profile file:

``` bash hl_lines="3"

vi ~/.bash_profile

export ANDROID_HOME=~/Library/Android/sdk

```

## Compile

The **Android SDK** source code can be compiled in the following Operating Systems:

- MacOS

To compile the code we must follow the following steps:

- [Fork the repository](https://github.com/beeping-io/sdk-android)

[![Fork](/assets/images/shoots/androidsdk-fork.jpg)](/assets/images/shoots/androidsdk-fork.jpg)

-  Make a clone of the repository

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/sdk-android
```

- Enter the SDK directory

``` bash
$ cd sdk-android
```

- Compile the SDK

``` bash
$ sh build.sh
```

- You can find the framework in the directory ./AndroidBeepingCore/build/outputs/aar/ with the following name: **AndroidBeepingCore-release.aar**

## Links

Here you have a series of links related to Android SDK:

- [Tutorial: Android-Hello](/tutorials/android-hello/)

- [Compile "Core System" Android SDK](/components/core/)

## Quote

!!! quote "Oprah Winfrey"
    Turn your wounds into wisdom.
