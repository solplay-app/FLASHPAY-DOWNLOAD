# Site de téléchargement FlashPay

Ce site ne contient PAS l'application. Il lit automatiquement la dernière version publiée
dans les « Releases » GitHub de votre dépôt d'application et envoie le visiteur directement sur le fichier .apk
(le téléchargement démarre, sans changer de page).

## 1. Régler 2 lignes (dans index.html, bloc CONFIG, en haut du script)
- `owner` : votre nom de compte GitHub (celui qui apparaît dans l'adresse du dépôt de l'app)
- `repo`  : le nom du dépôt de l'application
- Recommandé : `asset` = nom exact du fichier .apk dans la release (ex. `FlashPay.apk`)
- Si votre workflow republie toujours la même release (même tag), mettez ce tag dans `tag`.

⚠ Le dépôt de l'application (ou au moins sa Release) doit être **public**. Sinon le téléchargement est refusé aux visiteurs.

## 2. Mettre ces fichiers dans un dépôt GitHub
Créez un dépôt (ex. `flashpay-telechargement`) et envoyez-y tout le contenu de ce dossier
(index.html, icon-192.png, icon-512.png, _headers) à la racine.

## 3. Brancher Netlify sur ce dépôt
Netlify → Add new site → Import from Git → choisissez ce dépôt.
Build command : vide. Publish directory : `/` (racine). Chaque modification poussée sur GitHub met le site à jour.

## 4. Mises à jour de l'application
Rien à faire sur ce site : quand votre workflow publie une nouvelle release, la page affiche la nouvelle version,
la date, la taille et les nouveautés (texte de la release), et le bouton télécharge la nouvelle version.
Le QR code pointe vers la page : il ne change jamais.
