# SDK de Android

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/components/sdk-android/) | [Español](https://docs-es.beeping.io/components/sdk-android/)

## Introducción

**SDK de android** es el framework de **Beeping** que tiene como finalidad desencriptar los datos que nos envía un **Beep** desde nuestra aplicación.

## Repositorio

A continuación os dejamos el link del repositorio de este componente:

* [Android SDK](https://github.com/beeping-io/sdk-android)

## Dependencias

- Android SDK

Si no tienes instalado el Android SDK puedes hacerlos desde los siguientes links:

- [MacOs](https://dl.google.com/android/repository/sdk-tools-darwin-3859397.zip)

- [Linux](https://dl.google.com/android/repository/sdk-tools-linux-3859397.zip)

- [Windows](https://dl.google.com/android/repository/sdk-tools-windows-3859397.zip)

Una vez descargues el Androis SDK debes añadir la variable de entorno: 

``` bash
export ANDROID_HOME=[ANDROIS_SDK_FOLDER]
```

Por ejemplo desde MacOs yo he añadido la siguiente línea en mi fichero .bash_profile:

``` bash hl_lines="3"

vi ~/.bash_profile

export ANDROID_HOME=~/Library/Android/sdk

```

## Compilar

El código fuente del **SDK de Android** se puede compilar en los siguientes Sistemas Operativos:

- MacOS

Para compilar el código debemos seguir los siguientes pasos:

- [Hacer un fork del repositorio](https://github.com/beeping-io/sdk-android)

[![Fork](/assets/images/shoots/androidsdk-fork.jpg)](/assets/images/shoots/androidsdk-fork.jpg)

- Hacer un clone del repositorio

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/sdk-android
```

- Entrar en el directorio de la sdk de Android

``` bash
$ cd sdk-android
```

- Compilar la SDK

``` bash
$ sh build.sh
```

- Podrás encontrar en framework en el directorio ./AndroidBeepingCore/build/outputs/aar/ con el nombre: **AndroidBeepingCore-release.aar**

## Links

Aquí te dejamos una serie de links relacionados con la SDK de Android:

- [Tutorial: Android-Hello](/tutorials/android-hello/)

- [Compilar "Core System" de la SDK de Android](/components/core/)

## Frase

!!! quote "Oprah Winfrey"
    Transforma tus heridas en sabiduria.
