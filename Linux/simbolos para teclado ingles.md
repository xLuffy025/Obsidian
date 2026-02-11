### 🧠 Opción rápida: Alt Code (Windows)

Si estás en Windows, puedes usar el código Alt:

- **Ñ mayúscula**: Mantén presionada la tecla `Alt` y escribe `0209` en el teclado numérico → **Ñ**
  
- **ñ minúscula**: Mantén presionada la tecla `Alt` y escribe `0241` → **ñ**

> ⚠️ Esto solo funciona si tienes un teclado numérico o activas el Num Lock.

### 🌐 Opción universal: Código HTML o Unicode

Ideal si estás programando o escribiendo en HTML:

- `&ntilde;` → **ñ**
 
- `&Ntilde;` → **Ñ**   

- Unicode: `\u00F1` para **ñ**, `\u00D1` para **Ñ**

---
### ⌨️ Opción práctica: Remapear teclas o usar scripts

Ya que tú dominas Termux y personalización avanzada, podrías:

- Crear un script en Termux que inserte `ñ` con una combinación personalizada (por ejemplo, `Ctrl+n`)

- Usar una app como [External Keyboard Helper Pro] o configurar `keylayout` para redefinir teclas
 
---
### 🧩 Opción 1: Usar la tecla Compose

La tecla **Compose** te permite escribir caracteres especiales con combinaciones simples.

#### ✅ Cómo activarla:

1. Edita tu archivo de configuración del teclado:

```bash
localectl set-x11-keymap us pc105 "" compose:ralt
```
   
Esto asigna la tecla **Alt derecha** como Compose.
   
2. Reinicia tu sesión gráfica o ejecuta:

```bash
setxkbmap -option compose:ralt
```
### 🧙‍♂️ Cómo usarla:

- Presiona `Alt derecha` (Compose), luego `~` y `n` → **ñ**
  
- Para **Ñ**: `Alt derecha`, `~`, `Shift+n`

---
### 🧠 Opción 2: Usar Unicode directamente

En muchas terminales o editores (como Vim, VSCode, etc.), puedes insertar Unicode:

- Presiona `Ctrl+Shift+u`, luego escribe `00f1` → **ñ**

- Para **Ñ**: `Ctrl+Shift+u`, luego `00d1`

---
### 🛠️ Opción 3: Cambiar el layout temporalmente

Si prefieres usar el layout español por momentos:

```bash
setxkbmap es
```

Y para volver al inglés:

```bash
setxkbmap us
```

>[!nota] También puedes crear un script para alternar entre layouts con un solo comando.

---
### ⚙️ Opción 4: Personalizar con Xmodmap (avanzado)

Ya que tú dominas configuraciones profundas, puedes mapear una tecla específica a `ñ` usando `.Xmodmap`. Ejemplo:

```bash
keycode 48 = n N ntilde Ntilde
```

Esto requiere saber el keycode exacto (puedes usar `xev` para identificarlo).

---
### 🧠 Opción 1: Insertar Unicode directamente en Neovim

Neovim permite insertar caracteres Unicode en modo **insert**:

- En modo **insert**, presiona: `Ctrl-v` seguido de `u00f1` → **ñ** `Ctrl-v` seguido de `u00d1` → **Ñ**
    

>[!tip] Este método funciona en la mayoría de terminales compatibles con Unicode.

### 🧩 Opción 2: Usar la tecla Compose en tu sistema

Si ya configuraste la tecla Compose (como `Alt derecha`), puedes usarla dentro de Neovim:

- `Compose` + `~` + `n` → **ñ**

- `Compose` + `~` + `Shift+n` → **Ñ**
  

Si no está activa, puedes habilitarla con:

```bash
setxkbmap -option compose:ralt
```

---
### ⚙️ Opción 3: Mapeo personalizado en Neovim

Ya que tú dominas configuraciones avanzadas, puedes crear un **atajo personalizado** en tu `init.lua` o `init.vim` para insertar `ñ` con una combinación de teclas:

#### Ejemplo en Lua:

```lua
vim.keymap.set('i', '<C-n>', 'ñ', { noremap = true })
vim.keymap.set('i', '<C-N>', 'Ñ', { noremap = true })
```

Esto te permite escribir `ñ` con `Ctrl+n` en modo insert. Súper útil si estás codificando en HTML o escribiendo contenido en español.

---
### 🛠️ Opción 4: Snippets con LuaSnip

Si usas LuaSnip, puedes crear un snippet para insertar `ñ` automáticamente:

```lua
s("nn", t("ñ")),
s("NN", t("Ñ")),
```

Así, escribir `nn` se convierte en `ñ`. Minimalismo total.

¿Quieres que te ayude a integrar esto en tu launcher HTML o backend Python para que puedas escribir `ñ` desde tu interfaz personalizada? Podríamos hacer algo elegante con un botón que simule la entrada.

---
### 🔤 Letras con acento y caracteres latinos

| Carácter | Combinación (Compose Key) | Unicode  |
| -------- | ------------------------- | -------- |
| á        | `Compose` + `'` + `a`     | `\u00E1` |
| é        | `Compose` + `'` + `e`     | `\u00E9` |
| í        | `Compose` + `'` + `i`     | `\u00ED` |
| ó        | `Compose` + `'` + `o`     | `\u00F3` |
| ú        | `Compose` + `'` + `u`     | `\u00FA` |
| ñ        | `Compose` + `~` + `n`     | `\u00F1` |
| ü        | `Compose` + `"` + `u`     | `\u00FC` |
| ¿        | `Compose` + `?` + `?`     | `\u00BF` |
| ¡        | `Compose` + `!` + `!`     | `\u00A1` |

>[!tip] En terminales compatibles, también puedes usar `Ctrl+Shift+u` seguido del código Unicode.

---
### 🔣 Símbolos comunes del teclado en inglés

| Símbolo | Nombre en inglés       | Tecla o combinación         |                |
| ------- | ---------------------- | --------------------------- | -------------- |
| @       | At sign                | `Shift` + `2`               |                |
| #       | Hash / Pound           | `Shift` + `3`               |                |
| $       | Dollar                 | `Shift` + `4`               |                |
| %       | Percent                | `Shift` + `5`               |                |
| ^       | Caret                  | `Shift` + `6`               |                |
| &       | Ampersand              | `Shift` + `7`               |                |
| *       | Asterisk               | `Shift` + `8`               |                |
| ( )     | Parentheses            | `Shift` + `9` / `0`         |                |
| _       | Underscore             | `Shift` + `-`               |                |
| +       | Plus                   | `Shift` + `=`               |                |
| =       | Equal sign             | `=`                         |                |
| -       | Hyphen                 | `-`                         |                |
| ~       | Tilde                  | `Shift` + `` ` ``           |                |
| `       | Grave accent           | `` ` ``                     |                |
| "       | Double quotes          | `Shift` + `'`               |                |
| '       | Apostrophe             | `'`                         |                |
| :       | Colon                  | `Shift` + `;`               |                |
| ;       | Semicolon              | `;`                         |                |
|         | Less / Greater than    | `Shift` + `,` / `.`         |                |
| /       | Forward slash          | `/`                         |                |
| \       | Backslash              | `\\`                        |                |
|         |                        | Pipe / Vertical bar         | `Shift` + `\\` |
| [ ]     | Brackets               | `[` / `]`                   |                |
| { }     | Braces                 | `Shift` + `[` / `]`         |                |
| °       | Degree                 | `Compose` + `o` + `o`       |                |
| © ®     | Copyright / Registered | `Compose` + `c` + `o` / `r` |                |


---
### 🎯 ¿Qué tecla usar como Compose?

Las más comunes para asignar como Compose son:

- **Alt derecha** (`Right Alt` o `AltGr`)
- **Caps Lock** (si no la usas)
- **Menu key** (la que está entre Alt derecha y Ctrl derecha)
- **Scroll Lock** (en teclados extendidos)

### ⚙️ Cómo asignar la tecla Compose

Puedes hacerlo con este comando:

```bash
setxkbmap -option compose:ralt
```

Esto asigna **Alt derecha** como Compose. Si prefieres otra tecla, aquí tienes algunas opciones:

| Tecla       | Comando          |
| ----------- | ---------------- |
| Alt derecha | `compose:ralt`   |
| Caps Lock   | `compose:caps`   |
| Menu key    | `compose:menu`   |
| Scroll Lock | `compose:scroll` |

Ejemplo para usar Caps Lock como Compose:

```bash
setxkbmap -option compose:caps
```

### 🧠 Para hacerlo permanente

Agrega esta línea a tu archivo de inicio gráfico, por ejemplo en `.xprofile`, `.xinitrc` o en tu configuración de tu gestor de ventanas:

```bash
setxkbmap -option compose:ralt
```

---
### ⭐ **Resumen rápido**

En Windows puedes escribir cualquier letra acentuada o símbolo español usando **ALT + código numérico**. Ejemplo: **ALT + 160 → á**, **ALT + 168 → ¿**, **ALT + 164 → ñ**.

### 🇪🇸 **Acentos y letras del español**

## **Vocales acentuadas**

|Carácter|Código ALT|
|---|---|
|á|**ALT + 160**|
|é|**ALT + 130**|
|í|**ALT + 161**|
|ó|**ALT + 162**|
|ú|**ALT + 163**|
|Á|**ALT + 0193**|
|É|**ALT + 0201**|
|Í|**ALT + 0205**|
|Ó|**ALT + 0211**|
|Ú|**ALT + 0218**|

## **La letra ñ**

| Carácter | Código ALT    |
| -------- | ------------- |
| ñ        | **ALT + 164** |
| Ñ        | **ALT + 165** |

## **Signos de interrogación y exclamación**

| Carácter | Código ALT    |
| -------- | ------------- |
| ¿        | **ALT + 168** |
| ¡        | **ALT + 173** |

## **Diéresis (ü, Ü)**

| Carácter | Código ALT    |
| -------- | ------------- |
| ü        | **ALT + 129** |
| Ü        | **ALT + 154** |

### 🔣 **Otros símbolos útiles**

| Símbolo | Código ALT |
| ------- | ---------- |
| ©       | ALT + 184  |
| ®       | ALT + 169  |
| «       | ALT + 174  |
| »       | ALT + 175  |
| º       | ALT + 167  |
| ª       | ALT + 166  |

### 📝 **Notas importantes**

- Debes usar **teclado numérico** (no los números de arriba).
- Asegúrate de que **Num Lock esté activado**.
- En laptops sin teclado numérico, debes usar el **teclado numérico integrado** (Fn + teclas marcadas).

---

### 📘 **TABLA COMPLETA DE CARACTERES ESPECIALES (Windows + Linux + Unicode)**

## 🇪🇸 **1. Letras del español**

### **Vocales acentuadas**

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|á|ALT + 160|Compose + `'` + a|U+00E1|
|é|ALT + 130|Compose + `'` + e|U+00E9|
|í|ALT + 161|Compose + `'` + i|U+00ED|
|ó|ALT + 162|Compose + `'` + o|U+00F3|
|ú|ALT + 163|Compose + `'` + u|U+00FA|
|Á|ALT + 0193|Compose + `'` + A|U+00C1|
|É|ALT + 0201|Compose + `'` + E|U+00C9|
|Í|ALT + 0205|Compose + `'` + I|U+00CD|
|Ó|ALT + 0211|Compose + `'` + O|U+00D3|
|Ú|ALT + 0218|Compose + `'` + U|U+00DA|

---

### **La letra ñ**

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|ñ|ALT + 164|Compose + `~` + n|U+00F1|
|Ñ|ALT + 165|Compose + `~` + N|U+00D1|

---

### **Signos de interrogación y exclamación**

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|¿|ALT + 168|Compose + `?` + `?`|U+00BF|
|¡|ALT + 173|Compose + `!` + `!`|U+00A1|

---

### **Diéresis**

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|ü|ALT + 129|Compose + `"` + u|U+00FC|
|Ü|ALT + 154|Compose + `"` + U|U+00DC|

---

### 🔣 **2. Símbolos comunes**

| Símbolo | Windows (ALT) | Linux (Compose) | Unicode |
| ------- | ------------- | --------------- | ------- |
| ©       | ALT + 184     | Compose + c + o | U+00A9  |
| ®       | ALT + 169     | Compose + r + o | U+00AE  |
| ™       | ALT + 0153    | Compose + t + m | U+2122  |
| °       | ALT + 248     | Compose + o + o | U+00B0  |
| €       | ALT + 0128    | Compose + e + = | U+20AC  |
| £       | ALT + 156     | Compose + L + - | U+00A3  |
| ¥       | ALT + 157     | Compose + Y + - | U+00A5  |
| «       | ALT + 174     | Compose + < + < | U+00AB  |
| »       | ALT + 175     | Compose + > + > | U+00BB  |

---

### 🧰 **3. Métodos universales en Linux**

### **A) Unicode directo en terminal o Neovim**

En modo insert:

```
Ctrl + Shift + u
```

Luego escribes el código hex:

- `00BF` → ¿
- `00F1` → ñ
- `00E1` → á

Y presionas **Enter** o **Espacio**.

---

### **B) Digraphs de Vim/Neovim**

Activa digraphs:

```
:set digraph
```

Luego en modo insert:

```
Ctrl + K  ?I   → ¿
Ctrl + K  n~   → ñ
Ctrl + K  a'   → á
```

---

### **C) Compose Key en Linux**

Puedes asignarla así:

```
setxkbmap -option compose:ralt
```

Luego:

- `Compose` + `~` + `n` → ñ
- `Compose` + `?` + `?` → ¿
- `Compose` + `'` + `a` → á

---

### 📦 **4. Tabla lista para guardar en Obsidian**

Si quieres, te la convierto en:

- **Markdown limpio**
- **Tabla extendida**
- **Versión PDF**
- **Plantilla para tu vault**

Solo dime en qué formato la quieres y te la dejo lista para pegar.


---
### Caracteres especiales: Windows + Linux + Unicode

## 1. Vocales acentuadas

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|á|ALT + 160|Compose + `'` + a|U+00E1|
|é|ALT + 130|Compose + `'` + e|U+00E9|
|í|ALT + 161|Compose + `'` + i|U+00ED|
|ó|ALT + 162|Compose + `'` + o|U+00F3|
|ú|ALT + 163|Compose + `'` + u|U+00FA|
|Á|ALT + 0193|Compose + `'` + A|U+00C1|
|É|ALT + 0201|Compose + `'` + E|U+00C9|
|Í|ALT + 0205|Compose + `'` + I|U+00CD|
|Ó|ALT + 0211|Compose + `'` + O|U+00D3|
|Ú|ALT + 0218|Compose + `'` + U|U+00DA|

---

## 2. Letra ñ

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|ñ|ALT + 164|Compose + `~` + n|U+00F1|
|Ñ|ALT + 165|Compose + `~` + N|U+00D1|

---

## 3. Signos de interrogación y exclamación

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|¿|ALT + 168|Compose + `?` + `?`|U+00BF|
|¡|ALT + 173|Compose + `!` + `!`|U+00A1|

---

## 4. Diéresis

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|ü|ALT + 129|Compose + `"` + u|U+00FC|
|Ü|ALT + 154|Compose + `"` + U|U+00DC|

---

## 5. Símbolos comunes

|Símbolo|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|©|ALT + 184|Compose + c + o|U+00A9|
|®|ALT + 169|Compose + r + o|U+00AE|
|™|ALT + 0153|Compose + t + m|U+2122|
|°|ALT + 248|Compose + o + o|U+00B0|
|€|ALT + 0128|Compose + e + =|U+20AC|
|£|ALT + 156|Compose + L + -|U+00A3|
|¥|ALT + 157|Compose + Y + -|U+00A5|
|«|ALT + 174|Compose + < + <|U+00AB|
|»|ALT + 175|Compose + > + >|U+00BB|

---

## 6. Métodos universales en Linux

### Unicode directo

```
Ctrl + Shift + u
```

Luego escribir el código (ej. `00BF`) y confirmar.

### Digraphs en Vim/Neovim

```
Ctrl + K  ?I   → ¿
Ctrl + K  n~   → ñ
Ctrl + K  a'   → á
```

### Compose Key

Ejemplo para activar:

```
setxkbmap -option compose:ralt
```

---

### Tabla completa de caracteres especiales (Windows + Linux + Unicode)

### 1. Vocales acentuadas (español)

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|á|ALT + 160|Compose + `'` + a|U+00E1|
|é|ALT + 130|Compose + `'` + e|U+00E9|
|í|ALT + 161|Compose + `'` + i|U+00ED|
|ó|ALT + 162|Compose + `'` + o|U+00F3|
|ú|ALT + 163|Compose + `'` + u|U+00FA|
|Á|ALT + 0193|Compose + `'` + A|U+00C1|
|É|ALT + 0201|Compose + `'` + E|U+00C9|
|Í|ALT + 0205|Compose + `'` + I|U+00CD|
|Ó|ALT + 0211|Compose + `'` + O|U+00D3|
|Ú|ALT + 0218|Compose + `'` + U|U+00DA|

---

### 2. Letra ñ

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|ñ|ALT + 164|Compose + `~` + n|U+00F1|
|Ñ|ALT + 165|Compose + `~` + N|U+00D1|

---

### 3. Signos de interrogación y exclamación

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|¿|ALT + 168|Compose + `?` + `?`|U+00BF|
|¡|ALT + 173|Compose + `!` + `!`|U+00A1|

---

### 4. Diéresis

|Carácter|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|ü|ALT + 129|Compose + `"` + u|U+00FC|
|Ü|ALT + 154|Compose + `"` + U|U+00DC|

---

### 5. Símbolos tipográficos

| Símbolo     | Windows (ALT) | Linux (Compose) | Unicode |
| ----------- | ------------- | --------------- | ------- |
| ©           | ALT + 184     | Compose + c + o | U+00A9  |
| ®           | ALT + 169     | Compose + r + o | U+00AE  |
| ™           | ALT + 0153    | Compose + t + m | U+2122  |
| °           | ALT + 248     | Compose + o + o | U+00B0  |
| ·           | ALT + 250     | Compose + . + . | U+00B7  |
| — (em dash) | ALT + 0151    | Compose + - + - | U+2014  |
| – (en dash) | ALT + 0150    | Compose + - + . | U+2013  |
| «           | ALT + 174     | Compose + < + < | U+00AB  |
| »           | ALT + 175     | Compose + > + > | U+00BB  |

---

### 6. Símbolos matemáticos

|Símbolo|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|±|ALT + 241|Compose + + + -|U+00B1|
|×|ALT + 0215|Compose + x + x|U+00D7|
|÷|ALT + 0247|Compose + : + -|U+00F7|
|≤|ALT + 243|Compose + < + =|U+2264|
|≥|ALT + 242|Compose + > + =|U+2265|
|≠|ALT + 8800|Compose + ! + =|U+2260|
|∞|ALT + 236|Compose + 8 + 8|U+221E|
|√|ALT + 251|Compose + v + v|U+221A|
|∑|ALT + 228|Compose + S + S|U+2211|
|∫|ALT + 8747|Compose + f + f|U+222B|

---

### 7. Símbolos de programación

|Símbolo|Windows (ALT)|Linux (Compose)|Unicode|
|---|---|---|---|
|→|ALT + 26|Compose + - + >|U+2192|
|←|ALT + 27|Compose + < + -|U+2190|
|⇒|ALT + 8658|Compose + = + >|U+21D2|
|⇐|ALT + 8656|Compose + < + =|U+21D0|
|λ|ALT + 955|Compose + l + a|U+03BB|
|π|ALT + 227|Compose + p + i|U+03C0|
|Ω|ALT + 234|Compose + O + m|U+03A9|

---

### 8. Métodos universales en Linux

### Unicode directo

```
Ctrl + Shift + u
```

Escribir el código (ej. `00BF`) y confirmar.

### Digraphs en Vim/Neovim

```
Ctrl + K  ?I   → ¿
Ctrl + K  n~   → ñ
Ctrl + K  a'   → á
Ctrl + K  -:   → ÷
Ctrl + K  xx   → ×
Ctrl + K  oo   → °
```

### Activar Compose Key

```
setxkbmap -option compose:ralt
```

---
