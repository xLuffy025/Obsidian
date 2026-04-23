

---

🔐 1. ¿Qué son los permisos en Linux?

En Linux, todo es un archivo (archivos, carpetas, dispositivos).
Cada uno tiene permisos que controlan quién puede hacer qué.

Hay 3 tipos de usuarios:

Owner (u) → dueño del archivo

Group (g) → grupo del archivo

Others (o) → todos los demás



---

⚙️ 2. Tipos de permisos

Hay 3 permisos básicos:

r (read) → leer

w (write) → escribir/modificar

x (execute) → ejecutar



---

📂 3. Cómo ver permisos

Usa:

ls -l

Ejemplo:

-rwxr-xr-- 1 user user 1234 archivo.sh

Desglose:

- rwx r-x r--
| |   |   |
| |   |   └─ otros
| |   └──── grupo
| └──────── owner
└────────── tipo de archivo


---

📌 4. Tipos de archivo (primer carácter)

- → archivo normal

d → directorio

l → enlace simbólico



---

🔢 5. Permisos en formato numérico (muy importante)

Cada permiso tiene valor:

r = 4

w = 2

x = 1


Se suman:

Permiso	Valor

rwx	7
rw-	6
r-x	5
r--	4


Ejemplo:

chmod 755 archivo.sh

Significa:

Owner → 7 (rwx)

Group → 5 (r-x)

Others → 5 (r-x)



---

🛠️ 6. Cambiar permisos (chmod)

Forma numérica:

chmod 755 archivo.sh

Forma simbólica:

chmod u+x archivo.sh   # agrega ejecución al owner
chmod g-w archivo.sh   # quita escritura al grupo
chmod o=r archivo.sh   # otros solo lectura


---

👤 7. Cambiar dueño (chown)

chown usuario archivo

Ejemplo:

chown root archivo.sh

Cambiar usuario y grupo:

chown usuario:grupo archivo


---

👥 8. Cambiar grupo (chgrp)

chgrp grupo archivo


---

📁 9. Permisos en directorios

Aquí cambia un poco:

r → ver contenido

w → crear/eliminar archivos

x → entrar al directorio


Ejemplo:

chmod 755 carpeta


---

⚠️ 10. Permisos especiales (nivel pro)

🔴 SUID (Set User ID)

Ejecuta archivo como el dueño:

chmod 4755 archivo

Ejemplo típico: passwd


---

🔵 SGID (Set Group ID)

Ejecuta con permisos del grupo:

chmod 2755 archivo

En carpetas → heredan grupo


---

🟡 Sticky Bit

Solo el dueño puede borrar archivos:

chmod 1777 carpeta

Ejemplo: /tmp


---

🔍 11. Ver permisos especiales

ls -l

Ejemplo:

-rwsr-xr-x

s indica SUID o SGID.


---

🔐 12. Umask (permisos por defecto)

Define permisos al crear archivos.

Ver:

umask

Ejemplo:

umask 022

Resultado:

Archivos → 644

Carpetas → 755



---

⚡ 13. Ejemplos prácticos

Hacer script ejecutable

chmod +x script.sh


---

Proteger archivo

chmod 600 secreto.txt


---

Carpeta privada

chmod 700 privada


---

🧠 14. Consejos importantes

❌ Nunca uses 777 en todo → es inseguro

✔️ Usa permisos mínimos necesarios

✔️ Usa grupos para compartir acceso

✔️ Cuidado con SUID (puede ser peligroso)



---

🧪 15. Ejercicio para practicar (recomendado)

En tu entorno (Termux o Linux):

mkdir test_permisos
cd test_permisos

touch archivo.txt
ls -l

chmod 700 archivo.txt
ls -l


---

🚀 16. Nivel siguiente (si quieres avanzar)

Después de esto puedes aprender:

ACLs (setfacl) → permisos avanzados

Seguridad en servidores

Usuarios y grupos en profundidad

Automatización con bash



---

Si quieres, puedo llevarte a nivel práctico con un mini proyecto tipo:

👉 “crear sistema de usuarios con permisos reales en Linux como en un servidor”

o incluso integrarlo con tus scripts en Termux.