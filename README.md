# jeanlavallee.github.io

Site personnel de Jean Lavallée, servi par GitHub Pages à l'adresse https://jeanlavallee.github.io. Créé le 2026-11-19 sur le conseil de Ben Marx. Le site tient en cinq pages HTML écrites à la main (Home, About, Research, Teaching, Data ; découpage décidé par Jean le 2026-11-20), sans Jekyll, sans framework, sans traceur et sans requête vers un service tiers. Il n'a qu'un mode clair (décision de Jean du 2026-11-20). L'en-tête de la page porte une description, des balises Open Graph, une URL canonique, une icône en SVG intégré et une fiche schema.org (Person) pour les moteurs de recherche ; aucune ne charge de ressource externe.

## Structure

| Chemin | Contenu | Provenance |
|---|---|---|
| `index.html` | Page d'accueil : nom, champs, liens (CV, email, GitHub), présentation ; barre de menu Home · About · Research · Teaching · Data, commune aux cinq pages | Écrite le 2026-11-19, découpée le 2026-11-20 |
| `research.html` | Research in progress, Policy publications (avec la presse) | Résumés repris de `phd-applications/abstracts/` et de la note sur l'idéologie |
| `about.html` | Page About : Research experience et Education |
| `teaching.html` | Teaching : le TD d'économie monétaire internationale à Paris 1 (automne 2022) | Écrite le 2026-11-20, d'après `phd-applications/cv/sections/teaching.tex` |
| `data.html` | Data resources (liens à activer le 2026-12-15) | Écrite le 2026-11-20 | Intitulés et dates de `phd-applications/cv/sections/` |
| `style.css` | Feuille de style commune aux cinq pages (mode clair seulement) | Écrite le 2026-11-20 |
| `files/cv.pdf` | CV public, sans adresse postale ni téléphone | Compilé depuis `phd-applications/cv/cv_web.tex` |
| `files/measuring_ideology_parties_worldwide_2025.pdf` | Note « Measuring the Ideology of Political Parties Worldwide » (Lavallée, Marx, Pons et Rollet, novembre 2025, 11 pages) | Téléchargée le 2026-11-20 depuis https://vrollet.github.io/files/Ideology.pdf (version datée du 6 novembre 2025), à la demande de Jean ; voir `files/README.md` |
| `fonts/` | Martian Mono Narrow Light et Source Sans 3, avec leurs licences | Voir `fonts/README.md` |
| `.nojekyll` | Fichier vide qui désactive Jekyll | Documentation GitHub Pages |

## Mettre le CV à jour

1. Modifier le contenu dans `~/Documents/GitHub/phd-applications/cv/sections/` (jamais le style).
2. Depuis la racine de phd-applications : `tectonic -X compile -Z search-path=. -Z search-path=cv cv/cv_web.tex`
3. Copier le PDF : `cp ~/Documents/GitHub/phd-applications/cv/cv_web.pdf ~/Documents/GitHub/jeanlavallee.github.io/files/cv.pdf`
4. Changer la date « Page updated » au bas des cinq pages si besoin, puis committer et pousser.

## Activer les liens de la section Data resources (le 2026-12-15)

La section `Data resources` est visible depuis le 2026-11-20, sur le modèle des pages Data de Vincent Pons et de Vincent Rollet (nom, coauteurs, deux phrases, lien vers le site propre de la base). Le 15 décembre, dans chaque entrée, remplacer la ligne « Website online in December 2026 » par la ligne en commentaire placée dessous, en mettant l'adresse du site à la place de `URL_ANNUAIRES` ou `URL_NPD`. Vérifier aussi la ligne des coauteurs de la National Policies Database.

## Mise en ligne (à faire par Jean)

1. Sur GitHub, créer le dépôt **public** `jeanlavallee.github.io` sur le compte `jeanlavallee` (un compte gratuit exige un dépôt public pour Pages).
2. Dans ce dossier : `git add -A`, `git commit -m "publishing the personal website"`, puis `git push -u origin main` (le remote `origin` doit pointer vers le dépôt créé).
3. Sur GitHub : Settings > Pages > Build and deployment > Source « Deploy from a branch », branche `main`, dossier `/ (root)`, Save.
4. Attendre quelques minutes (jusqu'à dix selon la documentation), puis ouvrir https://jeanlavallee.github.io et vérifier la page, le CV et les liens.
5. Ne pas configurer de nom de domaine personnalisé (voir la section suivante).

Source : https://docs.github.com/en/pages (consultée le 2026-11-19 ; note détaillée dans `phd-applications/prompts/website/github_pages.md`).

## Dépublication prévue le 2027-04-16

Jean a décidé le 2026-11-19 que le site reste en ligne jusqu'au 15 avril 2027 (date commune d'acceptation des offres), puis qu'il est dépublié jusqu'à sa troisième année de doctorat. L'événement « Dépublier le site personnel » est inscrit au 16 avril 2027 dans `phd-applications/programs/deadlines.ics`.

Procédure documentée par GitHub, sans supprimer le dépôt :

1. Sur le dépôt, ouvrir Settings > Pages.
2. À côté de « Your site is live at … », ouvrir le menu à trois points et choisir **Unpublish site**. Le déploiement est retiré ; le dépôt et ses réglages restent.
3. Autre voie : choisir la source `None` dans Settings > Pages, ce qui supprime le site publié sans supprimer le dépôt.
4. Pour republier plus tard, choisir de nouveau la branche `main` comme source.

Limites de la dépublication :

- Les moteurs de recherche gardent des copies en cache pendant un temps que GitHub ne contrôle pas ; la documentation de GitHub n'en parle pas.
- L'Internet Archive (web.archive.org) peut avoir archivé la page et le CV ; ces copies restent consultables.
- Les liens vers le site dans les CV, les formulaires et les briefs envoyés avant la dépublication ne mènent plus nulle part (erreur 404).
- Le dépôt public reste visible sur GitHub, avec tout son historique, tant qu'il n'est pas rendu privé ; rendre le dépôt privé coupe aussi Pages sur un compte gratuit.

Pour cette raison, le site n'utilise pas de nom de domaine personnalisé : un domaine laissé à l'abandon peut être racheté par un tiers, et la documentation de GitHub signale qu'un domaine non vérifié qui pointe encore vers Pages peut être pris par quelqu'un d'autre.
