# Core - Android SDK

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/componets/sdk-android-core/) | [Español](https://docs-es.beeping.io/componets/sdk-android-core/)

## Compilación ( MacOs )

La SDK tiene una dependencia del **Core System** que es una librería que se llama **libbeepingcore.so**.

Esta librería viene compilada en el repositorio del componente **SDK de Android** en la carpeta raíz.

!!! info "libbeepingcore.so"

    Esta librería por ahora soporta los siguientes 
    sistemas operativos:
    MacOs

!!! info "Brew"

    Para realizar la instalación necesitas tener instalado **Homebrew** 
    en tu Mac. En el caso de que no lo tengas 
    instalado, puedes ver cómo se instala en la
    siguiente página web: https://docs.brew.sh/Installation    

Para compilar esta librería debéis seguir los siguientes pasos:

- [Hacer un fork del repositorio](https://github.com/beeping-io/beeping-core)

[![Fork](/assets/images/shoots/core-fork.jpg)](/assets/images/shoots/core-fork.jpg)

- Hacer un clone del repositorio

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beeping-core
```

- Entrar en el directorio beeping-core

``` bash
$ cd beeping-core/android/
```

- Instalar Android NDK

``` bash
$ brew cask install android-ndk
```

- Compilar la librería

``` bash
$ sh build.sh
```

- En este punto ya tienes compilada la librería **libbeepingcore.so** para todas las arquitecturas en el siguiente directorio: ./libs

## Instalación ( MacOs )

La instalación de esta librería por ahora se debe hacer de forma manual.

A continuación os dejamos los siguientes pasos que debéis seguir:

``` bash
$ cp -R ./libs/* [ANDROID_SDK_PATH]/AndroidBeepingCore/src/main/jniLibs/
```

!!! info "Link de la librería"

    Por defecto esta libreía ya está linkada en 
    el proyecto de la SDK, con lo que no se tendría que hacer
    nada más que abrir la SDK de Android para trabajar con el código
    fuente.

## Frase

!!! quote "Muhammad Ali"
    No cuentes los días, haz que los días cuenten.