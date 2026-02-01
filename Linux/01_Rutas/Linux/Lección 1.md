# {{Linux día 1}}

## 🎯 Objetivo
-  Aprender a instalar Linux en WSL (Windows) y TERMUX(proot-distro) en Android

## 🕒 Duración estimada
- 

## 📚 Recursos
- web

## 📝 Notas clave
- # 🧠 IDEA CLAVE (léela primero)

Una distro “100% funcional” no significa _root real_, sino:

1. **Sistema actualizado**
2. **Usuario correcto**
3. **Herramientas base**
4. **Red, SSH y Git**
5. **Entorno de trabajo**
6. **Automatización y backups**
7. **Buenas prácticas de seguridad**   

Si haces esto bien, **proot y WSL funcionan casi igual que un Linux real**.

##  DIFERENCIAS IMPORTANTES (proot vs WSL)

| Tema            | proot-distro (Termux) | WSL                       |
| --------------- | --------------------- | ------------------------- |
| Root real       | ❌ No (root falso)     | ✅ Sí                      |
| systemd         | ❌ No                  | ✅ (WSL2)                  |
| SSH server      | ⚠️ Limitado           | ✅ Completo                |
| Puertos         | Limitados             | Normales                  |
| Rendimiento     | Medio                 | Alto                      |
| Uso recomendado | Desarrollo, scripts   | Desarrollo serio / server |

## ✅ Requisitos previos

Antes de instalar WSL, asegúrate de que tu sistema cumple con lo siguiente:

- Windows 10 versión **2004** o superior (compilación **19041+**) **o** cualquier versión de Windows 11.
- Permitir virtualización en BIOS/UEFI (normalmente ya viene activada).

## 🧪 Ejercicios

#  Instalar WSL en Windows y PROOT-DISTRO en Android desde Termux
###  🐧Cómo instalar en Android con Termux(proot-distro)

``` bash
pkg install proot-distro
proot-distro install ubuntu
proot-distro login ubuntu`
```

--------------------------------------------------------------------------
### 🐧 Cómo instalar WSL en Windows (Guía rápida y completa)
### 🚀 Instalación rápida (método recomendado)

Microsoft simplificó todo a **un solo comando**:

#### 1. Abre **PowerShell como administrador**

- Clic derecho en Inicio → **Windows PowerShell (Admin)** o **Terminal de Windows (Admin)**.
```powershell
wsl --install
```
##### Este comando hará lo siguiente automáticamente:

- Habilitar las características necesarias de Windows.
- Instalar WSL 2.
- Instalar Ubuntu como distribución predeterminada.
#### 3. Reinicia tu computadora

Windows te lo pedirá para completar la instalación.

## 🧩 Elegir otra distribución (opcional)
**Si no quieres Ubuntu, puedes ver la lista de distribuciones disponibles:**
```powershell
wsl --list --online
```

**E instalar una específica:**
```powershell
wsl --intall -d <NombreDistro>
```

**Ejemplo**:
```powershell
wsl --install -d Debian
```

## 🛠️ Primer inicio de Linux

Cuando abras tu distro por primera vez:

- Se descomprimirá e instalará (solo la primera vez).
- Te pedirá crear un **usuario** y **contraseña** de Linux
#### 🧪 Verificar que WSL está funcionando

```powershell
wsl --status
```

### 📌 Notas útiles

- Si la instalación se queda en **0%**, Microsoft recomienda usar:
```powershell
wsl --install --web-dowload -d <Distro>
```
- Puedes desinstalar la distribuciones sin afectar WSL completo.

--------------------------------------------------------------------------
###  ACTUALIZAR SISTEMA (PASO OBLIGATORIO)

Debian / Ubuntu
```bash 
sudo apt update && sudo apt upgrade -y
```
ArchLinux
```bash 
sudo pacman -Syu
```
Fedora 
```bash
def upgrade -y
```

##  USUARIOS: ¿root o usuario normal?

### 🔴 REGLA DE ORO

- **Root solo para instalar y configurar**
- **Usuario normal para trabajar**
**Crear usuario (en todas las distros)**
```bash 
useradd -m -s /bin/bash jose
passwd jose
```

**Agregar a sudo:**
```bash 
usermod -aG sudo jose # DEbian/Ubuntu
usermod -aG wheel jose # Arch/Fedora
```
**Editar sudoers (si hace falta)**
```bash 
EDITOR=nano visudo
```
**Descomenta:**
```bash 
%whell ALL=(ALL) ALL
```
**Cambiar a usuario:**
```bash 
su - jose
```
⚠️ **En proot**: root no es peligroso, pero acostúmbrate bien desde el inicio.

------------------------------------------------------------
##  PAQUETES ESENCIALES (BASE UNIVERSAL)

### 📦 Imprescindibles
```bash
# Debian / Ubuntu
sudo apt install -y \
  build-essential curl wget git vim nano \
  ca-certificates unzip zip htop \
  python3 python3-pip \
  openssh rsync tmux neofetch
```

```bash 
# Arch
sudo pacman -S --needed \
  base-devel curl wget git vim nano \
  unzip zip htop python python-pip \
  openssh rsync tmux neofetch
```

```bash 
# Fedora
sudo dnf install -y \
  @development-tools curl wget git vim nano \
  unzip zip htop python3 python3-pip \
  openssh rsync tmux neofetch
```

------------------------------------------------------------

------------------------------------------------------------
##  SHELL PRODUCTIVO (Bash bien hecho)
**Instala:**
```bash 
sudo apt install bash-completion
```
**edita `~/.bashrc 0 ~/.zshrc`:**
```bash 
#Alias basicos
alias ll='lsd -lh --group-dirs=first'
alias la='lsd -a --group-dirs=first'
alias l='lsd --group-dirs=first'
alias lla='lsd -lha --group-dirs=first'
alias ls='lsd --group-dirs=first'
alias cat='bat'

alias lls='ls -la'
alias cls='clear'
alias gs='git status'
alias py='python'
alias nv='nvim'


```

**Recarga:**
```bash
source ~/.bashrc #bash
source ~/.zshrc #zsh
```

-----------------------------------------------------------

## 🔥 CONCLUSIÓN

Si sigues este flujo:

**Instalar → actualizar → usuario → paquetes → [[Ssh - Git]] → [[Shell]] → [[Tmux]] → [[Vim y Neovim con (NvChad)]] → proyectos**

👉 Puedes **moverte de Ubuntu a Arch o Fedora sin miedo**  
👉 Puedes **replicar tu sistema en otro dispositivo en minutos**  
👉 Puedes trabajar **igual en Termux, WSL o Linux real**


## 📤 Entregable
- Terminal Funcionando

## 🔗 Enlaces relacionados
- [[Linux]]

## 🏷️ Estado
#proceso

