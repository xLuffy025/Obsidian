---
tipo: época
---
# Antigüedad clásica
Grecia y Roma: epopeya, tragedia y los cimientos de la tradición occidental.

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
