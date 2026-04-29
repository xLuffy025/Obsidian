## ¿Qué es `read`?

`read` permite que el **usuario escriba datos** mientras el script está corriendo. Hace tus scripts interactivos.

---

## Sintaxis básica:

```bash
#!/usr/bin/env bash

# Sin mensaje
read nombre

# Con mensaje (-p = prompt)
read -p "¿Cuál es tu nombre? " nombre

echo "Hola $nombre"
```

---

## Opciones útiles de `read`:

| Opción | Para qué |
|---|---|
| `-p "texto"` | Muestra un mensaje antes |
| `-s` | Oculta lo que escribe (contraseñas) |
| `-n 1` | Lee solo 1 carácter |
| `-t 5` | Espera 5 segundos máximo |

---

## Ejemplo completo:

```bash
#!/usr/bin/env bash

read -p "Tu nombre: " nombre
read -p "Tu edad: " edad
read -s -p "Tu contraseña: " password
echo ""  # salto de línea después de -s

echo "Nombre: $nombre"
echo "Edad: $edad"
echo "Contraseña guardada ✅"
```

---

## 🏋️ Ejercicio

Crea `input.sh` que:
- Pregunte el nombre
- Pregunte la edad
- Pregunte el sistema operativo favorito
- Imprima todo junto en un resumen