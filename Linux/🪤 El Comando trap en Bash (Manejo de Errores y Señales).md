En Bash, trap funciona exactamente como una trampa o una alarma. Le dice al script: "Quédate vigilando, y si ocurre X evento (un error, que el usuario presione Ctrl+C, o que el script termine), ejecuta este código inmediatamente".
Es fundamental para crear scripts robustos, ya que te permite "limpiar" la casa antes de salir o capturar exactamente dónde falló el programa.

### 🏗️ Sintaxis Básica

```bash
trap 'comando_a_ejecutar' SEÑAL
```

 * comando_a_ejecutar: Lo que quieres que haga el script (puede ser un echo, borrar un archivo temporal, o llamar a una función).
 * SEÑAL: El evento que activa la trampa.

**Las Señales más comunes:**

| Señal | ¿Cuándo se activa? |
|---|---|
| ERR | Cuando cualquier comando falla (devuelve un código distinto a 0). |
| EXIT | Justo cuando el script está a punto de terminar (ya sea por éxito o por error). |
| INT | (Interrupt) Cuando el usuario cancela el script presionando Ctrl + C. |
| DEBUG | Se ejecuta antes de evaluar cada línea o comando individual del script. |
### 🕵️‍♂️ Análisis Avanzado: El trap de tu script de Notas
En tu script tienes un bloque de código muy profesional para rastrear errores. Vamos a desglosarlo línea por línea para entender la magia que hace:

```bash
# 1. Inicializamos variables para que 'set -u' no lance error de "unbound variable"
current_command=''
last_command=''
ret=0

# 2. La trampa de rastreo (DEBUG)
trap 'last_command=${current_command-}; current_command=$BASH_COMMAND' DEBUG

# 3. La trampa de error (ERR)
trap 'ret=$?; err "Fallo: comando \"${last_command:-unknown}\" devolvió $ret"; exit $ret' ERR
```

**¿Cómo funciona en conjunto?**

Paso 1: El Vigilante Constante (DEBUG)
La primera trampa usa la señal DEBUG. Esto significa que Bash ejecuta ese código justo antes de correr cualquier comando de tu script.
 * $BASH_COMMAND es una variable secreta del sistema que contiene "el comando que estoy a punto de ejecutar".
 * Lo que hace esta línea es un juego de manos: Pasa el comando actual a la variable last_command (comando anterior), y guarda el nuevo comando que está por ejecutarse en current_command.
 * Resultado: En todo momento, tu script tiene en su memoria cuál fue el último comando que ejecutó. (Por eso veías los ++ en tu terminal cuando activaste el modo debug).

Paso 2: La Red de Seguridad (ERR)
Si un comando falla, Bash activa la segunda trampa (porque usaste la señal ERR).
 * ret=$?: Guarda el código de error exacto (ej. código 1, código 2, etc.) en la variable ret.
 * Llama a tu función de error (err) y le manda un mensaje dinámico diciendo exactamente qué comando falló leyendo la variable last_command que recolectamos en el paso anterior.
 * exit $ret: Apaga el script de forma segura devolviendo el código de error original.

>[!abstract] 💡 En resumen: En lugar de que el script muera en silencio y te deje adivinando por qué falló, este sistema te dice: "Oye, el script se detuvo en el comando `mkdir -p /ruta y falló con el código de error 1"`.

### 🧹 Otros Usos Prácticos de trap

**1. Limpiar archivos temporales al salir (El uso más común)**

Si tu script crea archivos basura temporales (.tmp), puedes asegurar que siempre se borren, incluso si el script falla a la mitad o si el usuario lo cancela con Ctrl+C.
```bash
# Creamos un archivo temporal
ARCHIVO_TEMP=$(mktemp)

# Le decimos a Bash: "No importa cómo termines (EXIT), siempre borra este archivo"
trap 'rm -f "$ARCHIVO_TEMP"; echo "Limpieza completada."' EXIT

# ... resto del código ...
```

**2. Bloquear el Ctrl + C (No recomendado a menos que sea necesario)**

Si estás ejecutando una instalación crítica y no quieres que el usuario la interrumpa a la mitad y corrompa el sistema:

```bash
Sobrescribimos la señal INT (Interrupción) con un simple mensaje
trap 'echo "Por favor, espera a que termine la instalación..."' INT
```

¡Lista! Ya puedes agregarla a tus notas.

>[!info] Es increíble cómo combinar `set -euo pipefail` junto con este rastreador de errores de trap eleva un script de aficionado a nivel empresarial.
