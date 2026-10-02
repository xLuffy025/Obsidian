El [kernel de Linux](https://www.google.com/search?sca_esv=a6c955fe1b50965a&hl=es-419&sxsrf=ANbL-n7jLjNy43VRpixrdk6fpihKfZznMg%3A1770351266713&q=kernel+de+Linux&source=lnms&fbs=ADc_l-bpk8W4E-qsVlOvbGJcDwpn60DczFdcvPnuv8WQohHLTbSVldBrj9mdwFjfwIgEUgS3rVmfuCXEBMRJMD3ur3wa2tCLwsB8aJ5Wjp89WKeRLLuXs4tOjKCOoHNLgcMj1cdUd43WEXlolARzPDn0VTcY2vLoEbvIv07nsT709DAAHPjp7p2FORnVxJJVJuWwlKLShdhhmDihtkNJtVcDF1_m0s-bB7azOXGHE1kGHcsMXz-XV-c&sa=X&ved=2ahUKEwj69am0gMSSAxXzI0QIHU0WKXkQgK4QegYIAQgAEAM&biw=1358&bih=636&dpr=1) es el ==núcleo fundamental y de código abierto de los sistemas operativos basados en Linux==, actuando como intermediario esencial entre el hardware (CPU, memoria, dispositivos) y el software. Desarrollado desde 1991 por [Linus Torvalds](https://www.google.com/search?sca_esv=a6c955fe1b50965a&hl=es-419&sxsrf=ANbL-n7jLjNy43VRpixrdk6fpihKfZznMg%3A1770351266713&q=Linus+Torvalds&source=lnms&fbs=ADc_l-bpk8W4E-qsVlOvbGJcDwpn60DczFdcvPnuv8WQohHLTbSVldBrj9mdwFjfwIgEUgS3rVmfuCXEBMRJMD3ur3wa2tCLwsB8aJ5Wjp89WKeRLLuXs4tOjKCOoHNLgcMj1cdUd43WEXlolARzPDn0VTcY2vLoEbvIv07nsT709DAAHPjp7p2FORnVxJJVJuWwlKLShdhhmDihtkNJtVcDF1_m0s-bB7azOXGHE1kGHcsMXz-XV-c&sa=X&ved=2ahUKEwj69am0gMSSAxXzI0QIHU0WKXkQgK4QegYIAQgAEAU&biw=1358&bih=636&dpr=1), gestiona recursos, procesos, controladores y seguridad. Funciona en modo "monolítico modular", lo que permite cargar controladores dinámicamente.

**Funciones Clave del Kernel Linux**

- **Gestión de Procesos:** Decide qué programas usan la CPU, cuándo y por cuánto tiempo.

- **Gestión de Memoria:** Supervisa la RAM, asignando espacio y liberándolo según sea necesario.

- **Controladores de Dispositivos (Drivers):** Actúa como mediador entre el hardware y las aplicaciones.

- **Seguridad y Llamadas al Sistema (SCI):** Recibe solicitudes de software y gestiona la seguridad del sistema.

**Características Principales**

- **Código Abierto:** Disponible bajo la licencia GPLv2, permitiendo su modificación y distribución libre.
- **Monolítico:** Todo el sistema operativo funciona en el espacio del núcleo, lo que ofrece alta eficiencia.
- **Versatilidad:** Utilizado en una gama inmensa de dispositivos, desde supercomputadoras hasta teléfonos Android e Internet de las cosas (IoT). 

**Gestión del Kernel**

- **Versiones:** Evoluciona continuamente, pasando por las series 5.x hasta llegar a la 6.x, con lanzamientos LTS (Long Term Support) para mayor estabilidad.
- **Verificación:** Se puede comprobar la versión en uso mediante el comando `uname -a` o `uname -mrs` en la terminal.
- **Actualización:** Es vital mantenerlo actualizado para mejorar la compatibilidad de hardware y parches de seguridad. 

El desarrollo del kernel es colaborativo y se rastrea utilizando Git, sistema creado por el propio Linus Torvalds.

>[!info] Todo en Linux depende del kernel, incluso las distros.

Relacionado:
- [[01 Qué es GNU Linux]]
- [[Distribuciones Linux]]
