# LSPD — Éditeur de site

## Installation : une seule fois
1. Décompressez LSPD_Editeur_Site.zip dans le dossier de votre dépôt lspd-portail.
2. Remplacez index.html et admin.html. Les anciens fichiers app.js, contenu.js, style.css, admin.js et admin.css ne sont plus utilisés ; vous pouvez les supprimer. Les conserver n’empêche pas le nouveau site de fonctionner.
3. Dans GitHub Desktop : Commit to main puis Push origin.
4. Gardez GitHub Pages configuré sur main, / (root). Si la publication n’est pas configurée : Settings → Pages → Deploy from a branch → main → / (root) → Save.
5. Ouvrez https://brainlsstv.github.io/lspd-portail/ après publication.

## Construire le site
Cliquez sur Administration. Le bouton « Essayer l’éditeur sans connexion » vous permet de découvrir les fonctionnalités et de préparer un brouillon.
- Identité : nom, sous-titre, devise.
- Pages & menu : ajouter, renommer, supprimer et réordonner les pages. La première page du menu est la page d’accueil.
- Blocs : titre, texte, image, lien, encadré et séparateur.
- Images : importer une image depuis le PC (PNG, JPEG, WebP, GIF, maximum 4 Mo) ou coller l’adresse HTTP/HTTPS d’une image en ligne.
- Les flèches déplacent les blocs. L’aperçu montre le rendu de la page sélectionnée.
- Le texte est saisi en texte simple ; les retours à la ligne sont conservés. Cet éditeur ne propose pas de mise en page libre ou de glisser-déposer.

## Publier pour les agents
1. Créez une clé GitHub à granularité fine : https://github.com/settings/personal-access-tokens/new
2. Propriétaire : BrainlssTV. Repository access : Only select repositories → lspd-portail.
3. Repository permissions : Contents → Read and write. Choisissez une expiration puis générez la clé.
4. Collez la clé uniquement dans l’écran de connexion de l’éditeur.
5. Construisez vos pages puis cliquez sur Publier le site. Les images sont envoyées, puis les pages sont enregistrées dans site.json avec un commit GitHub.
6. Attendez le déploiement GitHub Pages. Les agents consultent ensuite le site, sans compte ni clé.

La page Administration est accessible publiquement, mais personne ne peut enregistrer une modification dans votre dépôt sans un accès GitHub autorisé. La clé reste en mémoire dans l’onglet ; elle n’est pas stockée ni incluse dans les fichiers ou les exports. Une véritable connexion OAuth sans clé nécessiterait un service de connexion supplémentaire.

## Brouillons
Exporter le brouillon crée LSPD-brouillon.json, contenant vos textes et vos images importées. Ce fichier peut être restauré avec « Restaurer un brouillon exporté », en bas de l’éditeur, après connexion ou en mode essai. Les images fournies par une URL externe restent des liens.
Les brouillons ne sont pas automatiquement conservés au rechargement. Une alerte vous avertit si vous quittez avec des changements non publiés.

Si quelqu’un modifie site.json pendant votre session, la publication est bloquée. Exportez, reconnectez-vous, comparez les contenus puis reprenez. Réimporter votre brouillon remplace le contenu chargé : ne le faites pas sans comparer les modifications.
En cas de coupure réseau pendant la publication, vérifiez le dépôt avant de réessayer : une requête peut avoir réussi malgré l’absence de réponse. Les images déjà envoyées restent dans assets ; supprimer un bloc ne supprime pas automatiquement le fichier image du dépôt.

## À savoir
Le dépôt et le site sont publics. Le site se consulte avec plusieurs pages dans le menu ; leurs adresses utilisent #identifiant. Le logo étoilé est provisoire. Les anciens contenus de fiches ne sont pas repris : cette version repart avec Accueil et Espace Rookie, à remplir librement.
Le contenu public est chargé depuis site.json. site-default.js sert uniquement de secours si site.json ne peut pas être chargé, notamment lors d’une ouverture locale directe. Pour voir le contenu réellement publié, utilisez l’adresse GitHub Pages.
Le maximum de contenu textuel est de 900 Ko. Les protections de branche peuvent empêcher l’écriture directe. La vérification du code a été effectuée ; le rendu dans un navigateur et une publication réelle avec votre clé restent à vérifier.
