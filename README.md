# TD 1 - Git/Github

## Exercice 1 - Installation

1. Installer le logiciel GIT
2. Vérifier la version de GIT installer sur vos poste de travail (git --version)
```
MLNF6641@WX-OR6256636 MINGW64 /c/Git_projets/TD_1
$ git --version
git version 2.47.0.windows.2

```
## Exercice 2 - Configuration & création d’un repository

1. Initialiser votre nom & email. (user.name & user.email).
```

MLNF6641@WX-OR6256636 MINGW64 /c/Git_projets/training-git
$ git config --global user.name "Rémy"
$ git config --global user.email "remy.burdet@orange.com"

```
2. Créer un répertoire “training-git”.
```
MLNF6641@WX-OR6256636 MINGW64 /c/Git_projets/training-git

```
3. Initialiser votre repository à l’intérieur de ce dossier.
```
$ git init
Initialized empty Git repository in C:/Git_projets/training-git/.git/

```
4. Vérifier que le repository soit correctement créé́
(présence d’un certain dossier cacher..)
```
$ ls -lisa
total 4
12384898975427814 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 14:00 ./
37154696925860776 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 13:53 ../
35465847065697815 4 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 14:00 .git/

```
## Exercice 3 - 1er Commit

1. Dans le répertoire “training-git” créer un fichier index.html.
```

$ touch index.html

```
2. Insérer dans ce fichier la déclaration du doctype HTML.
```
$ vim index.html

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="utf-8">
    <title><!-- Insérer le titre ici--></title>
</head>
<body>
    <!-- Insérer le contenu ici -->
</body>
</html>

```
3. Ajoutez le fichier index.html dans le stage.
```
$ git add index.html
warning: in the working copy of 'index.html', LF will be replaced by CRLF the ne
xt time Git touches it

```
4. Créer un commit avec ce fichier, en respectant la norme de nommage du commit comme
vu en cours.
```
$ git commit -m "[Feat] Ajout du nouveau fichier index.html"
[master (root-commit) a06f98a] [Feat] Ajout du nouveau fichier index.html
 1 file changed, 18 insertions(+)
 create mode 100644 index.html

```
6. Vérifier que le commit ai bien été ajouté dans l’historique des commit de votre
repository.
```
$ git log
commit a06f98a24189d0ff9aa4578c9676fc0d868945c8 (HEAD -> master)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 14:14:34 2024 +0100

    [Feat] Ajout du nouveau fichier index.html

```
8. Modifier le fichier index.html
```
$ vim index.html

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="utf-8">
    <title>training GIT</title>
</head>
<body>
    <!-- Insérer le contenu ici -->
</body>
</html>

```
9. Comité à nouveau ce fichier en utilisant VIM
```
$ git add index.html
$ git commit

Ajout du commentaire via VIM -> [Feat] modification fichier index.html
Fermeture du fichier.

[master 829474b] [Feat] modification fichier index.html
 1 file changed, 1 insertion(+), 9 deletions(-)

$ git log
commit 829474b264dc88a136fab22f49160678551e4e43 (HEAD -> master)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:02:10 2024 +0100

    [Feat] modification fichier index.html

commit a06f98a24189d0ff9aa4578c9676fc0d868945c8
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 14:14:34 2024 +0100

    [Feat] Ajout du nouveau fichier index.html

```
## Exercice 5 - Merge

1. Créer un dossier training-merge.
```
$ mkdir training-merge
$ cd training-merge/

```
2. Initialiser votre git.
```
$ git init
Initialized empty Git repository in C:/Git_projets/training-merge/.git/

$ ls -lisa
total 4
39406496739678134 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:13 ./
37154696925860776 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:12 ../
28147497671279070 4 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:13 .git/

```
3. Créer un fichier index.html est commit le.
```
$ touch index.html
$ git add index.html
$ git commit -m "[Feat] Ajout fichier index.html"
[master (root-commit) b6c3b91] [Feat] Ajout fichier index.html
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.html

$ git log
commit b6c3b91ad78c30c432efc6c4b715ffb05e65c970 (HEAD -> master)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:15:59 2024 +0100

    [Feat] Ajout fichier index.html

```
4. Créer une branche “ feature-first-merge ” et déporte-toi dessus.
```
$ git branch feature-first-merge
$ git branch
  feature-first-merge
* master

$ git switch feature-first-merge
Switched to branch 'feature-first-merge'
$ git branch
* feature-first-merge
  master

```
5. Créer un fichier main.js
```
$ touch main.js

```
6. Commiter ce fichier
```
$ git add main.js
$ git commit -m "[Feat] Ajout fichier main.js"
[feature-first-merge 5cd7380] [Feat] Ajout fichier main.js
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 main.js

$ git log
commit 5cd73809dfb89a72170c1596e60f97eecca8c6d0 (HEAD -> feature-first-merge)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:21:06 2024 +0100

    [Feat] Ajout fichier main.js

commit b6c3b91ad78c30c432efc6c4b715ffb05e65c970 (master)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:15:59 2024 +0100

    [Feat] Ajout fichier index.html

```
7. Rends-toi sur la branche master et assure toi que ce fichier n’est pas présent.
```
$ git switch master
Switched to branch 'master'

$ ls -lisa
total 4
39406496739678134 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:21 ./
37154696925860776 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:12 ../
28147497671279070 4 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:21 .git/
65302194597074566 0 -rw-r--r-- 1 MLNF6641 1049089 0 Nov 26 15:14 index.html

```
8. Mergé la branche “feature-first-merge” sur master.
```
$ git merge feature-first-merge
Updating b6c3b91..5cd7380
Fast-forward
 main.js | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 main.js

$ git log
commit 5cd73809dfb89a72170c1596e60f97eecca8c6d0 (HEAD -> master, feature-first-merge)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:21:06 2024 +0100

    [Feat] Ajout fichier main.js

commit b6c3b91ad78c30c432efc6c4b715ffb05e65c970
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:15:59 2024 +0100

    [Feat] Ajout fichier index.html

```
9. Vérifier que le code le commit fait sur feature-first-merge est bien présent sur master.
```
$ git branch
  feature-first-merge
* master

$ ls -lisa
total 4
39406496739678134 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:39 ./
37154696925860776 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:12 ../
28147497671279070 4 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:39 .git/
65302194597074566 0 -rw-r--r-- 1 MLNF6641 1049089 0 Nov 26 15:14 index.html
23080948090498307 0 -rw-r--r-- 1 MLNF6641 1049089 0 Nov 26 15:39 main.js

```   
## Exercice 6 - Conflict

1. Créer un dossier training-conflict
```
$ mkdir training-conflict
$ cd training-conflict/

```
2. Initialiser votre git
```
$ git init
Initialized empty Git repository in C:/Git_projets/training-conflict/.git/
$ ls -lisa
total 8
75998243712053406 0 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:45 ./
37154696925860776 4 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:44 ../
54043195528523788 4 drwxr-xr-x 1 MLNF6641 1049089 0 Nov 26 15:45 .git/

```
3. Créer un fichier index.html & commit le
```
$ touch index.html
$ git add index.html
$ git commit -m "[Feat] Ajout fichier index.html"
[master (root-commit) b7530f9] [Feat] Ajout fichier index.html
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 index.html

```
4. Créer une branche “feature-first-conflict” et déporte-toi dessus.
```
$ git branch feature-first-conflict
$ git switch feature-first-conflict
Switched to branch 'feature-first-conflict'
$ git branch
* feature-first-conflict
  master

```
5. Modifie le fichier index.html pour lui ajouter un titre <title> à la ligne 1
```
$ vim index.html
Ajout de la balise <title> sur la première ligne
$ cat index.html
<title>

```
6. Commit cette modification
```
$ git add index.html
$ git commit -m "[Feat]Ajout balise <title>"
[feature-first-conflict 8aa7c56] [Feat]Ajout balise <title>
 1 file changed, 1 insertion(+)

```
7. Rends-toi sur la branche master
```
$ git switch master
Switched to branch 'master'
$ git branch
  feature-first-conflict
* master

```
8. Modifie le fichier index.html pour lui ajouter un <body> à la ligne 1
```
$ vim index.html
Ajout de la balise <body> sur la première ligne
$ cat index.html
<body>

```
9. Commit cette modification
```
$ git add index.html
$ git commit -m "[Feat] Ajout balise <body>"
[master b368b80] [Feat] Ajout balise <body>
 1 file changed, 1 insertion(+)

```
10. Merge la branche feature-first-conflict sur master.
Ici git vas t’indiquer qu’un conflit est apparu sur le fichier index.html, à toi de le résoudre en
sélectionnant les développements qui t'intéressent dans le fichier index.html, une fois que c’est fait,
supprime les lignes contenant ====== et >>>>>> ajoute le fichier index.html à ton stage puis
commit le.
```
$ git merge feature-first-conflict
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.

$ cat index.html
<<<<<<< HEAD
<body>
=======
<title>
>>>>>>> feature-first-conflict

Après modification :
$ cat index.html
<body>
<title>

$ git add index.html
$ git commit -m "[Feat]Gestion conflict"
[master b30b934] [Feat]Gestion conflict

$ git log
commit b30b934cd9d45596a3f2e2f04d0557b98d3ee25f (HEAD -> master)
Merge: b368b80 8aa7c56
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 16:10:39 2024 +0100

    [Feat]Gestion conflict

commit b368b808e54d158cc5431017dddadd77372a2ed1
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 16:05:20 2024 +0100

    [Feat] Ajout balise <body>

commit 8aa7c56301d276e1f8170f42a8fa34b9f6324741 (feature-first-conflict)
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:54:02 2024 +0100

    [Feat]Ajout balise <title>

commit b7530f935279b9a06a533f5aa12e7bc8246d55ba
Author: Rémy <remy.burdet@orange.com>
Date:   Tue Nov 26 15:47:18 2024 +0100

    [Feat] Ajout fichier index.html

```
## Exercice 7 - Déploiement du repository sur gitlab 
Le but de cet exercice est de déployer votre le repository "training-git" sur le cloud.

1. Se rendre sur https://gitlab.com/
2. Créer un compte gitlab.
```
https://github.com/PimsX9

```
3. Créer un projet training-git ( blank project, project public )
```

```
4. Rends-toi sur ton terminal
```

```
5. Exécute ligne par ligne le code situé sous “Push an existing Git repository” de l’interface de
gitlab
```

```
## Exercice 8 - Merge Request ( MR )
Le but de cet exercice est de comprendre le fonctionnement, l'utilité et la création d’une merge
request ( dis MR ). Pour ce faire, nous allons utiliser le repository “training-git” déployé à
l’instant sur gitlab.

1. Rendez-vous sur la branche master du projet training-git.
```

```
2. Créer une branche first-merge-request.
```

```
3. Pousse cette branche sur ton repository distant ( git push )
git t’informera que cette branche n’existe pas sur le repository distant ce qui est parfaitement
logique, et te proposera une commande à exécuter pour créer une nouvelle branche sur ton
repository distant au format ( git push --set-upstream origin <ma-branch> ), exécute le code
proposer par git.
```

```
5. Créer un fichier main.js
```

```
6. Ajouter le code console.log (“premiere MR”) à l’intérieur de celui-ci
```

```
7. Commit le et pousse le sur ton repository distant (git push)
```

```
8. Rends-toi sur gitlab (connectes-toi si besoin)
```

```
9. Rends-toi sur ton projet training-git.
```

```
10. Rends-toi sur la page branche est assure toi que ta nouvelle branche “first-mergerequest”
est bien présente.
```

```
12. Créer une nouvelle MR en sélectionnant le branche first-merge-request en “source
branch” et master en “target branche”
Le but ici est bien de créer une merge request qui après validation, permettra le merge des
modifications apporté par la branche “first-merge-request” vers la branche “master”
```

```
14. Une fois que tu t’es assuré que tes développements sont conformes aux attentes (onglet
change de la page merge request), tu peux cliquer sur merge.
En entreprise, tu t’assureras qu’un ou plusieurs de tes collègues ont approuvé tes changements en
cliquant sur l’emoji pouce par exemple avant de réaliser la merge.
```

```
16. Rends-toi sur la branche master, récupère les modifications et assures toi qu'elles soient
présentes
```

```
