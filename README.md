# New World English Center (NWEC)

Site vitrine statique de **New World English Center**, centre de formation spécialisé dans l’apprentissage et le perfectionnement de l’anglais.

Le projet utilise uniquement :

- **HTML** pour la structure et le contenu ;
- **CSS** pour le design, les galeries et la responsivité ;
- **JavaScript** pour les interactions et les traductions ;
- des images JPEG/JFIF fournies par NWEC.

Il n’y a pas de backend, de base de données, de framework ou de dépendance à installer.

## Fonctionnalités

- Page d’accueil en anglais par défaut ;
- traduction instantanée anglais/français ;
- mode clair/sombre avec mémorisation dans le navigateur ;
- menu hamburger sur téléphone et tablette ;
- bouton WhatsApp flottant ;
- bouton de retour automatique en haut ;
- formulaire de contact qui utilise actuellement `mailto:` ;
- galerie de séances de cours ;
- galerie de certificats et réussites des apprenants ;
- présentation de l’activité parrainée **L’Anglais Chez Soi** ;
- présentation du programme **ELCE Scholarship** ;
- dossier préparé pour les photos de la cérémonie de clôture ELCE 2025 ;
- footer complet avec les coordonnées de NWEC ;
- design responsive pour ordinateur, tablette et téléphone.

> Le formulaire utilise encore `mailto:` tant que l’endpoint Formspree n’a pas été fourni. Pour un envoi automatique sans ouvrir le client mail, il faudra remplacer l’action du formulaire par votre URL Formspree.

## Arborescence

```text
new-world-english-html-css-js/
├── index.html
├── style.css
├── script.js
├── logo.jfif
├── README.md
└── images/
    ├── hero-learning.jpeg
    ├── courses/
    │   ├── course-01.jpeg
    │   ├── course-02.jpeg
    │   ├── course-03.jpeg
    │   └── course-04.jpeg
    ├── book/
    │   ├── book-01.jpeg ... book-06.jpeg
    ├── certificates/
    │   ├── certificate-01.jpeg ... certificate-06.jpeg
    └── elce-2025/
        └── README.txt
```

## Emplacement des contenus

### Image Hero

`images/hero-learning.jpeg` est utilisée comme arrière-plan de la section principale `.hero`. Elle apparaît à droite sur ordinateur et s’adapte automatiquement sur mobile.

### Photos de séances de cours

Les photos du dossier `images/courses/` apparaissent dans la section `#experience`, intitulée **Our learning experience**. Cette section est placée après la présentation de NWEC et avant les certificats.

### Certificats de niveau de langue

Les images du dossier `images/certificates/` apparaissent dans la section `#certificates`, intitulée **Learner achievements**. Elles mettent en valeur les progrès, la remise des certificats et l’accompagnement des apprenants.

### L’Anglais Chez Soi

Les images du dossier `images/book/` apparaissent dans la section `#programmes`. Cette section présente le livre et l’activité parrainée par New World English Center.

### ELCE Scholarship

La section `#elce` présente le programme **English for Leadership & Corporate Excellence (ELCE)** :

- bourses complètes et partielles ;
- formation intensive de six mois ;
- anglais professionnel ;
- employabilité et leadership ;
- mobilité internationale ;
- préparation au TOEFL iBT, DET, TOEIC et autres tests.

Les photos de la cérémonie de clôture **ELCE édition 2025** sont maintenant intégrées dans la galerie de la section ELCE. Elles se trouvent dans :

```text
images/elce-2025/
```

Vous pouvez les nommer ainsi :

```text
elce-01.jpeg
elce-02.jpeg
elce-03.jpeg
```

La galerie est placée sous le texte de présentation du programme et avant le formulaire de contact. Les images sont affichées entièrement sans recadrage agressif.

## Structure de `index.html`

Le fichier HTML contient :

- l’en-tête et la navigation ;
- le Hero avec l’image NWEC ;
- la présentation de NWEC ;
- la galerie des séances de cours ;
- la galerie des certificats ;
- les offres de formation ;
- la section L’Anglais Chez Soi ;
- la section ELCE Scholarship ;
- les formations pour entreprises ;
- le formulaire ;
- les coordonnées et le footer.

Les textes traduisibles utilisent `data-i18n`, par exemple :

```html
<h2 data-i18n="elceTitle">English for Leadership &amp; Corporate Excellence.</h2>
```

## Structure de `style.css`

Le fichier CSS définit :

- les variables de couleurs NWEC ;
- les grilles de contenu ;
- l’arrière-plan du Hero ;
- les galeries d’images ;
- les cartes de programmes ;
- le dark mode ;
- le menu mobile ;
- le footer ;
- les boutons WhatsApp et retour en haut.

Les principaux breakpoints sont :

- `950px` pour tablette et menu hamburger ;
- `600px` pour téléphone et affichage sur une colonne.

## Structure de `script.js`

Le JavaScript gère :

- les traductions anglaises et françaises ;
- le rendu des cartes d’offres ;
- le dark mode avec `localStorage` ;
- le menu hamburger ;
- le retour en haut ;
- le formulaire de contact ;
- la préparation de l’email actuel avec `mailto:`.

## Formulaire et Formspree

Le formulaire est actuellement statique et utilise l’adresse :

```text
newworldenglishcenter4@gmail.com
```

Tant que l’URL Formspree n’est pas intégrée, le navigateur prépare un email avec `mailto:`. Cela peut ouvrir le client mail du visiteur et nécessite une action manuelle.

Après réception de l’endpoint Formspree, il faudra utiliser une structure similaire :

```html
<form action="https://formspree.io/f/VOTRE_ENDPOINT" method="POST">
```

Les champs devront avoir des attributs `name`, par exemple :

```html
<input name="first_name" required>
<input name="email" type="email" required>
<textarea name="objective" required></textarea>
```

## Lancer le site en local

Depuis le dossier du projet :

```bash
python3 -m http.server 3000
```

Ouvrez ensuite :

```text
http://localhost:3000
```

Avec VS Code, l’extension **Live Server** peut également être utilisée.

## Mettre le projet sur GitHub

Créez un nouveau dépôt GitHub, puis exécutez :

```bash
git init
git add .
git commit -m "Update NWEC website content and galleries"
git branch -M main
git remote add origin https://github.com/VOTRE_NOM/new-world-english-center.git
git push -u origin main
```

Pour GitHub Pages :

1. ouvrez **Settings** dans le dépôt ;
2. choisissez **Pages** ;
3. sélectionnez **Deploy from a branch** ;
4. choisissez `main` et `/ (root)` ;
5. cliquez sur **Save**.

L’adresse sera similaire à :

```text
https://VOTRE_NOM.github.io/new-world-english-center/
```

## Mise à jour future

Après chaque modification :

```bash
git add .
git commit -m "Update NWEC website"
git push
```

## Sites NWEC

La page d’accueil présente les trois sites de formation :

- **Abomey-Calavi** — Bakhita ;
- **Bohicon** — ZAKPO-ADAGAME ;
- **Parakou** — Banikanni.

La section est accessible depuis le menu avec le lien **Our locations / Nos sites**.

## Coordonnées NWEC

- Téléphone / WhatsApp : `01 61 89 11 97` ;
- lien WhatsApp international : `https://wa.me/2290161891197` ;
- email : `newworldenglishcenter4@gmail.com` ;
- secteur : enseignement ;
- taille : 2–10 employés ;
- fondé en : 2023.

## Licence

Projet créé pour **New World English Center (NWEC)**. Le logo, les photos et les contenus de marque appartiennent à NWEC.
