Las variables en programación son contenedores que almacenan datos. Las asignaciones permiten asignar un valor a una variable específica.

|Sintaxis|Descripción|Ejemplo de Uso|Qué hace el comando|
|---|---|---|---|
|`variable=valor`|Asigna un valor a una variable.|`nombre="Juan"`|Asigna el valor "Juan" a la variable `nombre`.|
|`$variable`|Accede al valor de una variable.|`echo $nombre`|Imprime el valor almacenado en la variable `nombre`.|
|`readonly`|Declara una variable como de solo lectura.|`readonly edad=30`|Declara la variable `edad` como de solo lectura con el valor 30.|
|`unset`|Elimina una variable.|`unset nombre`|Elimina la variable `nombre`.|
|`export`|Exporta una variable para que esté disponible en subprocesos.|`export PATH=/usr/bin`|Exporta la variable `PATH` para que esté disponible en subprocesos.|
|`$0`|Almacena el nombre del script o programa en ejecución.|`echo "Nombre del script: $0"`|Imprime el nombre del script o programa en ejecución.|
|`$1`, `$2`, ...|Almacenan los argumentos pasados a un script o función.|`echo "Primer argumento: $1"`|Imprime el primer argumento pasado al script o función.|
|`$#`|Almacena el número de argumentos pasados a un script o función.|`echo "Número de argumentos: $#"`|Imprime el número de argumentos pasados al script o función.|
|`$@`|Expande todos los argumentos pasados a un script o función.|`for arg in "$@"; do echo $arg; done`|Itera sobre todos los argumentos y los imprime uno por uno.|
|`$?`|Almacena el código de salida del comando más reciente.|`if [ $? -eq 0 ]; then echo "Éxito"; fi`|Verifica si el código de salida del comando anterior es igual a 0 y, en caso afirmativo, imprime "Éxito".|
|`$$`|Almacena el PID (identificador de proceso) del script actual.|`echo "PID del script: $$"`|Imprime el PID del script actual.|
|`$!`|Almacena el PID del último proceso en segundo plano.|`comando & echo "PID del proceso: $!"`|Ejecuta el comando en segundo plano y luego imprime el PID del proceso en segundo plano.|
|`$RANDOM`|Genera un número aleatorio.|`echo "Número aleatorio: $RANDOM"`|Genera un número aleatorio y lo imprime.|
## Variables con comandos asignados

| Variable   | Descripción                                     | Ejemplo de Asignación con Comando | Ejemplo de Uso                                        |
| ---------- | ----------------------------------------------- | --------------------------------- | ----------------------------------------------------- |
| `fecha`    | Almacena la fecha actual.                       | `fecha=$(date +%Y-%m-%d)`         | `echo "La fecha actual es: $fecha"`                   |
| `archivos` | Almacena la lista de archivos en un directorio. | `archivos=$(ls)`                  | `echo "Los archivos en el directorio son: $archivos"` |
| `contador` | Almacena el número de líneas de un archivo.     | `contador=$(wc -l archivo.txt     | awk '{print $1}')`                                    |