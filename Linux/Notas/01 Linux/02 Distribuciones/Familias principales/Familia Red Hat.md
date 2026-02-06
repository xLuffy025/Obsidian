---
Relacionado:
  - "[[Fedora]]"
  - "[[OpenShift]]"
  - "[[Podman]]"
  - "[[RPM]]"
  - "[[SELinux]]"
  - "[[SELinux]]"
  - "[[03 Mapa de Distribuciones Linux]]"
---

## 🌶️ La familia Red Hat / Fedora

Esta familia es crucial porque define otro estilo de Linux, muy diferente al mundo Debian.  
Si Debian es estabilidad y comunidad, Red Hat es estandarización, profesionalización y empresa.

---

## 🌳 1. Red Hat: la raíz del árbol
### Red Hat nació con una idea distinta a Debian:
- Estandarizar Linux para empresas  
- Soporte profesional  
- Ciclos de vida largos (LTS)  
- Herramientas corporativas  
- RPM como formato de paquetes  
- YUN-DNF como gestores

### Red Hat Enterprise Linux (RHEL) es la base de toda esta familia.

Cuándo se usa RHEL:  
- Empresas  
- Centros de datos  
- Servidores críticos  
- Infraestructura corporativa  
- Certificaciones (RHCSA, RHCE)

---

## 🌿 2. Ramas principales de la familia Red Hat
## Desde RHEL salen dos ramas enormes:

*A) Derivadas empresariales (clones de RHEL)*
- CentOS Stream  
- Rocky Linux  
- AlmaLinux  
- Oracle Linux

*B) Derivadas comunitarias / de escritorio*
- Fedora  
- Korora (descontinuada)  
- Qubes OS (parcialmente)

---

## 🌱 3. Derivadas empresariales (propósito y uso)

**CentOS Stream**
- Antes era un clon de RHEL, ahora es “la versión previa” a RHEL.  
- Ideal para: pruebas antes de pasar a RHEL, desarrollo empresarial.

**Rocky Linux**
- Fundado por el creador original de CentOS.  
- Objetivo: ser el clon 1:1 de RHEL.  
- Ideal para: reemplazar CentOS clásico, servidores estables.

**AlmaLinux**
- Otro clon 1:1 de RHEL.  
- Ideal para: empresas que quieren estabilidad sin pagar RHEL.

**Oracle Linux**
- Clon de RHEL con kernel optimizado.  
- Ideal para: entornos Oracle, bases de datos grandes.

---

## 🌼 4. Derivadas comunitarias / de escritorio

_Fedora_
La distro más importante de esta familia después de RHEL.

- Es el “laboratorio” donde se prueban tecnologías nuevas.  
- Muy actualizada, moderna, innovadora.  
- Base de lo que luego llega a RHEL.

Ideal para:  
- Desarrolladores  
- Usuarios avanzados  
- Escritorio moderno  
- Quienes quieren software reciente pero estable

**Qubes OS (parcialmente basado en Fedora)**
- Enfoque: seguridad extrema mediante virtualización por compartimentos.  
- Ideal para: privacidad, investigación, seguridad defensiva.

---

## 🌺 5. Distros Red Hat especializadas (por función)

| Función                      | Distro recomendada |
| ---------------------------- | ------------------ |
| Servidores empresariales     | RHEL, Rocky, Alma  |
| Desarrollo                   | Fedora Workstation |
| Seguridad extrema            | Qubes OS           |
| Bases de datos               | Oracle Linux       |
| Pruebas previas a producción | CentOS Stream      |

---

## 🌞 6. ¿Cuándo usar cada una? (Mapa mental práctico)

Si quieres estabilidad empresarial
*→ RHEL, Rocky Linux, AlmaLinux*

Si quieres lo más nuevo sin perder estabilidad
*→ Fedora Workstation*

Si quieres seguridad extrema
*→ Qubes OS*

Si quieres infraestructura corporativa
*→ RHEL*

Si quieres un entorno de pruebas para RHEL
*→ CentOS Stream*


---
# 🎯 8. Cómo se usa esta familia en la vida real

En empresas
- RHEL en servidores  
- OpenShift para contenedores  
- Podman para desarrollo seguro  
- SELinux SELinux en enforcing  
- Rocky/Alma para entornos sin licencia

En desarrollo
- Fedora Workstation  
- Podman rootless  
- Silverblue para entornos reproducibles

En seguridad
- SELinux  
- Qubes OS (basado parcialmente en Fedora

---
