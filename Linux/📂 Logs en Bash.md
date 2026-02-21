1. Conceptos Básicos de Redirección
En Bash, los logs se basan en desviar la salida de los comandos (stdout y stderr) hacia archivos.
 * >> (Append): Agrega contenido al final del archivo sin borrar lo anterior.
 * 2>&1: Redirige los errores al mismo lugar que la salida estándar.
 * /dev/null: El "agujero negro"; úsalo si quieres descartar la salida y no registrar nada.
```bash
# Ejemplo: Registrar salida y errores en un solo archivo
script.sh >> ejecucion.log 2>&1
```

2. El comando tee
Permite ver la salida en la terminal y guardarla en el log al mismo tiempo. Es fundamental para monitorear procesos en vivo.

```bash
# El flag -a es para 'append' (no sobrescribir)
comando | tee -a bitacora.log
```

3. Función de Log Profesional
Para que tus notas de Obsidian tengan un ejemplo reutilizable, esta función es el estándar de oro. Incluye Timestamp (fecha/hora) y Niveles.

```bash
# --- Función de Logger ---
LOG_FILE="mi_proyecto.log"

log() {
    local LEVEL=$1  # INFO, ERROR, WARN
    local MSG=$2
    local TIMESTAMP=$(date '+%Y-%m-%d %H:%M:%S')
    
    echo "[$TIMESTAMP] [$LEVEL] $MSG" | tee -a "$LOG_FILE"
}

# --- Uso ---
log "INFO" "Iniciando el script..."
log "WARN" "El espacio en disco es poco."
log "ERROR" "No se pudo conectar a la base de datos."
```

**4. Tipos de Niveles (Best Practices)**

| Nivel | Descripción |
|---|---|
| DEBUG | Detalles técnicos para desarrollo. |
| INFO | Confirmación de pasos exitosos. |
| WARN | Problemas menores (el script sigue). |
| ERROR | Fallos críticos que detienen el proceso. |
**5. Tips para Obsidian**

> [!TIP] Automatización Total
> Si quieres que todo lo que haga tu script se guarde automáticamente sin llamar a la función en cada línea, añade esto al inicio de tu archivo .sh:

```bash
exec > >(tee -a log_general.txt) 2>&1
```

 * [[Comandos Bash]]
 * [[Redirecciones en Linux]]
 * [[Automatización con Termux]]