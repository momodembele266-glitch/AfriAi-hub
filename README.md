# 🌍 AfriAI Hub — Guide de démarrage en 15 minutes

## 📁 Structure des fichiers

```
afriai/
├── index.html      → Page d'accueil avec chatbot intégré
├── chat.html       → Interface chat complète (style ChatGPT)
├── tools.html      → Outils IA (CV, Traducteur, Marché, Agriculture, Business)
├── pricing.html    → Tarifs freemium (USD / FCFA)
└── README.md       → Ce guide
```

---

## ⚡ Démarrage immédiat (0 configuration)

1. **Télécharge** les 4 fichiers HTML
2. **Ouvre** `index.html` dans ton navigateur
3. **C'est prêt !** — Le site fonctionne sans serveur

> Tous les outils ont un mode hors-ligne avec réponses simulées.

---

## 🤖 Activer le vrai Chat IA (Claude)

Pour activer les vraies réponses IA, tu as 2 options :

### Option A — Sans serveur (développement)
Le site appelle directement l'API Anthropic. Cela fonctionne uniquement si tu n'exposes pas ta clé publiquement.

**Ajoute ta clé API dans les 3 fichiers HTML :**
Cherche la ligne :
```javascript
headers: { "Content-Type": "application/json" },
```
Et ajoute juste après :
```javascript
"x-api-key": "sk-ant-VOTRE_CLE_ICI",
"anthropic-version": "2023-06-01",
"anthropic-dangerous-direct-browser-access": "true",
```

> ⚠️ Ne partage JAMAIS un fichier HTML avec ta clé API visible !

### Option B — Avec serveur proxy (recommandé pour production)
Crée un petit serveur Node.js ou utilisez un service serverless (Vercel Functions, Netlify Functions) qui garde ta clé en sécurité.

---

## 🌐 Mise en ligne gratuite (Vercel / Netlify)

### Via Vercel (recommandé) :
1. Crée un compte sur [vercel.com](https://vercel.com)
2. Drag & drop ton dossier `afriai/` dans l'interface
3. Ton site est en ligne en 60 secondes sur une URL gratuite

### Via Netlify :
1. Va sur [netlify.com/drop](https://app.netlify.com/drop)
2. Glisse ton dossier `afriai/`
3. Site en ligne instantanément

---

## 🔧 Personnalisation rapide

### Changer le nom du site :
- Cherche `AfriAI Hub` dans tous les fichiers
- Remplace par ton nom

### Changer les couleurs :
Dans chaque fichier HTML, modifie les variables CSS :
```css
:root {
  --green: #00A651;   /* Vert principal */
  --gold: #FFD700;    /* Or/accent */
  --bg: #0A0F0D;      /* Fond sombre */
}
```

### Ajouter des langues :
Dans `index.html`, cherche `translations` et ajoute tes traductions.

---

## 💰 Activer les paiements

### Stripe (cartes bancaires internationales) :
```html
<script src="https://js.stripe.com/v3/"></script>
```
Crée un compte sur [stripe.com](https://stripe.com) → Obtiens ta clé publique.

### Flutterwave (Mobile Money Afrique) :
```html
<script src="https://checkout.flutterwave.com/v3.js"></script>
```
Compte sur [flutterwave.com](https://flutterwave.com) — supporte Orange Money, MTN, M-Pesa, Wave.

---

## 📱 Installer comme App (PWA)

Pour que les utilisateurs puissent installer AfriAI Hub sur Android/iPhone :

1. Crée un fichier `manifest.json` :
```json
{
  "name": "AfriAI Hub",
  "short_name": "AfriAI",
  "start_url": "/index.html",
  "display": "standalone",
  "background_color": "#0A0F0D",
  "theme_color": "#00A651",
  "icons": [{"src": "icon.png", "sizes": "192x192", "type": "image/png"}]
}
```

2. Ajoute dans le `<head>` de chaque page :
```html
<link rel="manifest" href="manifest.json">
```

---

## 🔑 Obtenir une clé API Claude

1. Va sur [console.anthropic.com](https://console.anthropic.com)
2. Crée un compte (gratuit)
3. Génère une clé API
4. Les 5 premiers dollars sont offerts (~1000 requêtes)

---

## ❓ Support

- Chat IA : `chat.html` fonctionne immédiatement en mode simulé
- Outils : Tous fonctionnent en local sans API
- Tarifs : Page `pricing.html` prête, intègre Stripe/Flutterwave

---

*Fait avec ❤️ pour l'Afrique 🌍 — AfriAI Hub 2026*
