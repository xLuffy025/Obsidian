Crea un nuevo archivo llamado `hola.sh` con el siguiente contenido y dale permisos de ejecutables con `chmod +x hola.sh`

Ejecutar/ejecutar via: `./hola.sh`
```bash
#!/ust/bin/env bash

# Ten en cuenta que no se pueden usar espacios al rededor del perador de asignacion '='
whom_variable="Mundo"

# usa printf para generar los datos de forma segura 
printf "Hola %s/n" "$whom_variable"
#> Hola, Mundo
```

Esto imprimirá a la salida estándar cuando se ejecuten. `Hola Mundo`

para indicar a bash donde esta el script necesitas ser muy especifico, apuntando el directorio que contiene, normalmente `./` si esta en tu directorio de trabajo, donde `.` es un alias del directorio actual. Si no especificas el directorio, `bash` intenta localizar el script en uno de los directorios contenidos en la variable de entorno.

---
El siguiente código acepta un argumento `$1`, que es el primero de la línea de comandos, y lo genera en una cadena formateada siguiendo `Hola`

Ejecuta/ejecuta vía: `./hola.sh Mundo`

```bash 
#!/usr/bin/env bash
printf "Hola, %s/n" "$1"
#>Hola, Mundo
```

Es importante señalar que `$1` debe citarse entre comillas dobles, no entre comillas simples `"$1"`. Expande hasta el primer argumento de la línea de comandos, según se desee, mientras `'$1'` evalúa a la cadena literal `$1`.

>[!nota] Nota de seguridad:
>Lee **implicaciones de seguridad de olvidar citar una variable en los bash shells** para entender la importancia de colocar el texto de la variable entre comillas dobles.




