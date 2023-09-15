# Cours Système n°1 - `BASH`

*[lien vers le killercoda](https://killercoda.com/emelin)*  

## 1.1
- Ouvrir un terminal <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.
- Chemin absolu du home de *john* : `/home/john/`.
- `home` est un dossier qui contient tous les dossiers personnels des utilisateurs.
-  ⬆️ ou ⬇️ pour accéder à l'historique des commandes.
-  ⬅️ ou ➡️ pour corriger dans la ligne.

## 1.2

### La commande `ls` - list :
- `ls` : permet d'afficher la liste des dossiers et fichiers du dossier actuel

### La commande `cd` - Change Directory :
- `cd <nom_dossier>` : permet de se déplacer dans un dossier enfant.
- `cd ` : permet de se déplacer dans son home, repéré par le ~ (<kbd>AltGr</kbd> + <kbd>2</kbd>).
- `cd ..` : permet de remonter dans le dossier parent.
- `cd ../../` : permet de remonter dans le dossier grand-parent.

## 1.3
- `cat <addresse_vers_fichier>` permet de lire le contenu d'un fichier.
- <kbd>Tab</kbd> : autocomplétion du début d'une commande.

## 1.4
- `ls <nom_dossier>` : permet d'afficher la liste des dossiers et fichiers du dossier nom_dossier.
- **chemin relatif** `ls <chemin>` ou `cat <chemin>`: est un chemin qui dépend de l'endroit où l'on est.
- `ls ..` ou aussi `ls ../<chemin>`: permet de lister le contenu du dossier parent.

- **chemin absolu** `ls /<chemin>`: est un chemin qui ne dépend pas de la où je me trouve.

## 1.5
- le premier mot d'une ligne est une **commande** (= un fichier exécutable).
- les autres mots sont des arguments.
- `-v` *par exemple* est une option car il y a un tiret (*convention*).
- En version longue, il s'écrive avec deux tirets.

  * Les commandes les plus indispensables sont dans le répertoire `/bin/`,
  * Les commandes accessibles à tous les utilisateurs sont dans le répertoire `/usr/bin/`,
  * Certaines commandes ne sont accessibles qu'aux administrateurs du système. Les commandes d'administration sont dans le répertoire `/sbin/`.
 
 ## 1.6
 - `tree ..` : permet d'afficher l'arborescence du dossier parent.
 - `tree .` : permet d'afficher l'arborescence du dossier courant.
 - `~` : représente le dossier mon home.
 - `cd ~` : emmène directement dans mon home.
  
##
# Cours n°2

- `nano <chemin>` : pour éditer un nouveau fichier et ouvre un éditeur de fichier
- `mkdir <répertoire>` : créer un dossier
- `mkdir -r <répertoires>` : créer plusieurs dossier grâce à l'option `-r` (`--recursive`)
- `mkdir <arguments>` : créer plusieurs sous-dossier rapidement
- `touch <chemin vers un fichier>` : permet de mettre à jour (l'heure) de dernière modification
- `touch <chemin vers un fichier inexistant>` : créer un fichier vide
- `rm <chemin vers un fichier>` : permet de supprimer un **fichier**
- `rm -r <chemin vers un dossier>` ou `rm --recursive <chemin vers un dossier>` : efface tout les dossiers et fichiers qui sont les enfants du dossier et le dossier
- ⚠️ `rm -r /` : efface tout l'ordinateur
- `du <chemin vers un dossier>` : permet de connaître la taille d'un répertoire (`du` : *disk usage*)
- `du -s <dossier>` : fait la somme de l'espace disque utilisé
- `du -hm <dossier>` : affiche la taille avec une unité plus facile à lire
- `ls -l` : permet de voir la dernière date de modification d'un fichier


### option :
- `-a` ou `-- all` : permet de voir tous les fichiers/dossiers (même les fichiers cachés qui sont identifiés par `.<nom_fichier>`)
- `-l` : permet de donner plus d'informations sur les fichiers/dossiers

