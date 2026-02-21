
El Modo Estricto en Bash: `set -euo pipefail`
Por defecto, Bash es muy permisivo: si un comando falla o una variable no existe, simplemente ignora el error y continúa ejecutando la siguiente línea. Esto puede ser catastrófico (por ejemplo, borrar archivos en el directorio equivocado).
Para evitarlo, los scripts profesionales o "robustos" siempre inician activando el Modo Estricto. Es como ponerle un cinturón de seguridad al código.

```bash
#!/usr/bin/env bash
set -euo pipefail
```

Desglose de cada letra
1. set -e (Exit on error / Falla rápido)
Detiene el script inmediatamente si cualquier comando devuelve un código de error (distinto de cero).
 * El problema sin -e: Si escribes cd /carpeta_inexistente y luego rm -rf *, Bash fallará al cambiar de carpeta, pero sí ejecutará el borrado en tu carpeta actual.
 * La solución: Con -e, el script muere en el cd y te salva de un desastre.
 * Cómo evadirlo intencionalmente: Si sabes que un comando puede fallar y no quieres que el script se detenga, añade || true.
```bash
# El script no se detendrá aunque grep no encuentre la palabra
cat archivo.txt | grep "palabra_rara" || true
```

2. set -u (Unbound variables / Variables no definidas)
Detiene el script si intentas leer una variable que no ha sido declarada previamente.
 * El problema sin -u: Si quieres borrar rm -rf /$DIRECTORIO pero escribiste mal la variable o está vacía, Bash leerá rm -rf / (borrando la raíz del sistema).
 * La solución: Con -u, Bash arroja el error unbound variable y aborta. (Este fue el error que detuvo la ejecución al intentar evaluar DEBUG antes de definirlo).
 * Cómo evadirlo intencionalmente: Usa la sintaxis de expansión con valor por defecto ${VARIABLE:-valor_por_defecto}.
```bash
# Si DEBUG no existe, asume que es 0 en lugar de crashear
DEBUG="${DEBUG:-0}" 
```

3. `set -o pipefail` (Fallos en tuberías)
Por defecto, si conectas varios comandos con tuberías o pipes (|), Bash solo evalúa el código de salida del último comando.
 * El problema sin pipefail: Si haces comando_que_falla | echo "Terminado", Bash pensará que todo fue un éxito porque el echo (el último comando) funcionó, ignorando por completo el fallo catastrófico del principio.
 * La solución: pipefail le dice a Bash: "Si algún comando dentro de la tubería falla, considera que toda la tubería falló".
Plantilla de inicio rápido
Siempre que crees un nuevo script (por ejemplo en tu entorno Arch o Termux), inicia con este bloque:
```bash
#!/usr/bin/env bash
set -euo pipefail
IFS=$'\n\t' # Hace que los bucles 'for' separen elementos por saltos de línea y no por espacios

# Definición segura de variables iniciales
DEBUG="${DEBUG:-0}"
DIRECTORIO_BASE="${DIRECTORIO_BASE:-$HOME/mis_datos}"

# ... tu código aquí ...
```