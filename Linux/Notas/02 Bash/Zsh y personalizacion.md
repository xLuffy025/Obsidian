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
## Relacionado:
[[Powerlevel10k]]

