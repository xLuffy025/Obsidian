---
tipo: época
---
# Contemporánea
Literatura global desde finales del siglo XX hasta hoy.

## Contexto histórico y rasgos
-

## Autores
```dataview
TABLE país, género, nacimiento
FROM "01 Autores"
WHERE época = this.file.link
SORT nacimiento ASC
```

## Obras
```dataview
TABLE autor, año, estado
FROM "02 Obras"
WHERE contains(string(época), this.file.name)
SORT año ASC
```
