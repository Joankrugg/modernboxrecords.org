# Modern Box — portail racine

Une page entrepreneuriale pour les initiatives créatives indépendantes, prête à servir sur https://modernboxrecords.org/ .

## Ouvrir et modifier
Ouvrir index.html dans votre navigateur. Style et JavaScript sont intégrés : pas d’installation ni compilation. Trois pages : accueil, mentions légales, 404.

## Ce qui fonctionne
- Navigation vers les sections.
- Filtres Tout explorer / Rencontrer / Développer / Jouer.
- Présentations en fenêtres modales pour les projets dont le lien manque (fermeture bouton / Échap / clic extérieur).
- Lien vers https://bands.modernboxrecords.org/ ; il faut publier le site du label préparé séparément pour que la destination soit accessible.
- Email prérempli « Présenter mon projet » ; rien n’est envoyé automatiquement.
- Email et téléphone repris exactement : modernborecords@gmail.com / 07 60 95 09 56.
- Sans JavaScript, les contenus, le label et les contacts restent accessibles. Les filtres sont masqués et un message indique les adresses manquantes.

## À compléter
1. Dans le script en fin de index.html, l’objet projects contient trois `url:null`. Remplacer chaque null par l’URL publique exacte entre guillemets pour Beertrackr, le jeu et les launchers. Pour plusieurs launchers, pointer vers leur page d’entrée.
2. Le script connecte automatiquement le bouton à l’URL et retire le texte « Lien à compléter ». Adapter aussi les intitulés et notes aux noms finaux.
3. Ajouter le nom et l’URL de l’agence, puis modifier sa carte. Son action actuelle permet de prendre contact par email.
4. Remplacer les trois partenaires entre crochets par des noms, contributions concrètes et liens confirmés. Les catégories sont des suggestions, pas des partenariats établis.
5. Compléter les mentions légales et l’entité responsable du portail. Radioleg est identifié comme porteur du label ; aucune autre structure juridique n’a été inventée.
6. Les présentations décrivent le positionnement souhaité ; confirmer que les services annoncés sont proposés avant le lancement.

Pour transformer les entrées en liens HTML directs (préférable une fois les URL connues), remplacer le `<button data-project="...">` par `<a href="URL" class="project-link">...</a>` et supprimer la note de placeholder.

## GitHub Pages — racine du domaine
Ce portail utilise un dépôt distinct du site du label. Le label garde son domaine bands.modernboxrecords.org .

1. Créer un dépôt public pour le portail (exemple : modernbox-home).
2. Déposer le CONTENU du dossier modernbox-root à la racine du dépôt. Inclure .nojekyll et CNAME.
3. Settings → Pages → Deploy from a branch → main → / (root).
4. Custom domain : modernboxrecords.org, puis Save. Configurer le domaine dans GitHub avant les DNS.
5. Chez le gestionnaire DNS du domaine, configurer l’apex :

| Type | Hôte | Cible |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | VOTRE-COMPTE-GITHUB.github.io |

L’hôte @ peut être représenté par un champ vide chez certains fournisseurs. La cible www est le compte ou l’organisation GitHub propriétaire du dépôt, sans https:// ni nom de dépôt. Ne pas modifier les MX/TXT utilisés par la messagerie. Ne pas modifier le CNAME bands existant. Remplacer les éventuelles cibles web concurrentes de la racine uniquement après identification.

6. Après validation DNS, activer Enforce HTTPS ; la propagation et le certificat peuvent prendre jusqu’à 24 h.
7. Vérifier la racine, www et bands séparément.

La vérification de propriété dans les paramètres Pages du compte est recommandée : utiliser le TXT exact fourni par GitHub.
Source vérifiée le 7 octobre 2026 : https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

## Référencement et données
Titre, description, canonical, Open Graph, favicon, robots.txt et sitemap inclus. Pas de traceur, média externe intégré ni formulaire serveur. Une image de partage peut être ajoutée ultérieurement. Le sitemap comporte l’accueil ; les mentions provisoires sont en noindex.

## Validation
Syntaxe JavaScript, filtres, ouverture/fermeture des modales, liens locaux et ancres contrôlés automatiquement. Mise en page responsive et navigation clavier prévues. Le rendu dans un vrai navigateur n’a pas pu être contrôlé dans cet environnement. Ouvrir index.html sur ordinateur et mobile avant publication pour vérifier le rendu final. DNS, publication GitHub et liens externes ne sont pas validés par cette archive.
