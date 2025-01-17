# Docker - `exec` and co. 

```
# Execute command inside a container
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

# delete /tmp/somefile in container
docker exec mycontainer rm /tmp/somefile

# need help?
docker exec -h 
```

## Exercices

Lancer un container `httpd:alpine` exposant `8083:80` et y
**ouvrir une session shell interactive** avec **pseudo-TTY** et explorer le système de fichier (i.e. filesystem ou FS)

- le résultat est équivalent à ouvrir une session SSH sur une machine virtuelle... même si le fonctionnement n'a absolument rien à voir
- le FS de votre container est-il le même que celui de votre machine? 

---

Modifier le fichier `htdocs/index.html` dans le container et vérifier ce que renvoi `localhost:8083`

- Utiliser une commande `echo "Test content" > index.html` ou `vi`
- Que se passe-t-il si on lance un autre container utilisant la même image? Lancer un autre container `httpd:alpine` exposant `8084:80` et comparer!

---

Lister les process du container lancé précédemment **depuis le container lui-même**. Vérifier si ce même processus est visible depuis la machine hôte. 

- `ps -ef` permet d'afficher les processus machine et/ou du container
- `pstree -p` permet d'afficher l'ensemble des process sous forme d'arbre parent/enfant

