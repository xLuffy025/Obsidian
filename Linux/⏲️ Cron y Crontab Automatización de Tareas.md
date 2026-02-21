
Cron es el demonio (proceso en segundo plano) de Linux que ejecuta scripts o comandos a intervalos regulares. Se gestiona a través del comando crontab.

**1. Comandos Esenciales**
Para gestionar tus tareas programadas, usa estos comandos en la terminal:
 * crontab -e: Abre tu archivo de configuración para editar tareas.
 * crontab -l: Lista todas las tareas que tienes programadas.
 * crontab -r: Elimina todas tus tareas programadas.
**2. La Sintaxis del Crontab**
El archivo se organiza en 5 columnas seguidas del comando. En Obsidian puedes usar esta tabla como referencia rápida:

| Minuto | Hora | Día del Mes | Mes  | Día de la Semana   | Comando           |
| ------ | ---- | ----------- | ---- | ------------------ | ----------------- |
| 0-59   | 0-23 | 1-31        | 1-12 | 0-6 (0 es domingo) | /ruta/al/script.s |

**Operadores Especiales:**
 * *: Todos los valores (ej. * en hora significa "cada hora").
 * ,: Lista de valores (ej. 1,15,30 en minutos).
 * -: Rango de valores (ej. 1-5 en días significa de lunes a viernes).
 * */n: Cada "n" intervalos (ej. */10 en minutos significa "cada 10 minutos").

**3. Ejemplo Práctico: Log Automático**

Como estás aprendiendo a hacer scripts más formales, este es un ejemplo que ejecuta un script de respaldo y guarda un log cada hora:

Paso A: El Script (backup.sh)

```bash
#!/bin/bash
# Script simple para practicar logs
TIMESTAMP=$(date '+%Y-%m-%d_%H-%M-%S')
echo "[$TIMESTAMP] Respaldo ejecutado con éxito" >> /home/usuario/logs/cron_log.txt

Paso B: La Tarea Cron
Para ejecutar ese script todos los días a las 3:30 AM, añade esto al crontab -e:
# ┌───────────── minuto (0 - 59)
# │ ┌───────────── hora (0 - 23)
# │ │ ┌─────────── día del mes (1 - 31)
# │ │ │ ┌───────── mes (1 - 12)
# │ │ │ │ ┌─────── día de la semana (0 - 6) 
# │ │ │ │ │
# ↓ ↓ ↓ ↓ ↓
30 03 * * * /bin/bash /home/usuario/scripts/backup.sh
```

**4. Atajos Útiles (Macros)**

En lugar de los 5 asteriscos, puedes usar estos atajos comunes:
 * @reboot: Se ejecuta una vez al encender el sistema (ideal para iniciar servicios en Termux o Arch).
 * @daily: Una vez al día (equivale a 0 0 * * *).
 * @hourly: Una vez por hora (equivale a 0 * * * *).

**5. Tips para tus Notas de Obsidian**

> [!IMPORTANT] Rutas Absolutas
> cron no conoce tu entorno de usuario habitual. Siempre usa rutas completas.

* Mal: `python script.py`
   * Bien: `/usr/bin/python3 /home/usuario/scripts/script.py> 

>[!TIP] Logs de Error

Para saber »si tu tarea cron falló, redirige el error a un  * * * * * /ruta/al/script.sh >> /ruta/al/log.txt 2>&1
> 
Etiquetas: #linux #bash #automatización #aprendizaje
