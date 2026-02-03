### Cómo verificar e instalar Vim

Para confirmar si `vim` está instalado y, en caso contrario, añadirlo a su sistema, siga estos sencillos pasos dentro de su sesión de proot-distro Arch Linux:

1. **Actualice los repositorios de paquetes:** Antes de instalar cualquier software nuevo, es una buena práctica asegurarse de que su lista de paquetes esté actualizada.

```bash
sudo pacman -Syu #ArchLinux
sudo apt update && sudo apt upgrade -y #Debian/Ubuntu
sudo def upgrade -y #Fedora
pkg update && pkg upgrade -y  #Termux
```

2. **Intente instalar `vim`:** La forma más sencilla de verificar e instalar es ejecutar directamente el comando de instalación. Si `vim` ya estuviera presente en su versión más reciente, `pacman` se lo notificaría.

```bash
pacman -S vim
```

Tras ejecutar este comando, de instalación según tu distro se  descargará e instalará `vim` y las dependencias necesarias. Una vez completado el proceso, podrá empezar a utilizar el editor de texto `vim` escribiendo `vim` en su terminal.

El enfoque minimalista de Arch Linux y, por extensión, de las instalaciones a través de proot-distro, otorga a los usuarios un control total sobre el software presente en su sistema, evitando la inclusión de paquetes que podrían no ser necesarios para todos.

---

Aquí tienes una guía completa para empezar a configurar tu Vim, desde lo más básico hasta la instalación de plugins.

### 1. El Archivo `.vimrc`: El Corazón de tu Configuración

El archivo `.vimrc` es un fichero de texto plano que se encuentra en tu directorio `home`. Vim lo lee cada vez que se inicia para aplicar tu configuración personalizada. Si no existe, puedes crearlo.

- **Linux y macOS:** El archivo se encuentra en `~/.vimrc`.
- **Windows:** Generalmente se encuentra en `C:\Users\<tu_usuario>\_vimrc`.

**Para crear y editar tu `.vimrc`:**

1. Abre una terminal (o PowerShell en Windows).
2. Escribe `vim ~/.vimrc` (o `vim ~/_vimrc` en Windows).
3. Presiona `i` para entrar en el modo de inserción y comenzar a añadir tu configuración.

### 2. Configuración Básica Esencial (Tu Primer `.vimrc`)

Copia y pega este bloque de configuración en tu archivo `.vimrc`. Es un excelente punto de partida que activa funcionalidades muy útiles y mejora la experiencia de usuario.

Vim Script

```javascript
" =============================================================================
"  CONFIGURACIÓN ESENCIAL
" =============================================================================

" Establece el modo 'nocompatible' para usar todas las características de Vim
set nocompatible

" Codificación de caracteres
set encoding=utf-8

" Activa el resaltado de sintaxis
syntax on

" Muestra los números de línea
set number

" Muestra el número de línea relativo (útil para movimientos)
set relativenumber

" Resalta la línea actual
set cursorline

" Muestra la posición del cursor en la barra de estado
set ruler

" Búsquedas inteligentes: no distingue mayúsculas/minúsculas a menos que
" incluyas una letra mayúscula en tu búsqueda.
set ignorecase
set smartcase

" Resalta los resultados de la búsqueda a medida que escribes
set incsearch
set hlsearch

" Permite borrar texto con la tecla de retroceso sobre saltos de línea,
" auto-indentación y el inicio de la inserción.
set backspace=indent,eol,start

" Muestra los comandos que estás escribiendo en la esquina inferior derecha
set showcmd

" Muestra las coincidencias de paréntesis y corchetes
set showmatch

" =============================================================================
"  INDENTACIÓN Y FORMATO
" =============================================================================

" Activa la indentación automática al crear una nueva línea
set autoindent

" Usa espacios en lugar de tabulaciones
set expandtab

" Número de espacios por tabulación
set tabstop=4

" Número de espacios a usar en operaciones de indentación (<< y >>)
set shiftwidth=4

" Hereda la indentación de la línea anterior
set smartindent
```

**Para guardar y salir:**

1. Presiona la tecla `Esc` para salir del modo de inserción.
2. Escribe `:wq` y presiona `Enter`. Esto escribe (`w`) los cambios y cierra (`q`) Vim.

La próxima vez que abras Vim, notarás inmediatamente los cambios: números de línea, resaltado de sintaxis y mucho más.

---

### 3. Ampliando Vim con Plugins

Los plugins añaden funcionalidades increíbles a Vim. Para gestionarlos fácilmente, necesitas un gestor de plugins. **vim-plug** es uno de los más populares y sencillos de usar.

#### Paso 1: Instalar vim-plug

Ejecuta el siguiente comando en tu terminal (para Linux o macOS):

Bash

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

_(Para Windows y otras instalaciones, consulta las [instrucciones oficiales de vim-plug](https://github.com/junegunn/vim-plug))._

#### Paso 2: Configurar vim-plug en tu `.vimrc`

Añade esta sección a tu archivo `.vimrc`, preferiblemente al principio. Aquí es donde listarás todos los plugins que quieras usar.

Vim Script

```js
" =============================================================================
"  GESTIÓN DE PLUGINS CON VIM-PLUG
" =============================================================================

call plug#begin('~/.vim/plugged')

" Aquí se listan los plugins. Ejemplos:

" 1. Un explorador de archivos (el árbol de directorios)
Plug 'preservim/nerdtree'

" 2. Una barra de estado mejorada
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'

" 3. Un tema de colores popular
Plug 'dracula/vim', { 'as': 'dracula' }

" 4. Comentar código fácilmente
Plug 'tpope/vim-commentary'

" ... añade más plugins aquí

" Finaliza la sección de plugins
call plug#end()
```

#### Paso 3: Instalar los Plugins

1. **Guarda** tu archivo `.vimrc` (`:w`).
2. **Vuelve a cargar** tu `.vimrc` sin salir de Vim escribiendo `:so %` o simplemente reinicia Vim.
3. Ejecuta el comando para instalar los plugins que listaste:

```
:PlugInstall
```

Vim-plug abrirá una nueva ventana y comenzará a descargar e instalar cada plugin. Una vez terminado, presiona `q` para cerrar esa ventana.

---
---

### 4. Configuración de Plugins Populares

Ahora que tienes los plugins, necesitas configurar sus atajos de teclado y opciones. Añade esta sección a tu `.vimrc`, después del bloque de `plug#end()`.

```js
" =============================================================================
"  CONFIGURACIÓN DE PLUGINS
" =============================================================================

" --- NERDTree (Explorador de archivos) ---
" Abre NERDTree con Ctrl + n
nnoremap <C-n> :NERDTreeToggle<CR>

" --- Vim-Airline (Barra de estado) ---
" Activa la fuente de poder para una mejor apariencia
let g:airline_powerline_fonts = 1
" Establece un tema para la barra
let g:airline_theme = 'dracula'

" --- Dracula (Tema de colores) ---
" Establece el tema de colores y activa el fondo oscuro
set background=dark
colorscheme dracula

" --- Vim-Commentary ---
" Ahora puedes comentar líneas de código usando 'gcc' en modo normal,
" o seleccionando varias líneas y usando 'gc'.
```

### Resumen del Flujo de Trabajo

1. **Encuentra un plugin** que te interese (por ejemplo, en [Vim Awesome](https://vimawesome.com/)).
2. **Añádelo** a la sección `plug#begin()`...`plug#end()` de tu `.vimrc`.
3. **Abre Vim y ejecuta** `:PlugInstall`.
4. **Lee la documentación del plugin** para ver sus opciones y atajos.
5. **Añade la configuración personalizada** para ese plugin en tu `.vimrc`.

Esta guía te proporciona una base sólida y funcional. El mundo de la configuración de Vim es vasto; te animo a explorar diferentes plugins, temas de colores y ajustes para crear el editor perfecto para ti.

---


