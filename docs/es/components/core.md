# Core System

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://en.beeping.land/componets/core/) | [Español](https://es.beeping.land/componets/core/)

## Introducción

Como hemos comentado en la introducción de este apartado el **Core System** son librerías que están escritas en C++ que son las que se encargan de encriptar y desencriptar los datos que son transportados por los ultrasonidos.

Estas librerías están escritas en C++ y son **Open Source**, con lo que pueden ser compiladas y modificadas por cualquier ingeniero.

## Repositorios

Se unificado un único repositorio con estas librerías, aunque tienen efecto sobre distintos componentes. Eso sifnifica que cada uno de los componentes de Beeping pueden necesitas una o más de una de estas librerías como dependencias.

Podéis encontrar todas estas librerías en el siguiente repositorio:

* [Core System](https://github.com/beeping-io/beeping-core)

Dentro de este repositorio veréis que hay una calsificación por componente al que afecta el **Core System** que contiene dentro de cada carpeta el código fuente necesario para cada uno de los componentes que se utilizan en la tecnología de **Beeping**.

## Componentes

A continuación os dejamos una lista de los componentes que se ven afectados por el **Core System** y donde encontrar el código fuente corresponsiente:

* [Beepbox](https://github.com/beeping-io/beeping-core/beepbox)
* [iPhone SDK](https://github.com/beeping-io/beeping-core/sdk-iphone)
* [Android SDK](https://github.com/beeping-io/beeping-core/sdk-android)

## Beepbox

### MacOs

Este binario tiene una dependencia del **Core System** que es una librería que se llama **libBeepingCore.a**.

Esta librería viene compilada en el repositorio del componente **BeepBox** en la carpeta ./lib

!!! info "libBeepingCore.a"

    Esta librería por ahora soporta los siguientes 
    sistemas operativos:
    MacOs

Para compilar esta librería debéis seguir los siguientes pasos:

- [Hacer un fork del repositorio](https://github.com/beeping-io/beeping-core)

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

### Instalación en MacOs

La instalación de esta librería por ahora se debe hacer de forma manual.

A continuación os dejamos los siguientes pasos que debéis seguir:

``` bash
$ cp -f libBeepingCore.a [BEEPBOX_PATH]/lib
$ cp -f *.h [BEEPBOX_PATH]/lib/include
```

## Frase

!!! quote "Northrop Frye"
    La máquina más eficiente tecnológicamente que el hombre haya inventado es el libro.
