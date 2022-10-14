# La configuration de Git

[> Revenir au sommaire Git](./git.md)

Les commandes ci-dessous vont modifier le fichier **.gitconfig**. Sur Windows celui-ci est stocké à la racine de son utilisateur.

Personnalisation de Git - Configuration de Git

## Configurer le pseudo et l'email

Ce sont les paramètres indispensables au bon focntionnement.

Configuration du **pseudo** :

```bash
git config --global user.name "pseudo"
```

ou

```bash
git config --global user.name "Prénom Nom"
```

Configuration du **mail** :

```bash
git config --global user.email votre-email@domaine.fr
```

Rendu dans le fichier `.gitconfig` :

```.gitconfig
[user]
  name = pseudo
  email = votre-email@domaine.fr
```

## Configurer les couleurs dans le terminal Bash

```bash
git config --global color.ui ui
git config --global color.diff auto
git config --global color.status auto
git config --global color.branch auto
git config --global color.interactive auto
```

Rendu dans le fichier `.gitconfig` :

```.gitconfig
[color]
  ui = true
  diff = auto
  status = auto
  branch = auto
  interactive = auto
```

On peut régler encore plus les styles souhaités :

```bash
git config --global color.branch.current "yellow reverse bold"
git config --global color.branch.local "white"
git config --global color.branch.remote "cyan"
git config --global color.branch.upstream "cyan"
git config --global color.diff.meta "yellow bold"
git config --global color.diff.frag "magenta bold"
git config --global color.diff.old "red bold"
git config --global color.diff.new "green bold"
git config --global color.status.added "green"
git config --global color.status.changed "magenta"
git config --global color.status.untracked "cyan"
```

Rendu dans le fichier `.gitconfig` :

```.gitconfig
[color "branch"]
  current = yellow reverse bold
  local = white
  remote = cyan
  upstream = cyan

[color "diff"]
  meta = yellow bold
  frag = magenta bold
  old = red bold
  new = green bold

[color "status"]
  added = green
  changed = magenta
  untracked = cyan
```

La couleur peut prendre les valeurs suivantes : `normal`, `black`, `red`, `green`, `yellow`, `blue`, `magenta`, `cyan` ou `white`. Si vous souhaitez ajouter un attribut de casse, les valeurs disponibles sont `bold` (gras), `dim` (léger), `ul` (underlined, souligné), `blink` (clignotant) et `reverse` (inversé).

## Forcer les retours à la ligne LF sur Windows

```bash
git config --global core.autocrlf true
```

## Configurer la branche "master" par défaut lorsque que l'on initialise un projet

Par défaut ce n'est plus la branch "main".

```bash
git config --global init.defaultBranch master
```

Rendu dans le fichier `.gitconfig` :

```.gitconfig
[init]
  defaultBranch = master
```

## Afficher les paramètres de Git

Liste de tous les paramètres :

```bash
git config --list
```

Liste des paramètres en global :

```bash
git config --global --list
```

## Modifier les paramètres de Git

### Modification du fichier .gitconfig dans le terminal VIM

```bash
vim ~/.gitconfig
```

Cela donne avec par exemple :

```.gitconfig
[color]
  diff = auto
  status = auto
  branch = auto
[user]
  name = pseudo
  email = votre-email@domaine.fr
[alias]
  ci = commit
  co = checkout
  st = status
  br = branch
```

## Ressources complémentaires

- [Personnalisation de Git - Configuration de Git (git-scm.com) [FR]](https://git-scm.com/book/fr/v2/Personnalisation-de-Git-Configuration-de-Git)
- [Kittygiraudel git-config](https://kittygiraudel.com/snippets/git-config/)
