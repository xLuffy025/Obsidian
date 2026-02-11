El shell de Bash también se puede ejecutar **de forma no interactiva** desde un script, haciendo que el shell no requiera interacción humana. El comportamiento interactivo y el guionizado deberían ser idénticos, una consideración importante de diseño de Unix V7, shell Bourne y Bash transitivamente. Por lo tanto, cualquier cosa que se pueda hacer en la línea de comandos puede almacenarse en el archivo script para su reutilización.

_Sigue estos pasos para crear un script de  `Hola Mundo`_

1. Crea un nuevo archivo llamado `hola-mundo.sh`
```bash
touch hola-mundo.sh
```

2. Haga que el script sea ejecutable ejecutando `chmod +x hola-mundo.sh`
3. Añada este código
```bash 
#!/bin/bash
echo "Hola Mundo"
```

**Línea 1**: La primera línea del script debe comenzar con la secuencia de caracteres `#!`, denominado shebang[^1] 1. El shebang instruye al sistema operativo para que funcione `/bin/bash`, el shell de Bash, pasándole la ruta del scrip como argumento.

Por ejemplo `/bin/bash hola-mundo.sh`

**Línea 2**: Utiliza el comando `echo` para escribir en la salida estándar `Hola Mundo`

4. Ejecuta el script desde la línea de comandos usando uno de los siguientes funciones: `hola-mundo.sh`

-  `./hola-mundo.sh` - el más comúnmente utilizado y recomendado 
- `/bin/bash hola-mundo.sh`
- `bash hola-mundo.sh` - suponiendo que esté en tu `/bin $PATH`
- `sh hola-mundo.sh`

Para uso real en producción, omitir la extension (que es engañosa de todos modos, ya que es un script Bash, no un script) y quizás mover el archivo a un directorio dentro de tu `PATH` para que esté disponible independiente de tu directorio de trabajo actual, igual que un comando system como O . `.sh sh cat ls`

Los errores comunes incluyen:

1. Olvidar aplicar permisos de ejecución sobre el archivo, es decir, `chmod +x hola.mundo.sh`
la salida de ./hola-mundo.sh: Permiso denegado 

2. Editar el script en Windows, lo que produce caracteres de final de línea incorrectos que Bash no puede manejar 

- Un síntoma común es  cuando el retorno del carro a forzado el cursor al inicio de la línea, sobrescribiendo el texto antes de los puntos en el mensaje de error. `:comando no encontrado`

- El script puede arreglarse usando el programa. `dos2unix`

- Un ejemplo de uso: `dos2unix hola-mundo.sh
_dos2unix **edita el archivo en línea.**_

3. Usando, `sh ./hola-mundo.sh`, sin darte cuenta que `bash y sh` son shell distintas con características distintas  (aunque, dado que Bash es compatible hacia atrás, el error contrario es inofensivo)
- De todos modos, simplemente confiar en la línea shebang del script es mucho mas preferible a escribir escribir explícitamente `bash` o `sh`(o `python` o `perl` o `awk` o `ruby`...) antes del nombre de archivo de cada script.
- Una línea común para hacer tu escritura más portátil de usar `#!/bin/bash/env bash` en lugar de codificar fijamente una ruta hacia Bash. De esa manera, `/usr/bin/env` tiene que existir, pero más allá de ese punto, `bash`, solo tiene que estar en tu `PATH`. En muchos sistemas, `/bin/bash` no existe, y deberías usar alguna ruta absoluta; `/usr/bin/local/bin/bash` Esta cambio evita tener que averiguar los detalles de eso 


---




[^1]: También conocido como sha-bag, hashbang, pound-bang, hash-pling
