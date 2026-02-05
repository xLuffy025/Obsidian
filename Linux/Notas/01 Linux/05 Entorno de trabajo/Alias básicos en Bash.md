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

## Relacionado:
[[Bash vs sh vs Zsh]]

