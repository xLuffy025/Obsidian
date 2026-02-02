El sistema operativo **GNU/Linux** es el resultado de la unión de dos proyectos independientes: el software de utilidad **GNU**, iniciado por Richard Stallman en 1984, y el núcleo (kernel) **Linux**, creado por Linus Torvalds en 1991 [1-3]. Esta combinación permitió la existencia del primer sistema operativo libre con código fuente disponible para arquitecturas de ordenadores comunes [3, 4].

Aquí tienes un resumen de su historia y las principales distribuciones que existen.

### Breve Historia: El Origen de un Sistema Libre

*   **El Proyecto GNU (1984):** Richard Stallman fundó la *Free Software Foundation* (FSF) para crear un sistema operativo tipo UNIX que fuera **software libre** . Para 1991, el proyecto ya tenía editores, compiladores y utilidades, pero carecía de un núcleo funcional (su núcleo, llamado Hurd, seguía en desarrollo) .
*   **Linus Torvalds y el Kernel Linux (1991):** Linus Torvalds, un estudiante finlandés, anunció en agosto de 1991 que había creado un núcleo basado en **Minix** (un clon académico de UNIX) para procesadores Intel 386 . Lo ofreció a la comunidad para que lo probaran y sugirieran mejoras.
*   **La Unión Definitiva:** Al combinar el núcleo de Torvalds con las herramientas de Stallman, nació lo que hoy conocemos como **GNU/Linux**.
*   **Filosofía:** Se basa en **cuatro libertades fundamentales**: usar el programa, estudiarlo/modificarlo, redistribuirlo y mejorar el código fuente. Mientras que el "Software Libre" tiene un enfoque ético y social, el término "Código Abierto" (Open Source) surgió después con un enfoque más pragmático y técnico.

---

### ¿Qué es una Distribución (Distro)?

Una distribución es una colección de software que incluye el **núcleo Linux** junto con una selección de aplicaciones y herramientas de configuración mantenidas por una empresa o comunidad. Su objetivo es optimizar el sistema para usos específicos, como computadoras personales, servidores o sistemas embebidos.

![[FB_IMG_1769723860184.jpg]]
#### 1. [[Familia Debían]] (Usa paquetes `.deb` y herramientas como `apt`)
*   **Debian:** Lanzada en 1993, es una de las más grandes y estables. Es mantenida por voluntarios de todo el mundo y no depende de ninguna empresa.
*   **Ubuntu:** Basada en Debian, se creó en 2004 para ofrecer un escritorio fácil de usar. Ofrece versiones **LTS** (*Long Term Support*) con soporte garantizado por varios años.
*   **Kali Linux:** Diseñada específicamente para auditorías de seguridad, pruebas de intrusión e informática forense.
*   **Knoppix:** Famosa por ser una de las primeras en ejecutarse directamente desde un CD (LiveCD) sin necesidad de instalación [29, 30].

#### 2. [[Familia Red Hat]] (Usa paquetes `.rpm` y herramientas como `yum` o `dnf`)
*   **Red Hat Enterprise Linux (RHEL):** Distribución comercial para empresas con soporte técnico profesional [24, 31, 32].
*   **CentOS:** Surge a partir del código fuente gratuito de RHEL, ofreciendo una versión empresarial estable pero sin soporte comercial [24, 33].
*   **Fedora:** Patrocinada por Red Hat, se enfoca en escritorios y sirve como banco de pruebas para las tecnologías que luego irán a RHEL [34-36].

#### 3. Familia SUSE
*   **SUSE Linux Enterprise Server (SLES):** Versión comercial para entornos de producción corporativos [37].
*   **openSUSE:** Versión gratuita y abierta para la comunidad de desarrolladores y usuarios [30, 37].

#### 4. Otras Distribuciones Destacadas
*   **Slackware:** Una de las más antiguas, apreciada por quienes desean aprender cómo funciona el sistema a bajo nivel [38, 39].
*   **Gentoo:** Se diferencia porque el usuario compila todos los programas desde el código fuente para maximizar la optimización [36, 40].
*   **Arch Linux:** Una distribución para usuarios avanzados que utiliza un modelo de actualización constante [[rolling release]] .
*   **Android:** Aunque no es una distribución convencional, utiliza una versión modificada del kernel de Linux para dispositivos móviles [43, 44].

Para entender Linux, primero debemos hablar del **Kernel** (o núcleo). Imagina que el Kernel es el director de una orquesta: no toca los instrumentos, pero se asegura de que los músicos (el hardware, como tu procesador y memoria) y las partituras (el software o aplicaciones) trabajen juntos en perfecta armonía.

### Conceptos Clave para empezar:

- **El Kernel 🧠**: Es el corazón del sistema. Gestiona la comunicación entre el software y el hardware.

- **Código Abierto (Open Source) 🔓**: A diferencia de otros sistemas, el "receta" (código fuente) de Linux es pública. Cualquiera puede verla, modificarla y compartirla.

- **Distribuciones (Distros) 📦**: Como el Kernel es libre, diferentes grupos crean sus propias versiones combinándolo con distintas herramientas. Hay distros para principiantes (como Ubuntu), para expertos (como Arch) o para servidores.
