# Git : Les commits

[> Revenir au sommaire Git](./git.md)

Permets d'enregistrer les modifications dans le dépôt.

## Connaître les fichiers modifiés récemment non comité ou indexé

```bash
git status
```

## Connaître les modifications apportées à un ou plusieurs fichiers

```bash
git diff
```

Il est possible de spécifier un fichier après `diff` :

```bash
git diff fichier1
```

## Ajouter des fichiers à prendre en compte lors du prochain commit (indexé)

Ajouter des fichiers modifiés spécifiques :

```bash
git add fichier1 fichier2
```

Ajouter tous les fichiers modifiés :

```bash
git add *
```

## Sauvegarder vos changements indexé (commit)

### Commit avec un message de validation

```bash
git commit -m "Message court sur les modifications apportées"
```

### Raccourci de `git add` + `git commit`

Inclut tous les fichiers listés dans `git status` :

```bash
git commit -a
```

Indique précisément quels fichiers inclure dans le commit :

```bash
git commit fichier1 fichier2
```

## Afficher l'historique des commits (les logs)

Visualiser les différents commits de la branche active.

```bash
git log
```

Options utiles: `-p` ou `–stat`

Afficher les logs des 3 derniers commits :

```bash
git log -n 3
```

Afficher les logs d'une branche :

```bash
git log nomBranche
```

## Modifier un commit

### Modification du dernier commit non push sur le serveur (local)

```bash
git commit –amend
```

### Fusionner/regrouper plusieurs commits local

On souhaite squasher nos commits qui se suivent dans l’historique, sur la même branche.

Très utile si un commit à été fait, mais il y a une modification manquante. (ex. fichier manquant, erreur de syntaxe).

On peut cibler les commits avec plusieurs méthodes :

- Prendre en compte les 3 derniers commits :

  ```bash
  git rebase -i HEAD~3
  ```

- Prendre en compte à partir d'un commit spécifique en ciblant le HASH du commit précédant

  ```bash
  git rebase -i idCommit
  ```

On entre alors en mode interactif (on utilise l’éditeur de git). Les commits sont affichés du plus ancien au plus récent.

Exemple :

```bash
pick  fbde9fd   Add Readme.md
pick  70aaed5   Update Readme
pick  ccf2779   Update Readme again
pick  8c706b5   Update Readme again and again
```

Le premier commit correspond à celui de base, celui que l’on souhaite conserver ; on laisse donc l’instruction `pick` devant. On souhaite squasher tous les commits suivants, on met donc l’instruction `squash` devant. (vous pouvez aussi utiliser l’alias `s` à la place de `squash`)

On obtient alors :

```bash
pick    fbde9fd Add Readme.md
squash  70aaed5 Update Readme
squash  ccf2779 Update Readme again
squash  8c706b5 Update Readme again and again
```

Concrètement, on dit à GIT de se baser sur le premier commit et on lui applique tous les suivants pour n’en faire qu’un seul.

Lorsque l’on valide le squash (on quitte le mode interactif), Git vas réappliquer les commits dans le même ordre qu’ils aient été configurés juste avant. On met alors un message de commit qui concerne le regroupement de nos commits et c’est tout.

On peut ensuite vérifier toujours à l’aide de la commande git que nos commits ont bien été squashés. Il ne vous reste plus qu'à pousser vos modifications :

```bash
git push origin master --force
```

> Note : Pensez à bien utiliser l’option `-–force` car le rebase doit écraser l’ancien historique des commits. Attention, l’option `--force` ne doit être utilisée que sur votre propre fork !

## Annuler un commit

### Annuler le dernier commit

Les fichiers restent modifiés :

```bash
git reset HEAD^
```

Les changements effectués dans les fichiers seront perdus :

```bash
git reset –hard HEAD^
```

### Annuler un commit publié

```bash
git revert idDuCommit
```

## Restaurer un commit

### Restaurer un fichier à son état lors du dernier commit

```bash
git checkout fichierName
```

## Ajouter un tag

### Répertorier les tags

```bash
git tag
```

### Créer un tag

```bash
git tag nomTag
```

### Créer un tag annoté

```bash
git tag -a nomTag
```

### Tagger un commit

```bash
git tag nomTag idCommit
```

### Partager les tags vers le dépôt distant

```bash
git push origin nomTag
```

### Consulter l'état d'un dépôt à un tag donné

```bash
git checkout nomTag
```

### Supprimer un tag

```bash
git tag -d nomTag
```

## Convention de nommage

- [Conventionalcommits.org [FR]](https://www.conventionalcommits.org/fr/v1.0.0/)

## Sauvegarder un dossier vide

Par défaut un dossier vide ne peut être versionné. Pour remédier à cela, il existe une convention de nommage d'un fichier temporaire nommé "**.gitkeet**" que l'on ajoute au dossier pour le versionner.

## Ignorer des fichiers ou dossiers spécifiques

Pour ignorer des fichiers ou dossiers du versionning afin de ne pas sauvegarder par exemple des fichiers temporaires.

On créer un fichier "**.gitignore**" :

```gitignore
*.log
cache/*
!/cache/.gitkeep
```

Dans l'exemple ci-dessus on exclut les fichiers avec l'extension `.log`, tous les fichiers inclus dans le dossier `cache/` sauf le fichier `.gitkeep`.

## Ressources complémentaires

- [Git Status (git-scm.com) [EN]](https://git-scm.com/docs/git-status)
- [Git Diff (git-scm.com) [EN]](https://git-scm.com/docs/git-diff)
- [Git Add (git-scm.com) [EN]](https://git-scm.com/docs/git-add)
- [Git Commit (git-scm.com) [EN]](https://git-scm.com/docs/git-commit)
- [Git Log (git-scm.com) [EN]](https://git-scm.com/docs/git-log)
- [Git Rebase (git-scm.com) [EN]](https://git-scm.com/docs/git-rebase)
- [Git Reset (git-scm.com) [EN]](https://git-scm.com/docs/git-reset)
- [Git Revert (git-scm.com) [EN]](https://git-scm.com/docs/git-revert)
- [Git Checkout (git-scm.com) [EN]](https://git-scm.com/docs/git-checkout)
- [Git Tag (git-scm.com) [EN]](https://git-scm.com/docs/git-tag)
