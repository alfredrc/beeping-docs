# Documentation

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/community/documentation/) | [Spanish](https://docs-es.beeping.io/community/documentation/)

## Overwiew

This documentary system is also **Open Source**.

This means that you can contribute as far as the documentation is concerned, whether you encounter communication errors, or start writing the documentation in a new language. As we always say as you see it more convenient to contribute.

This documentation has been created with the **Mkdocs** tool and the **Material for MkDocs** template.

## Start

To contribute to the documentation of the project, the first thing we must do is have the documentary project installed on our computer, following the steps in the [Rules](/community/rules) section  until we have made a clone of the repository on our computer.

## Dependencies

In order to run this documentation on our computer we must follow the following steps:

!!! info "Python"

    To perform the installation you need to have **Python** installed
    on your Mac. In case you don't have it
    installed, you can see how it is installed in the
    following website: https://www.python.org/ 

- Install **Mkdocs**

``` bash
$ pip install mkdocs
```

- Install **Material for MkDocs**

``` bash
$ pip install mkdocs-material
```

## Language

The documentation is written in different languages.

Language availability is defined by the mkdocs-xx.yml files.

In the event that we want to work with the Spanish language we must do the following:

``` bash
$ rm mkdocs.yml
$ ln -s mkdocs-es.yml mkdocs.yml
```

In the event that we want to work with the English language we must do the following:

``` bash
$ rm mkdocs.yml
$ ln -s mkdocs-en.yml mkdocs.yml
```

## Start

To start the documentary web on our computer we only need to run the following command:

``` bash
$ mkdocs serve
```

Now we can access the documentation from our browser through the address: http://127.0.0.1:8000

## Quote

!!! quote "Victor Hugo"
    Life is a flower of which love is the honey. 