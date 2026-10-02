---
tipo: género
---
# Novela
Narrativa extensa en prosa.

## Características
-

## Autores
```dataview
LIST
FROM "01 Autores"
WHERE contains(género, this.file.name)
SORT nacimiento ASC
```

## Obras
```dataview
TABLE autor, año, estado
FROM "02 Obras"
WHERE género = this.file.name
SORT año ASC
```
