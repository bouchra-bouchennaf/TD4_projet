# Collaboration

Pour réussir cette collaboration en binôme sur Git, suivez attentivement les étapes décrites ci-dessous. Le projet consiste à construire un site web parlant de Git. Chaque collègue a des tâches spécifiques, identifiées par des couleurs. Le travail de A est en rouge et celui de B est en bleu.

### `A` & `B` : Configurer Git

1. **Configurer Git avec votre nom et email :**
   ```sh
   git config --global user.name "Votre nom"
   git config --global user.email "vous@votre_ordinateur"
   ```

### `A` : Préparer un répertoire partagé

1. **Créer un nouveau répertoire GitHub :**
   - Allez sur [GitHub](https://github.com/new) et nommez le répertoire.
   - Ajoutez une description, cochez "Initialize this repository with a README" et créez le répertoire.
2. **Ajouter un collaborateur :**
   - Dans les réglages du projet, allez à l'onglet Collaborators `http://github.com/<a_utilisateur_nom>/<repertoir_nom>/settings/collaboration`.
   - Ajoutez l'identifiant GitHub de `B` et cliquez sur "Add collaborator".

### `B` : Obtenir une copie locale du répertoire

1. **Cloner le répertoire :**
   - Cloner le répertoire sur votre ordinateur avec `git clone https://github.com/<a_utilisateur_nom>/<repertoir_nom>`.
2. **Créer un fichier `index.html` :**
   - Créez un fichier `index.html` avec le squelette classique.
   - Commitez avec :
     ```sh
     git add index.html
     git status
     git commit -m "Ajout du fichier index.html"
     git log
     git push
     ```
   - Vérifiez sur GitHub que les modifications ont été reçues.

### `A` : Recevoir les mises à jour

1. **Tirer les modifications de votre collègue :**
   - Utilisez `git pull --ff-only` pour récupérer les modifications.
2. **Modifier `index.html` :**
   - Ajoutez ce contenu (avec une faute d’orthographe dans le nom de votre collègue) :
     ```html
     <!DOCTYPE html>
     <html>
     <head>
         <title>Le fantastique guide de Git</title>
     </head>
     <body>
         <h1>Le fantastique guide de Git</h1>
         <p>par nom de A, nom de B</p>
         <p>Contenu ajouté.</p>
     </body>
     </html>
     ```
   - Commitez et poussez :
     ```sh
     git add index.html
     git commit -m "Ajout de contenu et correction de nom"
     git push
     ```
### `B` : Créer `commandes.html` :
   - Créez `commandes.html` avec une liste des commandes Git connues jusqu’ici.
      ```html
      <!DOCTYPE html>
      <html>
      <head>
         <meta charset="UTF-8">
         <title>Commandes Git</title>
      </head>
      <body>
         <h1>Liste des commandes Git</h1>

         <dl>
            <dt>git init</dt>
            <dd>Initialise un nouveau dépôt Git.</dd>

            <dt>git clone &lt;url&gt;</dt>
            <dd>Clone un dépôt distant dans un nouveau répertoire.</dd>

            <dt>git add &lt;fichier&gt;</dt>
            <dd>Ajoute des modifications spécifiques à la zone de staging.</dd>

            <dt>git commit -m "Message de commit"</dt>
            <dd>Commite les changements dans le dépôt avec un message.</dd>

            <dt>git push</dt>
            <dd>Pousse les commits locaux vers le dépôt distant.</dd>

            <dt>git pull</dt>
            <dd>Récupère et fusionne les modifications du dépôt distant.</dd>

            <dt>git merge &lt;branche&gt;</dt>
            <dd>Fusionne une branche spécifiée dans la branche courante.</dd>
         </dl>

      </body>
      </html>
      ```
   - Ne commitez pas encore.
1. **Vérifier les modifications locales :**
   - Utilisez `git status` pour vérifier les modifications en cours.
2. **Fetcher et vérifier les statuts :**
   - Utilisez `git fetch`, puis `git status`. Si `A` a poussé des modifications, le message sera :
     ```sh
     On branch master
     Your branch is behind 'origin/master' by 1 commit.
     ```
3. **Tirer les modifications :**
   - Utilisez `git pull --ff-only` pour récupérer les modifications d'A.
4. **Commiter les modifications de B :**
   - Commitez `commandes.html` et poussez :
     ```sh
     git add commandes.html
     git commit -m "Ajout des commandes Git"
     git push
     ```

### Éviter les conflits de `A` avec stash

1. **Ajouter une feuille de style :**
   - Ajoutez une feuille de style à `index.html` mais ne commitez pas encore.
2. **Fetcher et tirer les modifications :**
   - Utilisez `git fetch` puis `git status`.
   - Si `B` a poussé des modifications, tirez-les avec `git pull --ff-only`.
3. **Committer les modifications avec stash :**
   - Commitez vos modifications :
     ```sh
     git add index.html style.css
     git commit -m "Ajout de la feuille de style"
     git push
     ```

### `B` : Corriger les erreurs de nom

1. **Corriger l'erreur de nom :**
   - Corrigez l'orthographe de votre nom dans `index.html`, puis tirez les modifications :
     ```sh
     git pull --ff-only
     ```
   - Si refusé, utilisez stash :
     ```sh
     git stash show
     git stash
     git pull --ff-only
     git stash apply
     git add .
     git commit -m "Correction de l'orthographe"
     git push
     ```

### Utiliser git gui et gitk

1. **Utiliser git gui :**
   - Utilisez `git gui` pour corriger et pousser des modifications via l'interface graphique.

### Faire la guerre

1. **Corriger les noms intentionnellement :**
   - Utilisez `git gui` pour introduire des fautes d'orthographe intentionnelles et pousser rapidement avant votre collègue.

### Travail facultatif

1. **Gérer des conflits :**
   - Apprenez à résoudre des conflits manuellement.
2. **Travailler avec les pull requests :**
   - Utilisez les pull requests sur GitHub pour la gestion collaborative.

En suivant ces étapes, vous maîtriserez les bases de la collaboration avec Git et serez en mesure de gérer efficacement les contributions de chacun.
