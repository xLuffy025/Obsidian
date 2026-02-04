## Párrafos 

Para crear párrafos en Markdown, usa una **línea en blanco** para separar los bloques de texto. Cada bloque de texto separado por una línea en blanco se trata como un párrafo distinto.

```md
This is a paragraph.

This is another paragraph.
```

Esto es un párrafo.

Este es otro párrafo.

Una línea en blanco entre líneas de texto crea párrafos separados. Este es el comportamiento por defecto en Markdown.

>[!tip] Espacios en blanco múltiples

### Interrupciones de línea 

Por defecto en Obsidian, pulsar una vez crea una nueva línea en tu nota, pero esto se trata como una _continuación_ del mismo párrafo en la salida renderizada, siguiendo el comportamiento típico de Markdown. Para insertar un salto _de línea dentro_ de un párrafo sin empezar uno nuevo, puedes hacerlo:`Enter`

- Añade **dos espacios** al final de una línea antes de pulsar , o`Enter`
- Usa el acceso directo para insertar directamente un salto de línea.`Shift+Enter`
>[!question] ¿Por qué no crean múltiples pulsaciones más saltos de línea en la  vista de lectura?`Enter`
>
>En Markdown, se ignora una sola y varias pulsaciones consecutivas resultan en un solo párrafo nuevo. Este comportamiento se alinea con la regla de envolver suavemente de Markdown, donde las líneas en blanco adicionales no generan saltos de línea o párrafos adicionales; se comprimen en un solo salto de párrafo. Así es como Markdown gestiona el texto por defecto, asegurando que los párrafos fluyan de forma natural sin interrupciones inesperadas.`Enter``Enter`

Obsidian incluye una configuración **[de saltos de línea estrictos](https://help.obsidian.md/settings#Strict%20line%20breaks)**, que hace que Obsidian siga la especificación estándar de Markdown para saltos de línea.

Para habilitar esta función:

1. **[Abrir Configuración](https://help.obsidian.md/settings)**.
2. Ve a la pestaña **Editor**.
3. Activa **saltos de línea estrictos**.

Cuando se habilita **el Strict Line Breaks** en Obsidian, los saltos de línea tienen tres comportamientos distintos dependiendo de cómo se separen las líneas:

**Retorno único sin espacios**: Un solo sin espacios finales combinará las dos líneas separadas en una sola línea cuando se renderice.`Enter`

```md
line one
line two
```

Se representa como:

línea uno línea dos

**Retorno único con dos o más espacios finales**: Si añades dos o más espacios al final de la primera línea antes de pulsar , las dos líneas permanecen como parte del mismo párrafo, pero se rompen por un salto de línea (elemento HTML). Usaremos dos guiones bajos para sustituir los espacios en este ejemplo.`Enter``<br>`

```md
line three__  
line four
```

Se representa como:

Línea Tres  
  
Línea Cuatro

**Doble retorno (con o sin espacios finales):** Pulsar dos veces (o más) separa las líneas en dos párrafos distintos (elementos HTML), independientemente de si añades espacios al final de la primera línea.`Enter``<p>`

```md
line five

line six
```

Se representa como:

Línea cinco

Línea seis

## Encabezados 
---
Para crear un encabezado, añade hasta seis símbolos antes del texto del encabezado. El número de símbolos determina el nivel del encabezado (como se muestra en el [Esquema](https://help.obsidian.md/plugins/outline)).`#``#`

```md
# This is a heading 1
## This is a heading 2
### This is a heading 3
#### This is a heading 4
##### This is a heading 5
###### This is a heading 6
```

# Esto es un encabezado 1

## Esto es un encabezado 2

### Esto es un encabezado 3

#### Esto es un encabezado 4

##### Esto es un encabezado 5

###### Esto es un encabezado 6

## Negrita, cursiva, resaltados 

El formato de texto también puede aplicarse usando [atajos de edición](https://help.obsidian.md/editing-shortcuts).

| Estilo                    | Sintaxis              | Ejemplo                                  | Producción                                        |
| ------------------------- | --------------------- | ---------------------------------------- | ------------------------------------------------- |
| Audaz                     | `** **` o `__ __`     | `**Bold text**`                          | **Texto en negrita**                              |
| Cursiva                   | `* *` o `_ _`         | `*Italic text*`                          | _Texto cursivo_                                   |
| Tachado                   | `~~ ~~`               | `~~Striked out text~~`                   | ~~Texto tachado~~                                 |
| Aspectos destacados       | `== ==`               | `==Highlighted text==`                   | ==Texto resaltado==                               |
| Negrita y cursiva anidada | `** **` y `_ _`       | `**Bold text and _nested italic_ text**` | **Texto en negrita y texto _en cursiva anidado_** |
| Negrita y ursiva          | `*** ***` o `___ ___` | `***Bold and italic text***`             | **_Texto en negrita y cursiva_**                  |
El formato puede verse forzado a mostrarse en texto plano añadiendo una barra diagonal delante.`\`

**Esta frase no será atrevida**

```markdown
\*\*This line will not be bold\*\*
```

*_Esta línea estará en cursiva y mostrará los asteriscos_*

```markdown
\**This line will be italic and show the asterisks*\*
```

## Enlaces internos 

Obsidian soporta dos formatos para [enlaces internos](https://help.obsidian.md/links) entre notas:

- Wikienlace: `[[Three laws of motion]]`
- Descuento: `[Three laws of motion](Three%20laws%20of%20motion.md)`

## Enlaces externos 

Si quieres enlazar a una URL externa, puedes crear un enlace en línea rodeando el texto del enlace con corchetes (), y luego la URL entre paréntesis ().`[ ]``( )`

```md
[Obsidian Help](https://help.obsidian.md)
```

[Obsidian Help](https://help.obsidian.md/)

También puedes crear enlaces externos a archivos en otros archivos, enlazando a un [URI de Obsidian](https://help.obsidian.md/uri).

```md
[Note](obsidian://open?vault=MainVault&file=Note.md)
```

### Escape de espacios en blanco en los enlaces 

Si tu URL contiene espacios en blanco, debes salir de ellos reemplazándolos por .`%20`

```md
[My Note](obsidian://open?vault=MainVault&file=My%20Note.md)
```

También puedes escapar de la URL envolviéndola con corchetes angulados ().`< >`

```md
[My Note](<obsidian://open?vault=MainVault&file=My Note.md>)
```

## Imágenes externas 

Puedes añadir imágenes con URLs externas, añadiendo un símbolo antes de un [enlace externo](https://help.obsidian.md/syntax#External%20links).`!`

```md
![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

![Engelbart](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)

Puedes cambiar las dimensiones de la imagen añadiendo al destino del enlace, donde 640 es el ancho y 480 es la altura.`|640x480`

```md
![Engelbart|100x145](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

Si solo especificas el ancho, la imagen escala según su relación de aspecto original. Por ejemplo:

```md
![Engelbart|100](https://history-computer.com/ModernComputer/Basis/images/Engelbart.jpg)
```

>[!tip] Propina
>Si quieres añadir una imagen desde dentro de tu bóveda, también puedes [incrustar una imagen en una nota](https://help.obsidian.md/embeds#Embed%20an%20image%20in%20a%20note).

## Presupuestos 

Puedes citar el texto añadiendo un símbolo antes del texto.`>`

```md
> Human beings face ever more complex and urgent problems, and their effectiveness in dealing with these problems is a matter that is critical to the stability and continued progress of society.

\- Doug Engelbart, 1961
```

> Los seres humanos se enfrentan a problemas cada vez más complejos y urgentes, y su eficacia para afrontar estos problemas es un asunto fundamental para la estabilidad y el progreso continuo de la sociedad.

- Doug Engelbart, 1961

>[!tip] 
>Puedes convertir tu presupuesto en una [señal](https://help.obsidian.md/callouts) añadiéndola como primera línea en la cita.`[!info]`

## Listas 

Puedes crear una lista no ordenada añadiendo un , , o antes del texto.`-``*``+`

```md
- First list item
- Second list item
- Third list item
```

- Primer ítem de la lista
- Segundo ítem de la lista
- Tercer punto de la lista

Para crear una lista ordenada, comienza cada línea con un número seguido de un símbolo de una o.`.``)`

```md
1. First list item
2. Second list item
3. Third list item
```

1. Primer ítem de la lista
2. Segundo ítem de la lista
3. Tercer punto de la lista

```md
1) First list item
2) Second list item
3) Third list item
```

1. Primer ítem de la lista
2. Segundo ítem de la lista
3. Tercer punto de la lista

Puedes usarla para insertar un [salto de línea](https://help.obsidian.md/syntax#Line%20breaks) dentro de una lista ordenada sin alterar la numeración.`Shift+Enter`

```md
1. First list item
   
2. Second list item
3. Third list item
   
4. Fourth list item
5. Fifth list item
6. Sixth list item
```

### Listas de tareas 

Para crear una lista de tareas, comienza cada elemento de la lista con un guion y un espacio seguido de .`[ ]`

```md
- [x] This is a completed task.
- [ ] This is an incomplete task.
```

- [x] Esta es una tarea completada.
- [ ] Esta es una tarea incompleta.

Puedes activar una tarea en la vista de Lectura seleccionando la casilla.

>[!tip]
>Puedes usar cualquier personaje dentro de los corchetes para marcarlo como completo.
>```md
>- [x] Milk
>- [x] Eggs
>- [ ] Eggs
>```
>- [x] Leche
>- [x] Eggs
>- [x] Eggs
>


### Listas de anidación 

Puedes anidar cualquier tipo de lista—ordenada, no ordenada o listas de tareas—bajo cualquier otro tipo de lista.

Para crear una lista anidada, indenta uno o más elementos de la lista. Puedes mezclar tipos de lista dentro de una estructura anidada:

```md
1. First list item
   2. Ordered nested list item
3. Second list item
   - Unordered nested list item
```

1. Primer ítem de la lista
    1. Elemento ordenado de lista anidada
2. Segundo ítem de la lista
    - Elemento de lista anidada sin ordenar

De manera similar, puedes crear una lista de tareas anidada indentando uno o más elementos de la lista:

```md
- [ ] Task item 1
	- [ ] Subtask 1
- [ ] Task item 2
	- [ ] Subtask 1
```

- [ ] Punto de tarea 1
    - [ ] Subtarea 1
- [ ] Punto de tarea 2
    - [ ] Subtarea 1

Utiliza o para sangar o no insangar los elementos seleccionados de la lista para organizarlos fácilmente.`Tab``Shift+Tab`

## Regla horizontal 

Puedes usar tres o más estrellas, guiones o guiones bajos en su propia línea para añadir una barra horizontal. También puedes separar símbolos usando espacios.`***``---``___`

```md
***
****
* * *
---
----
- - -
___
____
_ _ _
```

---

## Código 

Puedes formatear el código tanto en línea dentro de una frase, como en un bloque propio.

### Código en línea 

Puedes formatear código dentro de una frase usando backticks individuales.

```md
Text inside `backticks` on a line will be formatted like code.
```

El texto dentro de una línea estará formateado como código.`backticks`

Si quieres poner backticks en un bloque de código inline, rodéalo con backticks dobles así: inline .``code with a backtick ` inside``

### Bloques de código 

Para formatear el código como bloque, enciérralo con tres backticks o tres tildes.

``````
`````
cd ~/Desktop
`````
``````

```
~~~
cd ~/Desktop
~~~
```

```md
cd ~/Desktop
```

También puedes crear un bloque de código sangrando el texto con 4 espacios en blanco.`Tab`

```md
    cd ~/Desktop
```

Puedes añadir resaltado de sintaxis a un bloque de código, añadiendo un código de lenguaje tras el primer conjunto de retrocesos.

``````md
`````js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
`````
``````

```js
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

Obsidian utiliza Prism para resaltar la sintaxis. Para más información, consulte [Lenguas soportadas](https://prismjs.com/#supported-languages).

PrismJS y vistas de edición

[El modo fuente](https://help.obsidian.md/edit-and-read#Source%20mode) y [la Vista Previa en Vivo](https://help.obsidian.md/edit-and-read#Live%20Preview) no soportan PrismJS y pueden renderizar el resaltado de sintaxis de forma diferente.

#### Bloques de código anidados 

Cuando necesitas incluir un bloque de código dentro de otro bloque de código (por ejemplo, al documentar cómo usar bloques de código), puedes usar más de tres backticks o tildes para el bloque de código exterior.

Para anidar bloques de código, utiliza cuatro o más backticks (o tildes) para el bloque exterior, mientras que el bloque interior usa tres:

`````md
````md
Here's how to create a code block:
```js
console.log("Hello world")
```
````
`````

También puedes mezclar backticks y tildes. Esto es especialmente útil cuando se trabaja con código que genera otros bloques de código:

`````md
````md
```dataviewjs
dv.paragraph(`
~~~mermaid
graph TD
    A --> B
~~~
`)
```
````
`````

El principio clave es que el bloque de código exterior debe usar **más** caracteres de cerca (backticks o tildes) que cualquier bloque de código interior, o usar un tipo de carácter de cerca diferente.

## Notas 

Puedes añadir notas [al pie[1]](https://publish.obsidian.md/#fn-1-1796f3de432141fb) a tus notas usando la siguiente sintaxis:

```md
This is a simple footnote[^1].

[^1]: This is the referenced text.
[^2]: Add 2 spaces at the start of each new line.
  This lets you write footnotes that span multiple lines.
[^note]: Named footnotes still appear as numbers, but can make it easier to identify and link references.
```

También puedes incluir notas al pie en una frase. Ten en cuenta que el caret va fuera de los brackets.

```md
You can also use inline footnotes. ^[This is an inline footnote.]
```

Nota

Las notas al pie en línea solo funcionan en vista de lectura, no en Vista Previa en Vivo.

## Comentarios 

Puedes añadir comentarios envolviendo el texto con . Los comentarios solo son visibles en la vista de Edición.`%%`

```md
This is an %%inline%% comment.

%%
This is a block comment.

Block comments can span multiple lines.
%%
```

## Escapando de la sintaxis de Markdown 

En algunos casos, puede que necesites mostrar caracteres especiales en Markdown, como , , o , sin activar su formato. Para mostrar estos caracteres literalmente, coloca una barra diagonal () delante de ellos.`*``_``#``\`

Personajes comunes para escapar

- Asterisco: `\*`
- Subrayado: `\_`
- Hashtag: `\#`
- Backtick: `` \` ``
- Tubería (usada en tablas): `\|`
- Tilde: `\~`

```md
\*This text will not be italicized\*.
```

*Este texto no estará en cursiva*.

Al trabajar con listas numeradas, puede que necesites evitar el periodo posterior al número para evitar el formato automático de listas. Coloca la barra diagonal () antes del punto, **no** antes del número.`\`

```md
1\. This won't be a list item.
```

1. Esto no será un punto de lista.

## Aprende más 

Para aprender una sintaxis de formato más avanzada, como tablas, diagramas y expresiones matemáticas, consulta la [sintaxis de formato avanzada](https://help.obsidian.md/advanced-syntax).

Para saber más sobre cómo Obsidian analiza Markdown, consulta [Obsidian Flavored Markdown](https://help.obsidian.md/obsidian-flavored-markdown).

---

1. Esto es una nota al pie.[↩︎](https://publish.obsidian.md/#fnref-1-1796f3de432141fb)