# Bassiste — Entraîneur de notes (PWA)

Application web qui s'installe comme une vraie app sur téléphone et ordinateur.
Tirage aléatoire d'une note × une corde, pour réviser le manche.

## 📦 Ce que contient ce dossier

```
pwa/
├── index.html              ← l'application (tout est dedans)
├── manifest.webmanifest    ← infos d'installation (nom, icônes…)
├── sw.js                   ← service worker (fonctionnement hors-ligne)
├── icon-192.png
├── icon-512.png
└── icon-maskable-512.png
```

---

## 🚀 Publier sur GitHub Pages — étape par étape

But : obtenir une URL `https://TON-PSEUDO.github.io/bassiste/` que tu peux ouvrir
sur ton téléphone, ton ordi, et envoyer à ton bassiste pour qu'il l'installe aussi.

### Étape 1 — Créer un compte GitHub (si tu n'en as pas)

1. Va sur [github.com](https://github.com) → **Sign up**
2. Crée le compte (email + mot de passe + pseudo). Gratuit.
3. Confirme ton email.

### Étape 2 — Créer un nouveau dépôt (repository)

1. En haut à droite, clique sur le **+** → **New repository**
2. Donne-lui un nom court, par ex. `bassiste`
3. Coche **Public** (obligatoire pour utiliser GitHub Pages gratuit)
4. Coche **Add a README file** (utile pour valider la création immédiatement)
5. Clique **Create repository**

### Étape 3 — Uploader les fichiers du dossier `pwa/`

1. Sur la page de ton dépôt, clique **Add file** → **Upload files**
2. **Glisse-dépose les 6 fichiers du dossier `pwa/`** (pas le dossier lui-même,
   son contenu) dans la zone d'upload
3. Tout en bas, clique **Commit changes**

### Étape 4 — Activer GitHub Pages

1. Toujours sur ton dépôt, clique l'onglet **Settings** (en haut)
2. Dans le menu de gauche, clique **Pages**
3. Sous **Source**, choisis **Deploy from a branch**
4. Sous **Branch**, choisis **main** puis **/(root)**, et clique **Save**
5. **Attends 1 à 2 minutes** (GitHub déploie en arrière-plan)
6. Rafraîchis la page : l'URL apparaît tout en haut, du genre
   `https://TON-PSEUDO.github.io/bassiste/`

C'est ta URL d'app. Elle marche partout dans le monde.

---

## 📱 Installer sur ton téléphone

### iPhone (Safari obligatoire)

1. Ouvre l'URL dans **Safari**
2. Appuie sur l'icône **Partager** (carré avec flèche vers le haut)
3. Fais défiler et choisis **Sur l'écran d'accueil**
4. Confirme **Ajouter**

Une icône Bassiste apparaît sur ton écran d'accueil. Elle s'ouvre en plein écran,
sans la barre d'adresse, et fonctionne **hors-ligne** une fois ouverte une première fois.

### Android (Chrome)

1. Ouvre l'URL dans **Chrome**
2. Une bannière **"Installer"** apparaît en bas, ou via le menu ⋮ → **Installer l'application**
3. Confirme

Pareil : icône, plein écran, hors-ligne.

---

## 💻 Installer sur ton ordinateur

### Chrome / Edge

1. Ouvre l'URL
2. Dans la barre d'adresse, une petite **icône d'installation** (écran + flèche) apparaît à droite
3. Clique-la → **Installer**

L'app se lance comme un logiciel : raccourci dans le menu Démarrer / Launchpad,
icône dans le Dock / Barre des tâches, fenêtre dédiée sans onglets.

### Safari (Mac, depuis macOS 14+)

1. Ouvre l'URL
2. Menu **Fichier** → **Ajouter au Dock**

---

## 👥 Partager avec ton bassiste

Envoie-lui juste l'URL `https://TON-PSEUDO.github.io/bassiste/` (SMS, mail, Signal…).
Il suit l'étape "Installer sur ton téléphone" ci-dessus. Pas besoin de compte,
de store, de rien.

---

## 🔄 Mettre à jour l'app

Quand tu changes l'app (nouvelle version), tu :

1. Va sur ton dépôt GitHub
2. **Add file → Upload files** et glisse les nouveaux fichiers (écrasement OK)
3. **Commit changes**
4. Attends 1-2 min → l'app installée se met à jour automatiquement au prochain lancement
   (le service worker détecte la nouvelle version).

> Astuce : pour forcer la mise à jour immédiate, incrémente la ligne
> `const CACHE = 'bassiste-v1';` dans `sw.js` (passer à `v2`, etc).

---

## 🐛 Si quelque chose ne marche pas

- **L'URL renvoie une 404** → attends 2 min, GitHub Pages prend un moment au 1er déploiement
- **L'app ne s'installe pas** → vérifie que tu es bien en HTTPS (l'URL GitHub Pages l'est),
  et que `manifest.webmanifest` est bien à la racine (au même niveau que `index.html`)
- **Pas de hors-ligne** → ouvre l'app une 1ère fois en ligne pour que le SW se cache,
  puis ferme et rouvre

Bonne révision 🎸
