# Documentación

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/community/documentation) | [Español](https://docs-es.beeping.io/community/documentation)

## Introducción

Este sistema documental también es **Open Source**.

Esto siginifica que puedes aportar en lo que a la documentación se refiere, tanto si encientra errores de comunicación, como arrancar la escritura de la documentación en una nueva lengua. Como siempre decimos como vosotros veáis más conveniente contribuir.

Esta documentación se ha creado con el tool **Mkdocs** y con la plantilla **Material for MkDocs**.

## Empezar

Para contribuir en la documetación del proyecto lo primero que debemos hacer es tener instalado el proyecto documental en nuestro ordenador siguiendo los pasos del apartado [Rules](/community/rules) hasta que hayamos hecho un clone del repositorio en nuestro ordenador.

## Dependencias

Para poder ejecutar esta documentación en nuestro ordenador debemos seguir los siguiente pasos:

!!! info "Python"

    Para realizar la instalación necesitas tener instalado **Python** 
    en tu Mac. En el caso de que no lo tengas 
    instalado, puedes ver cómo se instala en la
    siguiente página web: https://www.python.org/    

- Instalar **Mkdocs**

``` bash
$ pip install mkdocs
```

- Instalar **Material for MkDocs**

``` bash
$ pip install mkdocs-material
```

## Lenguaje

La documentación está escrita en distintas lenguas. 

La disponibilidad de las lenguas las definen los ficheros mkdocs-xx.yml

En el caso de que queramos trabajar con la lengua castellana debemos hacer lo siguiente:

``` bash
$ rm mkdocs.yml
$ ln -s mkdocs-es.yml mkdocs.yml
```

En el caso de que queramos trabajar con la lengua inglesa debemos hacer lo siguiente:

``` bash
$ rm mkdocs.yml
$ ln -s mkdocs-en.yml mkdocs.yml
```

## Start

Para arrancar la web documental en nuestro ordenador solo necesitamos ejecutar el siguiente comando:

``` bash
$ mkdocs serve
```
Ahora podremos acceder a la documentación desde nuestro navegador a través de la dirección: http://127.0.0.1:8000

## Frase

!!! quote "Victor Hugo"
    La vida es una flor de la que el amor es la miel.

