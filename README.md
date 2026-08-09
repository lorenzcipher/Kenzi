# Kenzi — Landing Page

Landing page (page d'atterrissage) en français pour **Kenzi**, l'application mobile de budget personnel pour l'Algérie (montants en dinar, DA).

Fichier unique et autonome : `index.html`. Aucune dépendance, aucun build, aucun `npm install` — c'est du HTML/CSS/JS pur, prêt à être déployé tel quel.

---

## 📁 Contenu

```
kenzi-landing/
├── index.html      → la page complète (SEO, styles, animations, JS inline)
└── README.md        → ce fichier
```

Le logo Kenzi est encodé directement dans le fichier (en base64), donc il n'y a pas d'images externes à gérer.

---

## ✨ Ce que contient la page

- Balises SEO complètes (title, meta description, Open Graph, Twitter Card, JSON-LD)
- Thème navy `#0F1826` / gold `#C9A227`, polices Fraunces + Inter + IBM Plex Mono
- Mockup de téléphone avec tableau de bord animé
- Animations : entrée en fondu du hero, texte doré scintillant, badges flottants, tracé progressif du graphique, effet de brillance sur les boutons, motif "guilloché" en fond
- Respect de `prefers-reduced-motion` : toutes les animations sont désactivées si l'utilisateur l'a demandé dans son système

---

## 🚀 Déployer sur Vercel

Aucune configuration n'est nécessaire : Vercel sert automatiquement un `index.html` à la racine comme site statique. Les animations sont en CSS/JS pur et s'exécutent directement dans le navigateur — **elles fonctionnent dès la mise en ligne, sans étape supplémentaire.**

### Option A — Import direct sur vercel.com (le plus simple)
1. Allez sur [vercel.com/new](https://vercel.com/new)
2. Choisissez **"Deploy without Git"** / glissez-déposez le dossier `kenzi-landing`
3. Vercel détecte le site comme statique et le déploie — c'est tout

### Option B — Via GitHub
1. Créez un repo GitHub et poussez-y ce dossier (`index.html` + `README.md`)
2. Sur [vercel.com/new](https://vercel.com/new), importez le repo
3. Laissez le "Framework Preset" sur **Other** et le "Build Command" vide (rien à compiler)
4. Cliquez sur **Deploy**

### Option C — Via la CLI Vercel
```bash
npm install -g vercel
cd kenzi-landing
vercel --prod
```

Après le déploiement, ouvrez l'URL fournie par Vercel : les animations d'entrée se déclenchent automatiquement au chargement, et les animations au scroll (`IntersectionObserver`) se déclenchent en descendant la page.

---

## 🔧 À personnaliser avant mise en ligne

- Remplacer `kenzi.app` par votre vrai nom de domaine dans les balises `canonical`, `og:url`, `og:image`, `twitter:image`
- Remplacer les liens `href="#"` des boutons App Store / Google Play par vos vraies URLs
- Ajouter une vraie image `og-image.jpg` (1200×630px) hébergée sur votre domaine, pour les aperçus de partage sur les réseaux sociaux

---

## 🖥️ Tester en local

Pas besoin de serveur — ouvrez simplement `index.html` dans un navigateur. Pour un rendu plus proche de la production (chemins relatifs, etc.), vous pouvez aussi lancer un petit serveur local :

```bash
cd kenzi-landing
python3 -m http.server 8000
# puis ouvrez http://localhost:8000
```
