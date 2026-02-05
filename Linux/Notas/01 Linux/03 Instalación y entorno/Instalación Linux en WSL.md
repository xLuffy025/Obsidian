## ✅ Requisitos previos

Antes de instalar WSL, asegúrate de que tu sistema cumple con lo siguiente:

- Windows 10 versión **2004** o superior (compilación **19041+**) **o** cualquier versión de Windows 11.
- Permitir virtualización en BIOS/UEFI (normalmente ya viene activada).

## 🐧 Cómo instalar WSL en Windows (Guía rápida y completa)
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

>[!warning] Reinicia tu computadora


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

>[!tip] Verificar que WSL está funcionando

```powershell
wsl --status
```

>[!info] Si la instalación se queda en **0%**, Microsoft recomienda usar:

```powershell
wsl --install --web-dowload -d <Distro>
```

>[!info] Puedes desinstalar la distribuciones sin afectar WSL completo.

## Relacionado:
[[WSL vs proot-distros]]
