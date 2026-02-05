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

# Instalación de ZSH

## ZSH(Oh my ZSH - Plugins - p10k)
### Instalar ZSH
```bash 
sudo apt install zsh-autosuggestions zsh-syntax-highlighting zsh -y #Debian/Ubuntu
sudo pacman -S zsh-autosuggestions zsh-syntax-highlighting zsh --noconfirm #Archlinux
```

### Instalar Oh my ZSH.
``` bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Instala los plugins.

- **autosuggessions plugin**
```bash 
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
- **zsh-syntax-highlighting plugin**
```bash 
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```
- **zsh-fast-syntax-highlighting plugin**
```bash
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/plugins/fast-syntax-highlighting
```
- **zsh-autocomplete plugin**
```bash 
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git $ZSH_CUSTOM/plugins/zsh-autocomplete
```
  
### Habilite los complementos agregándolos a .zshrc.
- Abrimos .zshrc
`nvim ~/.zshrc`
- Encuentra la línea que dice
`plugins=(git)`.
- Reemplace esa línea con
`plugins=(git zsh-autosuggestions zsh-syntax-highlighting fast-syntax-highlighting zsh-autocomplete)`

---
### Instalar Powerlevel10k

Instalar **Powerlevel10k** (p10k) es un excelente paso para mejorar tu terminal, especialmente considerando que sueles trabajar en entornos como **Arch Linux** y **Termux**.

Aquí tienes los pasos detallados para instalarlo utilizando **Oh My Zsh**, que es el método más común y sencillo:

### 1. Requisito previo: Instalar una Nerd Font

P10k utiliza iconos especiales. Si no tienes una fuente compatible, verás cuadros o signos de interrogación. La recomendada es **MesloLGS NF**.

- **En Windows (WSL/Terminal):** Descarga e instala el `.ttf` en Windows y selecciónalo en la configuración de la Terminal.
 
- **En Android (Termux):** Puedes usar `termux-styling` o descargar la fuente directamente a tu carpeta `~/.termux/font.ttf`.
### 2. Descargar Powerlevel10k

Clona el repositorio oficial dentro de la carpeta de temas de Oh My Zsh con este comando:

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ~/powerlevel10k
echo 'source ~/powerlevel10k/powerlevel10k.zsh-theme' >>~/.zshrc
```
### 3. Activar el tema en tu configuración

Debes editar tu archivo `.zshrc` (puedes usar **Neovim** con tu configuración de NvChad para esto):

1. Abre el archivo: `nvim ~/.zshrc`
2. Busca la línea que empieza con `ZSH_THEME`.
3. Cámbiala por: `ZSH_THEME="powerlevel10k/powerlevel10k"`
4. Guarda y cierra (`:wq`).
### 4. Configuración inicial

Para que los cambios surtan efecto, reinicia tu terminal o ejecuta:

```bash
source ~/.zshrc
```

Al hacerlo, se lanzará automáticamente el **asistente de configuración de p10k**.

El asistente te hará preguntas visuales (¿Ves un diamante? ¿Ves un candado?) para verificar que tu fuente es correcta y luego te permitirá elegir el estilo:

- **Lean**: Minimalista.
- **Classic**: Con separadores angulares.
- **Rainbow**: Con bloques de colores (muy popular).
### Tips adicionales

- **Reconfigurar**: Si alguna vez quieres cambiar el diseño, simplemente ejecuta: `p10k configure`.
- **Plugins**: Ya que usas mucho el desarrollo en Python y Linux, te recomiendo añadir `zsh-autosuggestions` y `zsh-syntax-highlighting` a tu lista de `plugins=(...)` en el `.zshrc` para una experiencia completa.



## Relacionado:
[[Alias básicos en Bash]]