
## USUARIOS: ¿root o usuario normal?

### 🔴 REGLA DE ORO

- Root solo para instalar y configurar
- Usuario normal para trabajar

**Crear usuario (en todas las distros)**
```bash 
useradd -m -s /bin/bash xluffy025
passwd xluffy025
```

**Agregar a sudo:**
```bash 
usermod -aG sudo xluffy025 # DEbian/Ubuntu
usermod -aG wheel xluffy025 # Arch/Fedora
```

**Editar sudoers (si hace falta)**
```bash 
EDITOR=nvim visudo
```

**Descomenta:**
```bash 
%whell ALL=(ALL) ALL
```

**Cambiar a usuario:**
```bash 
su - jose
```

>[!warning] **En proot**: root no es peligroso, pero acostúmbrate bien desde el inicio.

## Relacionado:

[[Instalación Linux en WSL]]
[[Instalación Linux en Termux con proot-distro]]
