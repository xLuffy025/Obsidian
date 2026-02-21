El comando printf (Print Formatted) es una herramienta estándar de los sistemas tipo Unix para imprimir texto. A diferencia de echo, printf te da control absoluto sobre cómo se muestra la información, permitiéndote alinear texto, rellenar espacios, formatear números y procesar colores sin problemas de compatibilidad.

Es la opción preferida para scripts profesionales y funciona exactamente igual en cualquier entorno (Arch Linux, servidores Ubuntu, Termux, macOS, etc.).

## 🏗️ Sintaxis Básica
La filosofía de printf es separar el formato (la plantilla) de los datos (los argumentos).

``` bash
printf "FORMATO" argumento1 argumento2 ...
```

 * FORMATO: Una cadena de texto entre comillas que contiene el texto fijo y "comodines" (especificadores) que indican dónde y cómo irán los datos.
 * Argumentos: Las variables o textos que rellenarán esos comodines en orden.
   
Ejemplo básico:

```bash
printf "Mi nombre es %s y tengo %d años.\n" "Dimas" 25
# Salida: Mi nombre es Dimas y tengo 25 años.
```

>[!Nota] Nota:
>printf no añade un salto de línea automáticamente. Siempre debes incluir \n        al |final si quieres pasar a la siguiente línea).


## 🧩 Especificadores de Formato (Los "Comodines")

Estos son los símbolos que pones dentro de tu formato para que sean reemplazados por tus argumentos. Siempre empiezan con el signo de porcentaje (%)

| Especificador | ¿Para qué sirve?                                                                            | Ejemplo de uso                        | Resultado               |
| ------------- | ------------------------------------------------------------------------------------------- | ------------------------------------- | ----------------------- |
| %s            | Cadena de texto (String) normal.                                                            | `printf "Nota: %s\n" "ideas.md"`      | Nota: ideas.md          |
| %b            | Cadena que interpreta secuencia de escape (ideal para variables con colores como `\e[36m`). | `printf "%bTexto%b\n" "CYAN" "RESET"` | Texto _(en color cyan)_ |
| %d            | Número entero decimal.                                                                      | `printf "Total: %d\n" 42`             | Total:42                |
| %f            | Número decimal (flotante ).                                                                 | `printf "Peso: %f MB\n" 1.5`          | Peso:1.500000 MB        |
### 🪄 Modificadores de Formato (La Magia)

Aquí es donde printf brilla. Puedes poner números y signos entre el % y la letra del especificador para alterar cómo se muestra el dato.

**1. Rellenar números con ceros**
Muy útil para crear identificadores ordenados o nombrar archivos secuenciales.
 * Sintaxis: %0Nd (donde N es la cantidad total de dígitos).
<!-- end list -->
```bash
printf "ID de nota: %03d\n" 5
printf "ID de nota: %03d\n" 124
# Salida:
# ID de nota: 005
# ID de nota: 124
```

**2. Alinear texto y crear columnas (Tablas)**
Si le das un número a %s, printf reservará esa cantidad exacta de caracteres en la pantalla.
 * Número positivo (%20s): Alinea a la derecha.
 * Número negativo (%-20s): Alinea a la izquierda.
<!-- end list -->
```bash
# Alineación a la izquierda (-) y a la derecha (+)
printf "| %-15s | %10s |\n" "Título" "Tamaño"
printf "| %-15s | %10s |\n" "recetas.md" "12 KB"
printf "| %-15s | %10s |\n" "todo_list.md" "1 MB"

# Salida:
# | Título          |     Tamaño |
# | recetas.md      |      12 KB |
# | todo_list.md    |       1 MB |
```

**3. Limitar decimales**
Para el especificador %f, puedes usar .N para decir cuántos decimales quieres.

```bash
printf "Uso de CPU: %.2f%%\n" 45.6789
# Salida: Uso de CPU: 45.68%
```

### 🔤 Secuencias de Escape Comunes

Estos caracteres especiales se pueden usar dentro de la cadena de formato o al usar %b.

| Secuencia | Acción |
|---|---|
| \n | Nueva línea (Enter). Fundamental al final de casi cada printf. |
| \t | Tabulación (añade un espacio largo). |
| \e | Carácter de escape (se usa para iniciar códigos de color ANSI). |
| \\ | Imprime una barra invertida literal \. |
| %% | Imprime un signo de porcentaje literal %. |
### 🛠️ Ejemplos Prácticos para Scripts

**1. Imprimir mensajes con color de forma segura**

A diferencia de echo -e, esto nunca fallará sin importar dónde se ejecute el script.
```bash
ERROR="\e[31m"
RESET="\e[0m"

# Usamos %b para que printf entienda y aplique los códigos \e
printf "%b[ERROR]%b El archivo no existe.\n" "$ERROR" "$RESET"

2. Formatear un menú interactivo
Separar los colores de los números hace que el código sea mucho más limpio de leer.
CYAN="\e[36m"
RESET="\e[0m"

printf "%b1)%b Crear nueva nota\n" "$CYAN" "$RESET"
printf "%b2)%b Listar notas guardadas\n" "$CYAN" "$RESET"
```

**3. Reutilizar la plantilla automáticamente**

Un truco avanzado: Si le pasas más argumentos a printf de los que hay en tu plantilla, printf repetirá la plantilla en bucle hasta que se acaben los datos.

```bash
# La plantilla solo tiene un %s, pero le damos 3 palabras
printf "-> %s\n" "Manzana" "Pera" "Plátano"

# Salida:
# -> Manzana
# -> Pera
# -> Plátano
```
