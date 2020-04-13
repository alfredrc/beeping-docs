# Core - iPhone SDK

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/componets/sdk-iphone-core/) | [Español](https://docs-es.beeping.io/componets/sdk-iphone-core/)

## Compilación ( MacOs )

La SDK tiene una dependencia del **Core System** que es una librería que se llama **libBeepingCoreUniversal.a**.

Esta librería viene compilada en el repositorio del componente **SDK de iPhone** en la carpeta raíz.

!!! info "libBeepingCoreUniversal.a"

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

- Entrar en el directorio sdk

``` bash
$ cd beeping-core/iphone
$ sh build.sh
```

- En este punto ya tienes compilada la librería **libBeepingCoreUniversal.a**

## Instalación ( MacOs )

La instalación de esta librería por ahora se debe hacer de forma manual.

A continuación os dejamos los siguientes pasos que debéis seguir:

``` bash
$ cp -f libBeepingCoreUniversal.a [IPHONE_SDK_PATH]/
```

!!! info "Link de la librería"

    Por defecto esta libreía ya está linkada en 
    el proyecto de la SDK, con lo que no se tendría que hacer
    nada más que abrir la SDK de iPhone para trabajar con el código
    fuente.

## Frase

!!! quote "Benjamin Franklin"
    Bien hecho es mejor que bien dicho.