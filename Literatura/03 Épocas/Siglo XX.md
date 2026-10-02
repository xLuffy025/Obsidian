---
tipo: época
---
# Siglo XX
**La literatura del siglo XX** se caracterizó por una ==**ruptura radical con las normas tradicionales** del siglo XIX, reflejando un mundo fragmentado por las guerras mundiales, el colapso de los imperios y el nacimiento de la era tecnológica==. El concepto de la literatura dejó de ser el de un espejo claro de la realidad (Realismo) para convertirse en un espacio de **experimentación, introspección psicológica y cuestionamiento de la existencia**.

A grandes rasgos, la literatura de este siglo se entiende a través de tres grandes revoluciones:

---
Guerras, existencialismo, boom latinoamericano y nuevas narrativas.

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
