
## CONFIGURAR SSH y GitHub (cliente y servidor)

Configurar una clave SSH es la mejor manera de trabajar con GitHub para no tener que introducir tu usuario y contraseña cada vez que haces un cambio.

Aquí tienes los pasos exactos para generar la clave y conectarla a tu cuenta.

--------------------------------------------------------------------------

### Paso 1: Generar la clave SSH

Abre tu terminal (o Termux/Git Bash) y ejecuta el siguiente comando. Asegúrate de usar el correo electrónico asociado a tu cuenta de GitHub:

### 🔹 Cliente SSH (todos)
```bash
ssh-keygen -t ed25519 -C "jose@linux"
```

1. Cuando te pregunte dónde guardar la clave (`Enter file in which to save the key`), simplemente presiona **Enter** para usar la ubicación por defecto.

2. Te pedirá una frase de contraseña (`passphrase`). Puedes escribir una para extra seguridad o dejarlo en blanco y presionar **Enter** dos veces para no usar contraseña.
### Paso 2: Activar el agente SSH (Opcional pero recomendado)
Esto asegura que el sistema recuerde tu clave durante la sesión.

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

### Paso 3: Copiar tu clave pública

Necesitas copiar el contenido de tu clave pública para pegarlo en GitHub. Ejecuta este comando para ver la clave:
### 🔹 GitHub / GitLab
```bash 
cat ~/.ssh/id_ed25519.pub
```
Se mostrará un texto largo que empieza con `ssh-ed25519` y termina con tu correo. **Copia todo ese texto.**

### Paso 4: Agregar la clave a GitHub

1. Ve a [GitHub.com](https://github.com) e inicia sesión.
2. Haz clic en tu foto de perfil (arriba a la derecha) y selecciona **Settings** (Configuración).
3. En el menú de la izquierda, busca y haz clic en **SSH and GPG keys**.
4. Haz clic en el botón verde **New SSH key**
5. **Title:** Ponle un nombre para identificar tu dispositivo (ej: "Mi PC" o "Termux").
6. **Key type:** Déjalo en "Authentication Key".
7. **Key:** Pega el texto que copiaste en el Paso 3.
8. Haz clic en **Add SSH key**.
### Paso 5: Probar la conexión

Vuelve a tu terminal y ejecuta:
```bash 
ssh -T git@github.com
```

- Si te pregunta `Are you sure you want to continue connecting?`, escribe `yes` y presiona Enter.
- Deberías ver un mensaje como:
> 	- "Hi [TuUsuario]! You've successfully authenticated, but GitHub does not provide shell access."
    
---
## 🔄 Sincronizar repositorios

1. **Clonar un repositorio con SSH:**
- Ve a la página principal del repositorio que quieres descargar en GitHub.
- Haz clic en el botón verde **Code**.
- **Importante:** Selecciona la pestaña que dice **SSH**.
- Copia la dirección que aparece. Debería empezar con `git@github.com:...`.

```bash
git clone git@github.com:usuario/repositorio.git
```

2. **Configurar el remoto en un repo existente:**
- Abre tu terminal y navega a la carpeta donde quieres guardar el proyecto. Luego escribe `git clone` y pega la dirección que copiaste.
- El comando se verá así:
```bash
git remote set-url origin git@github.com:usuario/repositorio.git
```

3. **Verificar la descarga**
Una vez que termine, entra en la carpeta que se acaba de crear:

```bash
cd NombreDelRepositorio
ls
```

4. **Subir cambios:**

```bash
git add .
git commit -m "mensaje claro"
git push origin main
```

5. **Traer cambios del remoto:**
```bash
git pull origin main
```

## ⚙️ Tips prácticos para tu estilo de trabajo

- Puedes crear un **script modular** que automatice `git add`, `commit` y `push` con mensajes dinámicos.
- Si trabajas en **Termux**, asegúrate de tener instalado `openssh` y `git`:
```bash
pkg install openssh git
```

- Para mayor claridad, usa colores en tu prompt (`PS1`) y alias como:
```bash
# Alias Github
alias gs='git status'
alias ga='git add .'
alias gc='git commit -m'
alias gp='git push'
alias gpo='git push origin'
alias gpl='git pull'
alias gco='git checkout'
alias gl='git log --oneline --graph --decorate'
alias gundo='git reset --soft HEAD~1'

alias gpush="git push origin main"
alias gpull="git pull origin main"
```

***

## 🔹 Servidor SSH
#### WSL ✅
```bash
sudo apt install openssh-server
sudo service ssh start
```

#### proot ❌ (no recomendado)
- Usa **SSH cliente**
- O usa **Termux + openssh** fuera del proot
------------------------------------------------------------
## 7️⃣ CONFIGURAR GIT (OBLIGATORIO)

```bash 
git config --global user.name "xLuffy025"
git config --global user.email "dimas.j0511@outlook.com"
git config --global init.defaultBranch main
git config --global pull.rebase false
```
**Alias útiles:** 
```bash 
git config --global alias.st status 
git config --global alias.co checkout
git config --global alias.cm "comit -m"
```


