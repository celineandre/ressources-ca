# Git : Les branches

[> Revenir au sommaire Git](./git.md)

## Afficher la liste des branches disponible

> Il y a une étoile devant la branche où l'on se trouve.

Liste des branches en local :

```bash
git branch
```

Afficher la liste de toutes les branches locale et distante :

```bash
git branch -a
```

## Création d'une branche

```bash
git branch nomBranche
```

### Renommer une branche

```bash
git branch --move nomBrancheOld nomBrancheNew
git push --set-upstream origin nomBrancheNew
git push origin --delete nomBrancheOld
```

## Se déplacer sur une autre branche

```bash
git checkout nomBranche
```

> Fonctionne seulement s’il n'y a pas de modifications sur les fichiers en cours.

## Sauvegarder le travail en cours

Cela met de côté les fichiers en cours de modification sans les comités afin de permettre de changer de branche pour par exemple effectuer un correctif rapide.

```bash
git stash
```

### Récupérer le travail sauvegardé

```bash
git stash apply
```

### Lister le travail sauvegardé

```bash
git stash list
```

## Fusionner une branche dans la branche où l'on se trouve

```bash
git merge nomBranche
```

## Supprimer une branche

### Supprimer une branche en local

```bash
git branch -d nomBranche
```

Avant de supprimer une branche locale, assurez-vous de passer à une autre branche que vous ne voulez PAS supprimer.

De plus la branche que l'on souhaite supprimer ne doit pas comporter des changements non fusionnés et des commits non poussés. Si malgré tous on souhaite forcer la suppression de la branche on aura :

```bash
git branch -D nomBranche
```

> Attention : le travail sur cette branche sera entièrement perdu.

### Supprimer une branche à distance (origin)

```bash
git push origin -d nomBranche
```

## Ressources complémentaires

- [Git Stash (git-scm.com) [EN]](https://git-scm.com/docs/git-stash)
- [Utilitaires Git - Remisage et nettoyage (git-scm.com) [EN]](https://git-scm.com/book/fr/v2/Utilitaires-Git-Remisage-et-nettoyage)
- [Git Checkout (git-scm.com) [EN]](https://git-scm.com/docs/git-checkout)
