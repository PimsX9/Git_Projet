# TD 1 - Git/Github

## Exercice 1 - Installation

1. Installer le logiciel GIT
2. Vérifier la version de GIT installer sur vos poste de travail (git --version)
```

```
## Exercice 2 - Configuration & création d’un repository

1. Initialiser votre nom & email. (user.name & user.email).
2. Créer un répertoire “training-git”.
3. Initialiser votre repository à l’intérieur de ce dossier.
4. Vérifier que le repository soit correctement créé́
(présence d’un certain dossier cacher..)

## Exercice 3 - 1er Commit

1. Dans le répertoire “training-git” créer un fichier index.html.
2. Insérer dans ce fichier la déclaration du doctype HTML.
3. Ajoutez le fichier index.html dans le stage.
4. Créer un commit avec ce fichier, en respectant la norme de nommage du commit comme
vu en cours.
5. Vérifier que le commit ai bien été ajouté dans l’historique des commit de votre
repository.
6. Modifier le fichier index.html
7. Comité à nouveau ce fichier en utilisant VIM
   
## Exercice 5 - Merge

1. Créer un dossier training-merge.
2. Initialiser votre git.
3. Créer un fichier index.html est commit le.
4. Créer une branche “ feature-first-merge ” et déporte-toi dessus.
5. Créer un fichier main.js
6. Commiter ce fichier
7. Rends-toi sur la branche master et assure toi que ce fichier n’est pas présent.
8. Mergé la branche “feature-first-merge” sur master.
9. Vérifier que le code le commit fait sur feature-first-merge est bien présent sur master.
    
## Exercice 6 - Conflict

1. Créer un dossier training-conflict
2. Initialiser votre git
3. Créer un fichier index.html & commit le
4. Créer une branche “feature-first-conflict” et déporte-toi dessus.
5. Modifie le fichier index.html pour lui ajouter un titre <title> à la ligne 1
6. Commit cette modification
7. Rends-toi sur la branche master
8. Modifie le fichier index.html pour lui ajouter un <body> à la ligne 1
9. Commit cette modification
10. Merge la branche feature-first-conflict sur master.
Ici git vas t’indiquer qu’un conflit est apparu sur le fichier index.html, à toi de le résoudre en
sélectionnant les développements qui t'intéressent dans le fichier index.html, une fois que c’est fait,
supprime les lignes contenant ====== et >>>>>> ajoute le fichier index.html à ton stage puis
commit le.

## Exercice 7 - Déploiement du repository sur gitlab 
Le but de cet exercice est de déployer votre le repository "training-git" sur le cloud.

1. Se rendre sur https://gitlab.com/
2. Créer un compte gitlab.
3. Créer un projet training-git ( blank project, project public )
4. Rends-toi sur ton terminal
5. Exécute ligne par ligne le code situé sous “Push an existing Git repository” de l’interface de
gitlab

## Exercice 8 - Merge Request ( MR )
Le but de cet exercice est de comprendre le fonctionnement, l'utilité et la création d’une merge
request ( dis MR ). Pour ce faire, nous allons utiliser le repository “training-git” déployé à
l’instant sur gitlab.

1. Rendez-vous sur la branche master du projet training-git.
2. Créer une branche first-merge-request.
3. Pousse cette branche sur ton repository distant ( git push )
git t’informera que cette branche n’existe pas sur le repository distant ce qui est parfaitement
logique, et te proposera une commande à exécuter pour créer une nouvelle branche sur ton
repository distant au format ( git push --set-upstream origin <ma-branch> ), exécute le code
proposer par git.
4. Créer un fichier main.js
5. Ajouter le code console.log (“premiere MR”) à l’intérieur de celui-ci
6. Commit le et pousse le sur ton repository distant (git push)
7. Rends-toi sur gitlab (connectes-toi si besoin)
8. Rends-toi sur ton projet training-git.
9. Rends-toi sur la page branche est assure toi que ta nouvelle branche “first-mergerequest”
est bien présente.
10. Créer une nouvelle MR en sélectionnant le branche first-merge-request en “source
branch” et master en “target branche”
Le but ici est bien de créer une merge request qui après validation, permettra le merge des
modifications apporté par la branche “first-merge-request” vers la branche “master”
11. Une fois que tu t’es assuré que tes développements sont conformes aux attentes (onglet
change de la page merge request), tu peux cliquer sur merge.
En entreprise, tu t’assureras qu’un ou plusieurs de tes collègues ont approuvé tes changements en
cliquant sur l’emoji pouce par exemple avant de réaliser la merge.
12. Rends-toi sur la branche master, récupère les modifications et assures toi qu'elles soient
présentes
