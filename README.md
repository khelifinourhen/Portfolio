# Portfolio — Nourhen Khelifi

Site statique (HTML, CSS, JavaScript). Aucun build nécessaire : le dossier est déjà prêt à être publié.

## Structure

- `index.html` : toute la page (contenu, styles, scripts)
- `frames/` : 80 images de la vidéo (fond transparent) pour l'animation au défilement
- `assets/` : photos des projets, `resume.pdf` (bouton Download résumé), `lybrinthia-report.pdf`

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

## À vérifier avant de rendre le dépôt public

- `assets/resume.pdf` contient ton numéro de téléphone (visible par tout le monde) : remplace-le par une version sans téléphone si tu préfères.
- Plusieurs images de projets montrent des identifiants (admin/admin123), des visages ou des noms de coéquipiers : floute-les ou retire-les.
