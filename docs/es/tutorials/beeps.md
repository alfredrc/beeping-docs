# Crear un beep

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/tutorials/beeps/) | [Español](https://docs-es.beeping.io/tutorials/beeps/)

## Introducción

**Beepbox** es el componente de **Beeping** que tiene como finalidad encriptar datos dentro de un fichero de audio. Este fichero de audio ( como se ha explicado anteriormente ) lo llamamos **Beep**.

## Step by Step

A continuación os dejamos los pasos que debes seguir para crear vuestro primer **beep**.

!!! info "Beepbox"

    Por ahora **BeepBox** sólo es compatible con MacOs
    

Lo primero que debemos hacer es descargar el binario:

- [Beepbox para MacOs](https://github.com/beeping-io/beepbox/releases/download/1.0.0/BeepBox-MacOs.zip)

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

## Solución de problemas

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

- [Components: BeepBox](/components/beepbox/)

- [Compilar "Core System" para Beepbox](/components/core/)

## Frase

!!! quote "Tim Berners-Lee"
    La Web como la imaginé, todavía no la hemos visto. El futuro sigue siendo mucho más grande que el pasado.
    
