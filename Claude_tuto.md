[Claude_tuto.md](https://github.com/user-attachments/files/28273178/README.md)
# 🎮 Rush Action Game — Carte Boissons & Snacking

Site web de la carte interactive, éditable sans compétences techniques.

---

## 📁 Structure du projet

```
rush-carte/
├── index.html          ← Page principale (ne pas modifier sauf si vous savez)
├── css/
│   └── style.css       ← Mise en page et couleurs
├── js/
│   ├── data.js         ← ⭐ DONNÉES : produits, prix, fournisseurs (modifiez ici !)
│   └── app.js          ← Logique d'affichage (ne pas modifier)
└── assets/
    └── logos/          ← Logos fournisseurs (PNG)
        ├── SM.png      (Sterne & Mousse)
        ├── CV.png      (Château de la Viaudière)
        ├── BB.png      (Bibibulles)
        ├── MS.png      (Maison Specht)
        ├── FC.png      (Flavie's & Co)
        ├── SC.png      (So Chips)
        ├── RUSH.png    (Rush Action Game)
        ├── ECLAIR.png  (Éclair)
        └── DES.png     (Dés)
```

---

## 🚀 Mise en ligne (première fois)

### Étape 1 — Créer un compte GitHub
1. Allez sur [github.com](https://github.com) → **Sign up**
2. Choisissez un nom d'utilisateur (ex: `rush-action-game`)
3. Validez l'email de confirmation

### Étape 2 — Créer le dépôt
1. Cliquez sur **New repository** (bouton vert)
2. Nom du dépôt : `carte-boissons`
3. Visibilité : **Public** (obligatoire pour Netlify gratuit)
4. Cochez **Add a README file**
5. Cliquez **Create repository**

### Étape 3 — Uploader les fichiers
**Option A — Interface web GitHub (plus simple)**
1. Dans votre dépôt, cliquez **Add file → Upload files**
2. Glissez-déposez tous les fichiers du projet
3. Important : respectez la structure des dossiers
4. Cliquez **Commit changes**

**Option B — GitHub Desktop (recommandé pour la suite)**
1. Téléchargez [GitHub Desktop](https://desktop.github.com)
2. Connectez-vous avec votre compte GitHub
3. File → Clone Repository → choisissez `carte-boissons`
4. Copiez les fichiers du projet dans le dossier cloné
5. Cliquez **Commit to main** puis **Push origin**

### Étape 4 — Déployer sur Netlify
1. Allez sur [netlify.com](https://netlify.com) → **Sign up with GitHub**
2. Cliquez **Add new site → Import an existing project**
3. Choisissez **GitHub** → autorisez Netlify
4. Sélectionnez le dépôt `carte-boissons`
5. Paramètres de build : laissez tout vide
6. Cliquez **Deploy site**

✅ Votre site est en ligne sur une URL du type `https://amazing-name-12345.netlify.app`

**Pour un domaine personnalisé :** dans Netlify → Domain settings → Add custom domain

---

## ✏️ Modifier les prix et produits

### Méthode 1 — Sur GitHub directement (rapide)
1. Ouvrez votre dépôt GitHub
2. Cliquez sur `js/data.js`
3. Cliquez sur l'icône crayon ✏️ (Edit this file)
4. Modifiez les valeurs souhaitées
5. Cliquez **Commit changes**
6. Le site se met à jour automatiquement en 30 secondes !

### Méthode 2 — Via le mode édition du site
1. Ouvrez le site
2. Cliquez **✏️ Modifier** en haut
3. Entrez le mot de passe
4. Modifiez les textes directement à l'écran
5. Cliquez **✅ Terminer**

> ⚠️ Note : les modifications via le mode édition du site ne sont pas permanentes (elles disparaissent au rechargement). Pour des changements définitifs, modifiez `data.js` sur GitHub.

---

## 📝 Comment modifier `data.js`

### Changer un prix
```js
// Avant
{ nom: "Thé Vert Pêche", prix: "2,50€", ... }

// Après
{ nom: "Thé Vert Pêche", prix: "2,80€", ... }
```

### Ajouter un produit
Copiez un bloc existant et ajoutez-le à la liste :
```js
softs: [
  // ... produits existants ...
  {
    id: "nouveau-prod",           // identifiant unique (sans espaces)
    nom: "Nom du produit",
    description: "Description",
    volume: "33cL",              // ou null
    prix: "3,00€",
    prix2: null,                 // 2e prix (ex: 50cL) ou null
    bio: true,
    fournisseur: "SM",           // code fournisseur
    photo: null,
    visible: true
  }
]
```

### Masquer un produit (sans le supprimer)
```js
{ nom: "Produit", visible: false, ... }
```

### Changer le mot de passe
```js
config: {
  mot_de_passe_edition: "VotreNouveauMotDePasse"
}
```

---

## 🖼️ Ajouter un logo fournisseur
1. Préparez votre image en PNG (fond blanc ou transparent)
2. Nommez-la avec le code fournisseur (ex: `SM.png`)
3. Uploadez-la dans `assets/logos/` sur GitHub
4. Dans `data.js`, vérifiez que `logo: "assets/logos/SM.png"`

---

## 🎨 Changer les couleurs
Dans `css/style.css`, modifiez les variables au début :
```css
:root {
  --rose:   #EC008C;   /* couleur principale */
  --bleu:   #48AAD0;   /* couleur secondaire */
}
```

---

## 💡 Éditeurs recommandés pour modifier le code

| Outil | Niveau | Lien |
|-------|--------|------|
| **GitHub.dev** | Débutant | Appuyez sur `.` dans votre dépôt GitHub |
| **VS Code** | Intermédiaire | [code.visualstudio.com](https://code.visualstudio.com) |
| **Cursor** | Intermédiaire+ | [cursor.sh](https://cursor.sh) — VS Code avec IA intégrée |

### GitHub.dev (le plus simple)
1. Ouvrez votre dépôt GitHub
2. Appuyez sur la touche `.` (point) du clavier
3. Un VS Code s'ouvre dans le navigateur !
4. Modifiez `js/data.js`
5. Ctrl+S pour sauvegarder → le site se met à jour

---

## 🔄 Workflow quotidien recommandé

```
Modifier data.js sur GitHub.dev
    ↓ (automatique, ~30 secondes)
Site Netlify mis à jour
    ↓
QR code → clients voient les nouveaux prix
```

---

## 📞 Besoin d'aide ?
Si quelque chose ne fonctionne pas, les informations à fournir :
- L'URL de votre dépôt GitHub
- Le message d'erreur exact
- Ce que vous essayiez de faire
