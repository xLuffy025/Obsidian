## Condicionales de Archivo

| Expresión | Valor     | ¿Qué hace?                                                           |
| --------- | --------- | -------------------------------------------------------------------- |
| `-a`      | `archivo` | Si el archivo existe.                                                |
| `-b`      | `archivo` | Si el archivo existe y es un archivo especial de bloque.             |
| `-c`      | `archivo` | Si el archivo existe y es un archivo especial de carácter.           |
| `-d`      | `archivo` | Si el archivo existe y es un directorio.                             |
| `-e`      | `archivo` | Si el archivo existe.                                                |
| `-f`      | `archivo` | Si el archivo existe y es un archivo regular.                        |
| `-g`      | `archivo` | Si el archivo existe y tiene el bit de grupo establecido.            |
| `-h`      | `archivo` | Si el archivo existe y es un enlace simbólico.                       |
| `-k`      | `archivo` | Si el archivo existe y tiene el bit de pegajosidad establecido.      |
| `-p`      | `archivo` | Si el archivo existe y es una tubería con nombre (_FIFO_).           |
| `-r`      | `archivo` | Si el archivo existe y es legible.                                   |
| `-s`      | `archivo` | Si el archivo existe y su tamaño es mayor que cero.                  |
| `-t`      | `fd`      | Si el descriptor de archivo está abierto y se refiere a un terminal. |
| `-u`      | `archivo` | Si el archivo existe y tiene el bit de usuario establecido.          |
| `-w`      | `archivo` | Si el archivo existe y es escribible.                                |
| `-x`      | `archivo` | Si el archivo existe y es ejecutable.                                |
| `-G`      | `archivo` | Si el archivo existe y es propiedad del ID de grupo efectivo.        |
| `-L`      | `archivo` | Si el archivo existe y es un enlace simbólico.                       |
| `-N`      | `archivo` | Si el archivo existe y ha sido modificado desde la última lectura.   |
| `-O`      | `archivo` | Si el archivo existe y es propiedad del ID de usuario efectivo.      |
| `-S`      | `archivo` | Si el archivo existe y es un socket.                                 |
## Comparaciones de Archivos

|Expresión|¿Qué hace?|
|---|---|
|`archivo -ef archivo2`|Si ambos archivos se refieren al mismo inode y números de dispositivo.|
|`archivo -nt archivo2`|Si `archivo` es más nuevo que `archivo2` (_usa el tiempo de modificación_) o si `archivo` existe y `archivo2` no.|
|`archivo -ot archivo2`|Si `archivo` es más antiguo que `archivo2` (_usa el tiempo de modificación_) o si `archivo2` existe y `archivo` no.|

## Condicionales de Variable

| Expresión | Valor | ¿Qué hace?                                  |
| --------- | ----- | ------------------------------------------- |
| `-o`      | `opt` | Si la opción del shell está habilitada.     |
| `-v`      | `var` | Si la variable tiene un valor asignado.     |
| `-R`      | `var` | Si la variable es una referencia de nombre. |
| `-z`      | `var` | Si la longitud de la cadena es cero.        |
| `-n`      | `var` | Si la longitud de la cadena no es cero.     |
## Comparaciones de Variables

|Expresión|¿Qué hace?|
|---|---|
|`var = var2`|Igual a.|
|`var == var2`|Igual a (_sinónimo de `=`_).|
|`var != var2`|No igual a.|
|`var < var2`|Menor que (_en orden alfabético ASCII_).|
|`var > var2`|Mayor que (_en orden alfabético ASCII_).|
# OPERADORES ARITMÉTICOS
## Asignación
|Operadores|¿Qué hace?|
|---|---|
|`=`|Inicializa o cambia el valor de una variable.|
## Aritméticos
|Operadores|¿Qué hace?|
|---|---|
|`+`|Adición|
|`-`|Sustracción|
|`*`|Multiplicación|
|`/`|División|
|`**`|Exponenciación|
|`%`|Módulo|
|`+=`|Más-igual (_Incrementa una variable._)|
|`-=`|Menos-igual (_Decrementa una variable._)|
|`*=`|Por-igual (_Multiplica una variable._)|
|`/=`|Dividido-igual (_Divide una variable._)|
|`%=`|Módulo-igual (_Resto de dividir una variable._)|
## Bitwise

|Operadores|¿Qué hace?|
|---|---|
|`<<`|Desplazamiento a la izquierda a nivel de bits|
|`<<=`|Desplazamiento a la izquierda-igual|
|`>>`|Desplazamiento a la derecha a nivel de bits|
|`>>=`|Desplazamiento a la derecha-igual|
|`&`|AND a nivel de bits|
|`&=`|AND a nivel de bits-igual|
|`\|`|OR a nivel de bits|
|`\|=`|OR a nivel de bits-igual|
|`~`|NOT a nivel de bits|
|`^`|XOR a nivel de bits|
|`^=`|XOR a nivel de bits-igual|
## Lógicos
| Operadores | ¿Qué hace? |
| ---------- | ---------- |
| `!`        | NOT        |
| `&&`       | AND        |
| `\|`       | OR         |

>[!exemple]

|Comando/Expresión|Descripción|Ejemplo de Uso|Qué hace el comando|
|---|---|---|---|
|`[[ -d <directorio> ]]`|Verifica si `<directorio>` existe y es un directorio.|`if [[ -d $dir ]]; then echo "El directorio existe."; fi`|Verifica si el directorio `$dir` existe y, en caso afirmativo, imprime "El directorio existe.".|
|`[[ -f <archivo> ]]`|Verifica si `<archivo>` existe y es un archivo regular.|`if [[ -f $file ]]; then echo "El archivo existe."; fi`|Verifica si el archivo `$file` existe y, en caso afirmativo, imprime "El archivo existe.".|
|`[[ -e <ruta> ]]`|Verifica si `<ruta>` existe (archivo o directorio).|`if [[ -e $path ]]; then echo "La ruta existe."; fi`|Verifica si la ruta `$path` existe y, en caso afirmativo, imprime "La ruta existe.".|
|`[[ -r <archivo> ]]`|Verifica si `<archivo>` tiene permisos de lectura.|`if [[ -r $file ]]; then echo "El archivo es legible."; fi`|Verifica si el archivo `$file` tiene permisos de lectura y, en caso afirmativo, imprime "El archivo es legible.".|
|`[[ -w <archivo> ]]`|Verifica si `<archivo>` tiene permisos de escritura.|`if [[ -w $file ]]; then echo "El archivo es escribible."; fi`|Verifica si el archivo `$file` tiene permisos de escritura y, en caso afirmativo, imprime "El archivo es escribible.".|
|`[[ -x <archivo> ]]`|Verifica si `<archivo>` tiene permisos de ejecución.|`if [[ -x $file ]]; then echo "El archivo es ejecutable."; fi`|Verifica si el archivo `$file` tiene permisos de ejecución y, en caso afirmativo, imprime "El archivo es ejecutable.".|
|`[[ -s <archivo> ]]`|Verifica si `<archivo>` existe y no está vacío.|`if [[ -s $file ]]; then echo "El archivo no está vacío."; fi`|Verifica si el archivo `$file` existe y no está vacío, y en caso afirmativo, imprime "El archivo no está vacío.".|
