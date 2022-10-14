# La configuration des raccourcies de commande Git (alias)

[> Revenir au sommaire Git](./git.md)

## Via le fichier **.gitconfig**

Commande de base :

```bash
git config --global alias.ci commit
git config --global alias.co checkout
git config --global alias.st status
git config --global alias.br branch
```

Et pour simplifier la lisibilité des logs :

```bash
git config --global alias.lg "log --graph --date=relative --pretty=tformat:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%an %ad)%Creset'"
git config --global alias.l "log --oneline --graph"
```

Ou bien encore pour annuler la dernière livraison, mais garder les fichiers modifiés :

```bash
git config --global alias.uncommit "reset --soft HEAD~1"
```

Rendu dans le fichier `.gitconfig` :

```.gitconfig
[alias]
  ci = commit
  co = checkout
  st = status
  br = branch
  lg = log --graph --date=relative --pretty=tformat:'%Cred%h%Creset -%C(auto)%d%Creset %s %Cgreen(%an %ad)%Creset'
  l = log --oneline --graph
  uncommit = reset --soft HEAD~1
```

## Via le fichier **.bash_profile**

Exemple :

```.bash_profile
alias gco="git checkout"
alias gl="git log --oneline --graph"
```

Contrairement à la précédente solution qui est plus courante ici l'exécution du programme "git" est incluse dans l'alias. Cela signifie que vous n'aurez qu'à taper `gl` pour exécuter la commande complète de `git log --oneline --graph`.

## Ressources complémentaires

- [Git Alias with Arguments [EN]](https://mikebarkas.dev/2018/git-alias-bash-functions-with-arguments/)
- [Kittygiraudel git-aliases](https://kittygiraudel.com/snippets/git-aliases/)
