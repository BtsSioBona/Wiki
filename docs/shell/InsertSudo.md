## insert sudo en début de commande avec un simple Alt+S


```bash
insert_sudo () { zle beginning-of-line; zle -U "sudo " }
zle -N insert-sudo insert_sudo
bindkey "^[s" insert-sudo
```
