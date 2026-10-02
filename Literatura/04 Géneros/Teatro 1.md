---
tipo: género
---
# Terror Cósmico 
El horror cósmico es un subgénero literario y cinematográfico dónde el terror nace de comprender que el universo es vasto, antiguo y totalmente indiferente a la humanidad. 

## Características
- **Insignificancia humana:** Los seres humanos somos polvo sin importancia a escala cósmica.
- **Indiferencia absoluta:** Las entidades de este género no buscan destruirnos por malicia; simplemente no nos notan, igual que nosotros no notamos a las bacterias,
- **La locura como destino:** Intentar procesar la verdadera naturaleza de la realidad destruye la cordura del protagonista. 
- **Imposibilidad de vencer:** No existe arma plegaria ni tecnologías capaces de salvarnos; la lucha es inútil.

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
