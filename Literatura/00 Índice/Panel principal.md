---
tipo: índice
---
# 📚 Mi biblioteca literaria

## Leyendo ahora
```dataview
TABLE autor, año, inicio
FROM "02 Obras"
WHERE estado = "leyendo"
```

## Leídas
```dataview
TABLE autor, año, valoración, fin
FROM "02 Obras"
WHERE estado = "leído"
SORT fin DESC
```

## Pendientes
```dataview
LIST
FROM "02 Obras"
WHERE estado = "pendiente"
```

## Explorar
**Épocas:** [[Antigüedad clásica]] · [[Edad Media]] · [[Renacimiento y Siglo de Oro]] · [[Ilustración]] · [[Romanticismo]] · [[Realismo]] · [[Modernismo y vanguardias]] · [[Siglo XX]] · [[Contemporánea]]

**Géneros:** [[Novela]] · [[Poesía]] · [[Teatro]] · [[Cuento]] · [[Ensayo]] · [[Ejemplo]]  
## Todos los autores
```dataview
TABLE época, país, género
FROM "01 Autores"
SORT nacimiento ASC
```
