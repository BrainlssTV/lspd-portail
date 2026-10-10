# Portail LSPD — GitHub Pages

Site statique sans installation ni abonnement. Navigation, recherche, filtres et fiches avec liens. Les contenus initiaux sont des repères de formation à valider par le commandement. Aucun compte ni donnée personnelle.

## Mettre en ligne depuis GitHub
1. Créer un dépôt **public**, par exemple `lspd-portail`.
2. Décompresser le ZIP. Dans le dépôt : **Add file → Upload files**. Importer les fichiers du dossier à la racine du dépôt : `index.html`, `style.css`, `app.js`, `contenu.js` et `.nojekyll` (ce dernier est facultatif ici). Ne pas importer le ZIP lui-même.
3. Cliquer **Commit changes**.
4. Dans **Settings → Pages**, choisir **Deploy from a branch**, puis **main** et **/ (root)**, et **Save**.
5. Attendre la publication. L’adresse sera `https://TON-PSEUDO.github.io/lspd-portail/`.

## Ajouter vos liens et vos fiches
Ouvrir `contenu.js` sur GitHub et cliquer le crayon pour modifier.
Chaque fiche a une catégorie (`rookie`, `academy`, `procedures`, `unites`), un identifiant unique, un titre, une description, des repères et des liens.
Remplacer par exemple :
```js
"links": []
```
par :
```js
"links": [
  { "label": "Guide de formation", "url": "https://VOTRE-LIEN" },
  { "label": "Support vidéo", "url": "https://VOTRE-LIEN" }
]
```
Utiliser les vraies adresses HTTPS de vos documents (Google Docs, PDF, Discord, vidéos...). Vérifier aussi les permissions de partage des documents. Modifier les textes dans `points` pour détailler les fiches. Pour une nouvelle fiche, copier un objet complet dans `cards`, choisir un identifiant unique et séparer les objets par une virgule.
Modifier `announcement` pour le bandeau d’information.
Cliquer **Commit changes** : GitHub Pages publie automatiquement la mise à jour.

## Logo
L’emblème étoilé est provisoire : ce n’est pas le logo officiel du LSPD. Pour le remplacer, ajouter `logo.png` à la racine et remplacer `<span class="crest">★</span>` dans `index.html` par `<img src="logo.png" alt="Logo LSPD" width="48" height="54">`.

## Consultation
La version GitHub Pages et son code sont publics. Ne pas y ajouter d’informations internes confidentielles. Les fiches ne sont pas modifiables par les visiteurs : l’édition s’effectue depuis le dépôt GitHub.
La navigation utilise des ancres (`#rookie`) pour rester compatible avec GitHub Pages. Ouvrir `index.html` permet également une consultation locale.
