# Core - Beepbox

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/componets/beepbox-core/) | [Español](https://docs-es.beeping.io/componets/beepbox-core/)

## Compilación ( MacOs )

Este binario tiene una dependencia del **Core System** que es una librería que se llama **libBeepingCore.a**.

Esta librería viene compilada en el repositorio del componente **BeepBox** en la carpeta ./lib

!!! info "libBeepingCore.a"

    Esta librería por ahora soporta los siguientes 
    sistemas operativos:
    MacOs

Para compilar esta librería debéis seguir los siguientes pasos:

- [Hacer un fork del repositorio](https://github.com/beeping-io/beeping-core)

[![Fork](/assets/images/shoots/core-fork.jpg)](/assets/images/shoots/core-fork.jpg)

- Hacer un clone del repositorio

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beeping-core
```

- Entrar en el directorio beepbox

``` bash
$ cd beeping-core/beepbox
$ make clean
$ make
```
- En este punto ya tienes compilada la librería **libBeepingCore.a**

## Instalación ( MacOs )

La instalación de esta librería por ahora se debe hacer de forma manual.

A continuación os dejamos los siguientes pasos que debéis seguir:

``` bash
$ cp -f libBeepingCore.a [BEEPBOX_PATH]/lib
$ cp -f *.h [BEEPBOX_PATH]/lib/include
```

## Frase

!!! quote "Coco Chanel"
    Para ser insustituible uno siempre debe ser diferente.