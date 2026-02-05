**🔐 1. SELinux**: el corazón de la seguridad en Red Hat
SELinux no es un “extra”: es la razón por la que Red Hat domina en entornos críticos.

Qué es **SELinux**
Un sistema de control de acceso obligatorio (MAC) que define qué puede hacer cada proceso, incluso si es comprometido.

Cómo funciona
- Cada archivo, proceso y puerto tiene un contexto.  
- Las políticas definen qué interacciones están permitidas.  
- Si algo no está explícitamente permitido, se bloquea.

Modos
- Enforcing → aplica las reglas estrictamente  
- Permissive → solo registra violaciones  
- Disabled → apagado (no recomendado)

Por qué es tan importante
- Evita escaladas de privilegios  
- Contiene ataques incluso si un servicio es vulnerado  
- Es obligatorio en sectores como banca, salud, gobierno

Idea clave para tu mapa:  
> SELinux convierte a Linux en un sistema con seguridad de nivel militar.