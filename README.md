# benjaminbelot

Site personnel de Benjamin Belot (page perso + CV), servi par **GitHub Pages** sur le domaine
personnalisé `benjaminbelot.fr`.

Contenu :
- `index.html` — la page perso (design et contenu à ne pas modifier sans raison).
- `cv-fr.pdf` / `cv-eng.pdf` — les CV en français et en anglais, liés depuis `index.html`.
- `CNAME` — déclare le domaine personnalisé pour GitHub Pages.
- `.nojekyll` — désactive le traitement Jekyll (le site est servi tel quel).

## Mettre à jour un CV

1. Remplacer le fichier `cv-fr.pdf` ou `cv-eng.pdf` par la nouvelle version (même nom de fichier).
2. `git add cv-fr.pdf` (ou `cv-eng.pdf`)
3. `git commit -m "cv: mise à jour du CV fr"` (adapter le message)
4. `git push`

Le site se met à jour automatiquement après le push (déploiement GitHub Pages, en général sous 1-2 minutes).

## DNS à créer chez Gandi

Chez Gandi, sur la zone DNS de `benjaminbelot.fr`, créer les enregistrements suivants :

| Type  | Nom | Valeur |
|-------|-----|--------|
| A     | @   | `185.199.108.153` |
| A     | @   | `185.199.109.153` |
| A     | @   | `185.199.110.153` |
| A     | @   | `185.199.111.153` |
| AAAA  | @   | `2606:50c0:8000::153` |
| AAAA  | @   | `2606:50c0:8001::153` |
| AAAA  | @   | `2606:50c0:8002::153` |
| AAAA  | @   | `2606:50c0:8003::153` |
| CNAME | www | `benbelo.github.io.` |

Une fois ces enregistrements propagés et le certificat HTTPS émis par GitHub, activer **Enforce HTTPS**
dans les réglages GitHub Pages du repo (Settings → Pages).
