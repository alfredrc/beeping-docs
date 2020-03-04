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

    Para realizar este último paso necesitas tener instalado 
   **Homebrew** en tu Mac. En el caso de que no lo tengas 
    instalado, puedes ver cómo se instala en la
    siguiente página web: https://docs.brew.sh/Installation

- Compilar Beepbox

``` bash
$ make clean
$ make
```

- Podrás encontrar en binario en el directorio ./bin

## Downloads

**Beepbox** es un binario que podemos descargar para los siguientes Sistemas Operativos:

- MacOS

A continuación os dejamos la lista de descarga para cada uno de los Sistemas Operativos:

* [Beepbox para MacOs](https://github.com/beeping-io/beepbox/releases/download/1.0.0/BeepBox-MacOs.zip)

## Cómo funciona

- Descargar el fichero **beepbox** para vuestro sistema operativo

- Descomprimir el archivo que acabáis de descargar

- Ejecutar el siguiente comando para ver la sección de help:

``` bash
$ ./BeepBox
```

Este es el resultado que vamos a obtener:

``` bash
************************************************************
*  BeepBox App                                             *
*  Apache License 2.0                                      *
*   -- BeepBox v1.0.0 [20191213] --                        *
************************************************************

Usage: BeepBox --key key --output filename

Options:

  --key                 key       Key identifier (5 characters) to encode in output audio 
                                  (e.g. 01234)
                                  Short name: -k
  --output              filename  Filename of output audio file that will be written 
                                  (.wav)
                                  Short name: -o

```

## Posibles problemas

!!! error "Seguridad"

    Es posible que al ejecutar el fichero el Sistema Operativo
    nos avise de que su ejecución no es segura, ya que se ha 
    descargado desde Internet. En este caso hay que darle permisos 
    al fichero para que se pueda ejecutar en nuestro 
    Sistema Operativo.

### Problemas de seguridad

**MacOs**

Para resolver este problema desde un Mac debes seguir los siguientes pasos:

- Entrar en "Preferencias de Sistema"

- Entrar en "Seguridad y Privacidad"

- Desde la pestaña "General" podrás dar permisos a **BeepBox**

## Crear un beep

Para crear un beep debemos ejecutar el siguiente comando:

``` bash
$ ./BeepBox --key qa020 --output ultrasound.wav
```

Esto nos generará un fichero llamado **ultrasound.wav** que al ejecutarlo contendrá un ultrasonido.

Este ultrasonido transporta el identificador que le hemos enviado al componente a través del parámetro --key, por lo que en este este caso el **Beep** transpotará el identificador **qa020**.

!!! info "Identificador"

    El identificador tiene que ser un **String** de **5 carácteres** que puede contener 
    cualquier **letra minúscula** o un **número**. El propio componente **no aceptará** otro
    tipo de formato por el momento.

## Links

Aquí te dejamos una serie de links relacionados con BeepBox:

- [Tutorial: Crea tu primer Beep](/tutorials/beeps/)

- [Compilar "Core System" de Beepbox](/components/core/)

## Frase

!!! quote "Buddha"
    Todo lo que somos es el resultado de lo que hemos pensado.
