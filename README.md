# SOS DIGITAL — Application de Facturation

Application web de facturation professionnelle entièrement rebrandée SOS DIGITAL.

## Fonctionnalités

- **Tableau de bord** : métriques CA, graphiques de tendance, top clients
- **Factures & Devis** : création, prévisualisation, export PDF, conversion devis→facture
- **Multi-templates** : Classique Professionnel + Moderne Minimaliste
- **Clients (CRM)** : fiches clients, statuts actif/inactif/VIP, historique
- **Catalogue** : services récurrents avec prix pré-remplis
- **Rapports** : export PDF/Excel, filtres par période et client
- **Bilingue FR/EN** : interface + factures générées dans la langue choisie
- **WhatsApp** : bouton flottant + partage de factures (+237 653 522 435)

## Démarrage rapide

```bash
# Ouvrir directement dans le navigateur
open index.html

# Ou servir localement
npx serve .
# ou
python3 -m http.server 8080
```

## Structure des fichiers

```
sos-digital/
├── index.html              ← Application principale (SPA complète)
├── src/
│   └── i18n/
│       ├── fr.json         ← Traductions françaises
│       └── en.json         ← Traductions anglaises
└── README.md
```

## Configuration

### Numéro WhatsApp
Dans `index.html`, rechercher `237653522435` pour modifier le numéro.

### Couleurs de la marque
Les variables CSS dans `:root` :
```css
--sky: #0EA5E9;        /* Bleu ciel principal */
--sky-dark: #0369A1;   /* Bleu foncé */
--brown: #92400E;      /* Marron */
--brown-dark: #78350F; /* Marron foncé */
```

### Ajouter un template
1. Créer une nouvelle classe CSS `.inv-mytemplate`
2. Ajouter l'option dans `tpl-cards` du modal
3. Gérer le rendu dans `openPreviewModal()`

## Déploiement

### Option 1 — Hébergement statique (recommandé)
Déposer `index.html` sur : Netlify, Vercel, GitHub Pages, ou tout hébergeur web.

### Option 2 — Docker
```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/
EXPOSE 80
```
```bash
docker build -t sos-digital .
docker run -p 80:80 sos-digital
```

### Option 3 — Extension backend (Node.js)
Pour la persistance des données, connecter à une API REST :
```
POST /api/invoices
GET  /api/invoices
GET  /api/customers
POST /api/customers
```

## Contact
SOS DIGITAL — WhatsApp : +237 653 522 435
