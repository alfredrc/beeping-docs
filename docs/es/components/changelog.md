# Changelog

## Idiomas

> Esta página se puede leer en los siguiente idiomas:
>  
> [Inglés](https://docs.beeping.io/components/changelog/) | [Español](https://docs-es.beeping.io/components/changelog/)

## Introducción

En este documento se hace un repaso de todo el historial de **versiones** de cada uno de los componentes de **Beeping**.


!!! info "Nota"

    Los componentes que no aparecen en este
    documento es porque no tienen todavía historial,
    es decir, son componentes que sólo tienen una
    sola versión.

## BeepBox

### Versión 1.1.0

Se añaden nuevos parámetros:

---

**Nombre**: --mode [0|1|2|3]

**Descripción**: Beeping Mode

**Opcional**: SI

**Valor por defecto**: 2

| Nombre       | Valor    | Descripción   |
| :--------- | :------:  | :------: |
| **mode**    | 0 | Modo audible  |
| **mode**    | 1 | Modo hidden  |
| **mode**    | 2 | Modo non-audible  |
| **mode**    | 3 | Modo custom  |        

---

**Nombre**: --duration secs

**Descripción**: Duration of output file in seconds (>=5.1)

**Opcional**: SI

**Valor por defecto**: 5.1

| Nombre       | Valor    | Descripción   |
| :--------- | :------:  | :------: |
| **duration**    | seconds (>=5.1) | Duration of output file in seconds  |

---

**Nombre**: --interval secs

**Descripción**:  Interval in seconds between two audio marks (>=2.5)

**Opcional**: SI

**Valor por defecto**: 2.5

| Nombre       | Valor    | Descripción   |
| :--------- | :------:  | :------: |
| **interval**    | seconds (>=2.5) | Interval in seconds (>=2.5) between two audio marks |

### Versión 1.0.0

- Versión inicial

## Frase

!!! quote "Buddha"
    All that we are is the result of what we have thought.