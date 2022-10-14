# Le dépôt Git

[> Revenir au sommaire Git](./git.md)

## Pour créer un nouveau dépôt en local sur son poste

Pour initialisation du dépôt, il suffit de créer un dossier puis dans le terminal à la racine du dossier d'exécuter la commande ci-dessous :

```bash
git init
```

## Cloner un dépôt distant existant

C'est l'action de récupérer une copie d'un dépôt distant sur son poste.

Plusieurs formats sont possibles :

- ssh
- git
- https
- ftp

- [Git Clone (git-scm.com) [EN]](https://git-scm.com/docs/git-clone/)

## Récupérer les nouveautés présentes sur le serveur distant

Intègre les modifications d’un dépôt distant dans la branche actuelle :

```bash
git pull
```

- [Git Pull (git-scm.com) [FR]](https://git-scm.com/docs/git-pull/fr)

## Envoyer ses propres modifications sur le serveur distant

Intègre les modifications de la branche dans celle du dépôt distant :

```bash
git push
```

ou

```bash
git push origin
```

- [Git Push (git-scm.com) [FR]](https://git-scm.com/docs/git-push/fr)

## Ajouter un dépôt dans un autre (Submodules)

```bash
git submodule <url>
```

- [Les submodules (git-scm.com) [FR]](https://git-scm.com/docs/git-submodule/fr)
- [Comprendre et maîtriser les Submodules Git [FR]](https://delicious-insights.com/fr/articles/git-submodules/)
- [How To Add and Update Git Submodules [EN]](https://devconnected.com/how-to-add-and-update-git-submodules/)
