# Portfolio — Nourhen Khelifi

Site statique (HTML, CSS, JavaScript). Aucun build nécessaire : le dossier est déjà prêt à être publié.

## Structure

- `index.html` : toute la page (contenu, styles, scripts)
- `frames/` : 238 images de la vidéo (fond transparent) pour l'animation au défilement : les 80 images d'origine plus des images intermédiaires calculées (interpolation par flux optique) pour un mouvement fluide
- `assets/` : photos des projets, `resume.pdf` (CV anglais, bouton Download résumé), `resume-fr.pdf` (CV français), `lybrinthia-report.pdf`

## Tester en local

    python3 -m http.server 8000
    # puis ouvrir http://localhost:8000

(Ne pas ouvrir index.html en double-cliquant : les images ne se chargent pas depuis file://.)

## Publier gratuitement (au choix)

### GitHub Pages
1. Créer un dépôt public sur GitHub (ex. `portfolio`, ou `khelifinourhen.github.io` pour une URL à la racine).
2. Pousser ce dossier (voir ci-dessous).
3. Settings → Pages → Source : Deploy from a branch → `main` / `(root)` → Save.
4. Le site apparaît sur https://khelifinourhen.github.io/portfolio/ (1 à 2 minutes).

### Netlify, Vercel, Cloudflare Pages ou Render (Static Site)
1. New project → Import from GitHub → choisir le dépôt.
2. Build command : vide. Publish / output directory : `.` (la racine).
3. Chaque `git push` redéploie automatiquement. Chaque branche ou Pull Request peut avoir sa propre URL d'aperçu.

## Premier envoi sur GitHub

    git init
    git add .
    git commit -m "Portfolio v1.0"
    git branch -M main
    git remote add origin https://github.com/khelifinourhen/portfolio.git
    git push -u origin main
    git tag v1.0 && git push --tags

## Faire une modification (nouvelle version)

    git checkout -b maj-projets        # facultatif : une branche par changement
    # modifier index.html ou ajouter des images dans assets/
    git add . && git commit -m "Ajout du projet X"
    git push -u origin maj-projets     # aperçu sur Netlify/Vercel/Cloudflare
    git checkout main && git merge maj-projets && git push
    git tag v1.1 && git push --tags    # pour garder cette version


## Formulaire de contact

Le bouton « Send me a message » (section Contact) ouvre un formulaire.

- **Sans configuration** : à l'envoi, le formulaire ouvre le logiciel de mail du visiteur avec le message déjà rempli, à destination de khelifi.nourhen@gmail.com.
- **Avec un service gratuit (recommandé)** : les messages arrivent directement dans ta boîte mail, sans que le visiteur ait besoin d'un logiciel de mail.
  1. Créer un compte gratuit sur https://formspree.io, puis « New form » avec ton adresse e-mail.
  2. Copier l'adresse du formulaire (elle ressemble à `https://formspree.io/f/abcdwxyz`).
  3. Dans `index.html`, chercher `const FORM_ENDPOINT="";` et coller l'adresse entre les guillemets :

         const FORM_ENDPOINT="https://formspree.io/f/abcdwxyz";

  4. `git add . && git commit -m "Formulaire de contact" && git push`
  5. Faire un envoi test depuis le site en ligne, puis confirmer l'adresse e-mail demandée par Formspree.

Le formulaire ne fonctionne en envoi direct que sur le site publié (GitHub Pages, Netlify…), pas dans l'aperçu Claude.
Un champ caché anti-spam est déjà en place. Le formulaire gratuit de Formspree est limité à quelques dizaines de messages par mois.

## À vérifier avant de rendre le dépôt public

- `assets/resume.pdf` et `assets/resume-fr.pdf` contiennent ton numéro de téléphone (visible par tout le monde) : remplace-le par une version sans téléphone si tu préfères.
- Plusieurs images de projets montrent des identifiants (admin/admin123), des visages ou des noms de coéquipiers : floute-les ou retire-les.
