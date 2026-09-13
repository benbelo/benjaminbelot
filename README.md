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

## DNS (Route 53)

Le domaine est enregistré **via AWS Route 53** (le registre .fr passe par Gandi, partenaire d'AWS — c'est normal). Les enregistrements se créent donc dans la **zone hébergée Route 53** de `benjaminbelot.fr` (NS `ns-1468.awsdns-55.org` et consorts), **pas** chez Gandi.

⚠️ Tant que la délégation `.fr` n'a pas basculé sur ces NS AWS, les résolveurs peuvent encore renvoyer la zone de parking Gandi (`A @ → 217.70.184.38`) — c'est transitoire, ça disparaît tout seul.

| Type  | Nom | Valeur |
|-------|-----|--------|
| A     | `benjaminbelot.fr` (@) | `185.199.108.153` |
| A     | `benjaminbelot.fr` (@) | `185.199.109.153` |
| A     | `benjaminbelot.fr` (@) | `185.199.110.153` |
| A     | `benjaminbelot.fr` (@) | `185.199.111.153` |
| AAAA  | `benjaminbelot.fr` (@) | `2606:50c0:8000::153` |
| AAAA  | `benjaminbelot.fr` (@) | `2606:50c0:8001::153` |
| AAAA  | `benjaminbelot.fr` (@) | `2606:50c0:8002::153` |
| AAAA  | `benjaminbelot.fr` (@) | `2606:50c0:8003::153` |
| CNAME | `www.benjaminbelot.fr` | `benbelo.github.io` |

Une fois ces enregistrements propagés et le certificat HTTPS émis par GitHub, activer **Enforce HTTPS**
dans les réglages GitHub Pages du repo (Settings → Pages).
