# Beepbox

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://en.beeping.land/componets/beepbox/) | [Español](https://es.beeping.land/componets/beepbox/)

## Introducción

**Beepbox** es el componente de **Beeping** que tiene como finalidad encriptar datos dentro de un fichero de audio. Este fichero de audio ( como se ha explicado anteriormente ) lo llamamos **Beep**.

**Beepbox** es un binario escrito en C++ que se puede descargar desde nuestro repositorio de Github para distintos sistemas operativos.

## Repositorio

A continuación os dejamos el link del repositorio de este componente:

* [Beepbox](https://github.com/beeping-io/beepbox)

## Compilar

El código fuente de **Beepbox** se puede compilar en los siguientes Sistemas Operativos:

- MacOS

Para compilar el código debemos seguir los siguientes pasos:

- [Hacer un fork del repositorio](https://github.com/beeping-io/beepbox)

[![Fork](/assets/images/shoots/beepbox-fork.jpg)](/assets/images/shoots/beepbox-fork.jpg)

- Hacer un clone del repositorio

``` bash
$ git clone https://github.com/[YOUR_GIT_USERNAME]/beepbox
```

- Entrar en el directorio beepbox

``` bash
$ cd beepbox
```

- Instalar las dependencias

``` bash
$ brew install libsndfile
```

!!! info "Brew"

    Para realizar este último paso necesitas tener instalado **Homebrew** 
    en tu Mac. En el caso de que no lo tengas 
    instalado, puedes ver cómo se instala en la
    siguiente página web: https://docs.brew.sh/Installation

- Compilar Beepbox

``` bash
$ make clean
$ make
```

- Podrás encontrar en binario en el directorio ./bin

## Links

Aquí te dejamos una serie de links relacionados con BeepBox:

- [Tutorial: Crear un Beep](/tutorials/beeps/)

- [Compilar "Core System" de Beepbox](/components/core/)

## Frase

!!! quote "Buddha"
    Todo lo que somos es el resultado de lo que hemos pensado.
