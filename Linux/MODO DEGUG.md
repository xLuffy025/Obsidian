El modo debug (depuración) en un script de Bash es una funcionalidad que te permite ver exactamente qué está haciendo el script paso a paso. Es fundamental para identificar dónde falla tu código o por qué una variable no tiene el valor que esperabas.

La herramienta principal para esto es la opción -x (conocida como xtrace). Cuando activas esta opción, Bash imprime cada comando en la terminal (generalmente precedido por un signo +) justo antes de ejecutarlo, mostrando las variables ya expandidas y evaluadas.

Aquí te explico cómo funciona y las diferentes formas de utilizarlo:
1. Activar el debug al ejecutar el script
Si tienes un script y quieres ver todo su proceso de ejecución sin modificar el código fuente, puedes llamarlo directamente usando bash -x.
`bash -x mi_script.sh`

2. Activar el debug desde el Shebang
Si quieres que el script siempre se ejecute en modo debug, puedes añadir la opción -x en la primera línea del archivo (el shebang).

```bash
#!/bin/bash -x

echo "Iniciando proceso..."
variable="Hola Mundo"
echo $variable
```

3. Depurar solo una parte específica del script (set -x y set +x)
A menudo, los scripts son muy largos y no quieres ver el debug de todo, sino solo de una sección conflictiva. Puedes encender el modo debug con set -x y apagarlo con set +x.
```bash
#!/bin/bash

echo "Esta parte se ejecuta normal."

# Encendemos el modo debug
set -x 

resultado=$(( 5 + 5 ))
echo "El resultado es: $resultado"

# Apagamos el modo debug
set +x 

echo "El script vuelve a la normalidad."
```

Salida en la terminal:
```txt
Esta parte se ejecuta normal.
+ resultado=10
+ echo 'El resultado es: 10'
El resultado es: 10
+ set +x
El script vuelve a la normalidad.
```

(Nota cómo las líneas que empiezan con + te muestran lo que Bash está evaluando internamente).

Otras opciones útiles de depuración
Además de -x, hay otras banderas (flags) que los desarrolladores suelen combinar para crear scripts más robustos y fáciles de depurar:
 * -e (Exit on error): Detiene el script inmediatamente si algún comando falla (si devuelve un código de salida distinto a cero). Ideal para evitar que un error en cadena destruya tu sistema.
 * -u (Unbound variables): Detiene el script si intentas usar una variable que no ha sido definida previamente.
 * -v (Verbose): Imprime las líneas del script tal cual están escritas en el archivo antes de ejecutarlas (a diferencia de -x, que las muestra ya evaluadas).
El "Modo Estricto" de Bash:
Es una muy buena práctica poner esta línea al inicio de tus scripts para hacerlos más seguros y fáciles de depurar:
`set -euo pipefail`
