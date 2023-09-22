# Cours Système - `BASH`

*[lien vers le killercoda](https://killercoda.com/emelin)*  
  
##
## Cours n°1 - 08/09/2023

### 1.1
- Ouvrir un terminal <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.
- Chemin absolu du home de *john* : `/home/john/`.
- `home` est un dossier qui contient tous les dossiers personnels des utilisateurs.
-  ⬆️ ou ⬇️ pour accéder à l'historique des commandes.
-  ⬅️ ou ➡️ pour corriger dans la ligne.

### 1.2

#### La commande `ls` - list :
- `ls` : permet d'afficher la liste des dossiers et fichiers du dossier actuel

#### La commande `cd` - Change Directory :
- `cd <nom_dossier>` : permet de se déplacer dans un dossier enfant.
- `cd ` : permet de se déplacer dans son home, repéré par le ~ (<kbd>AltGr</kbd> + <kbd>2</kbd>).
- `cd ..` : permet de remonter dans le dossier parent.
- `cd ../../` : permet de remonter dans le dossier grand-parent.

### 1.3
- `cat <addresse_vers_fichier>` permet de lire le contenu d'un fichier.
- <kbd>Tab</kbd> : autocomplétion du début d'une commande.

### 1.4
- `ls <nom_dossier>` : permet d'afficher la liste des dossiers et fichiers du dossier nom_dossier.
- **chemin relatif** `ls <chemin>` ou `cat <chemin>`: est un chemin qui dépend de l'endroit où l'on est.
- `ls ..` ou aussi `ls ../<chemin>`: permet de lister le contenu du dossier parent.

- **chemin absolu** `ls /<chemin>`: est un chemin qui ne dépend pas de la où je me trouve.

### 1.5
- le premier mot d'une ligne est une **commande** (= un fichier exécutable).
- les autres mots sont des arguments.
- `-v` *par exemple* est une option car il y a un tiret (*convention*).
- En version longue, il s'écrive avec deux tirets.

  * Les commandes les plus indispensables sont dans le répertoire `/bin/`,
  * Les commandes accessibles à tous les utilisateurs sont dans le répertoire `/usr/bin/`,
  * Certaines commandes ne sont accessibles qu'aux administrateurs du système. Les commandes d'administration sont dans le répertoire `/sbin/`.
 
 ### 1.6
 - `tree ..` : permet d'afficher l'arborescence du dossier parent.
 - `tree .` : permet d'afficher l'arborescence du dossier courant.
 - `~` : représente le dossier mon home.
 - `cd ~` : emmène directement dans mon home.
  
##
## Cours n°2 - 15/09/2023

- `ls -l` : permet de voir la dernière date de modification d'un fichier
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
- `du -h <dossier>` : affiche la taille avec une unité plus facile à lire

#### option :
- `-a` ou `-- all` : permet de voir tous les fichiers/dossiers (même les fichiers cachés qui sont identifiés par `.<nom_fichier>`)
- `-l` : permet de donner plus d'informations sur les fichiers/dossiers

### 2.7
- `ps -o pid` : permet d'afficher les identifiants des processus
  * PID : l'identifiant du processus (Process ID)
  * ARGS : la commande qui a été utilisée pour lancer le processus
  * PPID : l'identifiant du processus parent (Parent Process ID)
  * UID : l'identifiant de l'utilisateur qui a lancé le processus
  * TTY : le terminal correspondant au processus
- `ps -aux` : permet de lister tout les processus de la machine
- <kbd>ctrl</kbd>+<kbd>z</kbd> et <kbd>ctrl</kbd>+<kbd>c</kbd> permettent respectivement d'envoyer **SIGSTOP** et **SIGINT** à un processus.
- `fg` et `bg` permettent respectivement de mettre en avant-plan et en arrière plan un processus préalablement gelé (avec SIGSTOP ou ctrl+z)
  
##
## Cours n°3 - 15/09/2023

### 3.1 - Droits des fichiers
`ls -l` :
- `-rw-r----- 1 sasha  etu  495 juil. 16 08:52: fichier1.txt`
  * `fichier1.txt` : nom du fichier
  * `juil. 16 08:52` : date et heure de la dernière modification du fichier
  * `495` : taille en **octets** du fichier
  * `sasha etu` : le fichier appartient à l'utilisateur *sasha* et est dans le groupe *etu*
  * `1` : nombre de lien qui pointe vers ce fichier
- `-rw-r-----` : 
  * le premier `-` indique qu'il s'agit d'un **fichier**
    * `-` quand c'est un fichier ou `d` quand c'est un dossier ou `l` quand c'est un lien
  * `r` (read - **droit de lecture**) : on peut lire le fichier
  * `w` (write - **droit d'écriture**) : on peut modifier le contenu du fichier
  * `x` (execute - **droit d'execution**) : on peut executer le fichier
  * les autres `-` : absence de droit de **lecture**/**écriture**/**execution** (en fonction de la position du caractère `-`)
  * `r--` : indique les droits des **membres du groupe** (*ici que le droit de lecture*)
  * les trois derniers `---` indique les droits de tous les **autres utilisateurs**.

  - `cp` : copier un fichier
  - `grep` : rechercher un mot dans un fichier
 
 ### 3.2 - Modification des droits des fichiers
  - `chmod` : permet de modifier les droits d'un fichier/dossier qui m'appartient (propriétaire et accès)

  `chmod <ugoa><+|-><rwx> nom_fichier` :
    - `u` : pour les droits de l'utilisateur
    - `g` : pour les droits du groupe
    - `o` : pour les droits des autres utilisateurs
    - `a` : pour les droits de tout le monde
    - `+` : pour ajouter un droit
    - `-` : pour retirer un droit
    - `rwx` : comme avant pour lire, écrire, exécuter
  on peut mettre par exemple (`og-r`) ou encore (`ug+r, o-x`)