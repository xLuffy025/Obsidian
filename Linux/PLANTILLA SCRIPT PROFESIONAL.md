```bash
#!/usr/bin/env bash

# ==============================================================================
# Nombre: plantilla_robusta.sh
# Descripción: Estructura base para crear scripts seguros y mantenibles.
# Autor: [Tu Nombre]
# ==============================================================================

# ------------------------------------------------------------------------------
# 1. MODO ESTRICTO (Red de seguridad)
# ------------------------------------------------------------------------------
# -e: Detiene el script inmediatamente si un comando falla.
# -u: Detiene el script si intentas usar una variable no definida.
# -o pipefail: Atrapa errores dentro de tuberías (ej. comando1 | comando2).
set -euo pipefail

# ------------------------------------------------------------------------------
# 2. VARIABLES GLOBALES Y CONFIGURACIÓN
# ------------------------------------------------------------------------------
# Declaramos las variables desde el inicio para evitar errores de "unbound variable"
DEBUG=0
VERSION="1.0.0"

# Códigos de escape ANSI para darle color a los mensajes en la terminal
ROJO='\033[0;31m'
VERDE='\033[0;32m'
AMARILLO='\033[1;33m'
SIN_COLOR='\033[0m'

# ------------------------------------------------------------------------------
# 3. FUNCIONES DE UTILIDAD (Herramientas reutilizables)
# ------------------------------------------------------------------------------

# Imprime un mensaje de error en rojo y detiene la ejecución del script con código 1
error_exit() {
    echo -e "${ROJO}Error:${SIN_COLOR} $1" >&2
    exit 1
}

# Imprime un mensaje informativo en verde
log_info() {
    echo -e "${VERDE}Info:${SIN_COLOR} $1"
}

# ------------------------------------------------------------------------------
# 4. LÓGICA PRINCIPAL (El corazón del script)
# ------------------------------------------------------------------------------
main() {
    log_info "Iniciando script v${VERSION}..."

    # Ejemplo de cómo usar nuestra variable DEBUG
    if (( DEBUG == 1 )); then
        echo -e "${AMARILLO}[DEBUG] Modo de depuración activado. Mostrando detalles...${SIN_COLOR}"
    fi

    # --- Aquí va tu código real ---
    # Ejemplo de uso de la función de error:
    # mkdir /directorio_protegido || error_exit "No se pudo crear el directorio. ¿Tienes permisos?"

    log_info "Proceso finalizado correctamente."
}

# ------------------------------------------------------------------------------
# 5. PUNTO DE ENTRADA
# ------------------------------------------------------------------------------
# Llamamos a la función principal pasándole todos los argumentos del script ("$@")
main "$@"
```

### ​La anatomía de un script "formal" o robusto

​ Esta es la mejor manera de estructurar un script profesional paso a paso. Es una convención que te ayudará a mantener el orden a medida que tus programas crezcan:

1. ​**El** _**Shebang**_**:** Indica qué intérprete va a ejecutar el código (ej. `#!/bin/bash`).
2. ​**El "Modo Estricto":** Tus reglas de seguridad (ej. `set -euo pipefail`).
3. ​**Variables Globales y de Configuración:** Aquí va tu `DEBUG=0`, rutas de archivos, colores para la terminal, etc. Ponerlas todas juntas al inicio hace que sean fáciles de modificar después.
4. ​**Funciones:** Bloques de código reutilizables (ej. una función para imprimir mensajes de error o para guardar una nota).
5. ​**Lógica Principal:** El código que realmente hace el trabajo, usando las variables y funciones que definiste arriba.