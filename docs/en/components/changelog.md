# Changelog

## Languages

> This page can be read in the following languages:
>  
> [English](https://docs.beeping.io/components/changelog/) | [Spanish](https://docs-es.beeping.io/components/changelog/)

## Introduction

This document reviews the entire **version** history of each of the **Beeping** components.

!!! info "Note"

    Components not listed in this
    document is because they don't have a history yet,
    that is, they are components that only have one
    single version.

## BeepBox

### Version 1.1.0

New parameters are added:

---

**Name**: --mode [0|1|2|3]

**Description**: Beeping Mode

**Optional**: YES

**Default Value**: 2

| Name       | Value    | Description   |
| :--------- | :------:  | :------: |
| **mode**    | 0 | Audible mode  |
| **mode**    | 1 | Hidden  mode  |
| **mode**    | 2 | Non-Audible  mode |
| **mode**    | 3 | Custom  mode |

---

**Name**: --duration secs

**Description**: Duration of output file in seconds (>=5.1)

**Optional**: YES

**Default Value**: 5.1

| Name       | Value    | Description   |
| :--------- | :------:  | :------: |
| **duration**    | seconds (>=5.1) | Duration of output file in seconds  |

---

**Name**: --interval secs

**Description**:  Interval in seconds between two audio marks (>=2.5)

**Optional**: YES

**Default Value**: 2.5

| Name       | Value    | Description   |
| :--------- | :------:  | :------: |
| **interval**    | seconds (>=2.5) | Interval in seconds (>=2.5) between two audio marks |

### Version 1.0.0

- Initial version 

## Quote

!!! quote "Buddha"
    All that we are is the result of what we have thought.
