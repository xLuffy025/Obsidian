
---
## ¿Qué es una variable?

Una variable es como una **caja** donde guardas información para usarla después.

```bash
#!/usr/bin/env bash

nombre="José"
edad=38
meta="hacking ético"

echo "Nombre: $nombre"
echo "Edad: $edad"
echo "Meta: $meta"
```

---

## Reglas importantes:

| Regla | Correcto | Incorrecto |
|---|---|---|
| Sin espacios en `=` | `nombre="José"` | `nombre = "José"` |
| Para usar la variable | `$nombre` | `nombre` |
| Nombres en minúscula | `mi_nombre` | `Mi Nombre` |

---

## 🏋️ Ejercicio

Crea `variables.sh` con:
- Una variable con tu nombre
- Una variable con tu edad
- Una variable con tu sistema operativo
- Imprime todo con `echo` usando las variables

