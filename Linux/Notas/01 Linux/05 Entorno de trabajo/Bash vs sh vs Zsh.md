## Compatibilidad entre Shells y Portabilidad (bash vs sh vs zsh)

### Objetivos de aprendizaje

- Comprender las diferencias entre Bash, sh y Zsh.
- Escribir scripts portables.

### Explicación teórica

- **Bash**: El shell más común en Linux, compatible con sh, pero con extensiones propias.
- **sh**: Shell estándar POSIX, máxima portabilidad.
- **Zsh**: Shell avanzado, más personalizable, pero menos estándar para scripting.

**Recomendaciones**:

- Usa `#!/bin/bash` si usas características específicas de Bash.
- Usa `#!/bin/sh` para scripts portables entre sistemas.
- Evita extensiones propias de Bash si necesitas máxima compatibilidad.
### Tabla comparativa

|Característica|Bash|sh (POSIX)|Zsh|
|---|---|---|---|
|Portabilidad|Alta|Máxima|Media|
|Personalización|Media|Baja|Muy alta|
|Plugins/Temas|Limitado|No|Sí (Oh My Zsh)|
|Uso en scripting|Estándar|Estándar|Opcional|

### Ejercicio interactivo

- Escribe un script que funcione tanto en Bash como en sh.
- Prueba el mismo script en Zsh y observa diferencias.

---
## Relacionado:
[[Zsh y personalizacion]]
[[Alias básicos en Bash]]