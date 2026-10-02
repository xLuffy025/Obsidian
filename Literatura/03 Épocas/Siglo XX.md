---
tipo: época
---
# Siglo XX
**La literatura del siglo XX** se caracterizó por una ==**ruptura radical con las normas tradicionales** del siglo XIX, reflejando un mundo fragmentado por las guerras mundiales, el colapso de los imperios y el nacimiento de la era tecnológica==. El concepto de la literatura dejó de ser el de un espejo claro de la realidad (Realismo) para convertirse en un espacio de **experimentación, introspección psicológica y cuestionamiento de la existencia**.

A grandes rasgos, la literatura de este siglo se entiende a través de tres grandes revoluciones:

---
## 🚀 1. Las Tres Grandes Mutaciones Conceptuales

- **De la Realidad Externa al Caos Mental:** Ya no importaba narrar de forma ordenada lo que pasaba afuera, sino cómo el individuo procesaba el mundo. Se popularizó el **monólogo interior** y el "fluir de la conciencia" (escribir tal como se piensa, sin filtros ni orden lógico).
- **La Fragmentación del Tiempo:** El tiempo cronológico lineal lineal (inicio, nudo, desenlace) desapareció. Los autores comenzaron a mezclar pasado, presente y futuro de forma caótica, reflejando la teoría de la relatividad y la psicología de Freud.
- **El Lenguaje como Problema:** La literatura ya no buscaba ser "bella" o "educativa". El lenguaje se volvió un objeto de laboratorio: se rompieron las reglas de puntuación, se inventaron palabras y se cuestionó si las palabras realmente servían para comunicar algo real.

---

## 🎨 2. Etapas y Movimientos Clave

La literatura de este siglo se suele dividir en dos grandes mitades separadas por las Guerras Mundiales:

```
[1900 ————— 1940]                   [1945 ————— 1999]
   Vanguardismo / Modernismo           Posmodernismo / Existencialismo
   (Ruptura y Experimentación)         (Desencanto, Absurdo y Pluralidad)
```

Primera Mitad: Vanguardismo y Modernismo Literario (1900–1940)

- **La crisis de la razón:** Autores como **James Joyce**, **Virginia Woolf**, **Franz Kafka** y **Marcel Proust** redefinieron la novela. El arte debía perturbar y desafiar.
- **Las Vanguardias:** Surgieron movimientos agresivos que buscaban destruir el pasado estético: el _Surrealismo_ (el mundo de los sueños), el _Dadaísmo_ (el sinsentido) y el _Futurismo_ (la adoración a las máquinas y la velocidad).

Segunda Mitad: Posmodernidad, Absurdo y Compromiso (1945–1999)

- **El Existencialismo y el Absurdo:** Tras el Holocausto y la bomba atómica, la literatura adoptó un tono profundamente pesimista. Autores como **Albert Camus** y **Jean-Paul Sartre** plantearon que la vida no tiene un sentido intrínseco. El teatro del absurdo (Samuel Beckett) mostró la incomunicación humana.
- **El Boom Latinoamericano:** En los años 60 y 70, la literatura mundial se revolucionó con el **Realismo Mágico** de autores como **Gabriel García Márquez** y **Julio Cortázar**, demostrando que lo fantástico y lo real podían convivir en la cotidianidad de un continente herido.
- **La Posmodernidad:** Hacia finales de siglo, la literatura se volvió metanarrativa (historias que hablan sobre el arte de escribir historias), mezclando la cultura de masas (cómics, cine, publicidad) con la alta literatura.

---

## 📊 Comparativa: Novela del Siglo XIX vs. Novela del Siglo XX

|Elemento|Novela del Siglo XIX (Realismo)|Novela del Siglo XX (Modernismo/Vanguardia)|
|---|---|---|
|**Narrador**|Omnisciente (un "Dios" que lo sabe todo y juzga).|Múltiple, poco fiable, limitado o fragmentado.|
|**Estructura**|Lineal y cronológica (ordenada).|No lineal, saltos temporales, rompecabezas.|
|**Objetivo**|Retratar la sociedad y educar moralmente.|Explorar la mente humana y cuestionar la realidad.|
|**El Héroe**|Personajes con metas claras (triunfar, casarse).|El **antihéroe**: alienado, confundido o marginado.|

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
