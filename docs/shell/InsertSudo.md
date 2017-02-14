## à mettre dans le bashrc Permet de gagner du temps avec le sudo juste avant, quand on l'oublie, meh!


```bash
insert_sudo () { zle beginning-of-line; zle -U "sudo " }
zle -N insert-sudo insert_sudo
bindkey "^[s" insert-sudo
```
