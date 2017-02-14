### Permet de remonter dans l'arborescence plus facilement ( cd *2 remonte de deux )

```bash
## cd .. * param ( default 1 )
up() {
    if [[ "$#" < 1 ]] ; then
        cd ..
    else
        CDSTR=""
        for i in {1..$1} ; do
            CDSTR="../$CDSTR"
        done
        cd $CDSTR
    fi
}
```
