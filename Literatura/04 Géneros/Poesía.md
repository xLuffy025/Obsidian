---
tipo: género
---
# Poesía
Verso, ritmo e imagen.

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
