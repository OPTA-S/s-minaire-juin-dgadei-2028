# Carte postale 2028 — DGA DEI

Icebreaker collaboratif de 5 minutes pour le séminaire DGA DEI du 17 juin 2026. Chaque participant scanne un QR code, choisit un emoji et écrit un mot d'espoir pour 2028. Sur l'écran de projection, une grande carte postale collective se construit en direct.

## Démarrer en 3 minutes (GitHub Pages)

### Étape 1 — Créer le repository

Aller sur `github.com`, cliquer **New repository**, le nommer par exemple `dgadei-2028`, le laisser **public**, cocher **Add a README**, valider. Puis cliquer sur **Upload files** et déposer `index.html` (le seul fichier nécessaire). Commit directement sur `main`.

### Étape 2 — Activer GitHub Pages

Dans le repository, aller dans **Settings → Pages**. Sous *Build and deployment*, sélectionner **Deploy from a branch**, choisir la branche `main` et le dossier `/ (root)`. Valider. Au bout de 30 à 60 secondes, GitHub affiche l'URL publique : `https://<ton-pseudo>.github.io/dgadei-2028/`.

### Étape 3 — Tester

Ouvrir cette URL au navigateur sur l'ordinateur de projection : l'écran de projection s'affiche avec le QR code. Scanner le QR avec un téléphone : la version mobile s'ouvre avec le formulaire. C'est prêt.

## Activer la synchro temps réel (Firebase)

Sans Firebase, l'application fonctionne en **mode démo local** : la console discrète en bas à gauche permet à l'animateur d'ajouter des cartes pré-écrites à la volée. Pour collecter de vraies réponses en direct, suivre les 3 étapes Firebase.

### 1. Créer un projet Firebase (3 min)

`console.firebase.google.com` → connexion Google → **Ajouter un projet** → nommer `dgadei-2026` → désactiver Google Analytics → valider. Dans le menu de gauche, **Build → Realtime Database → Créer une base de données** → région **Europe** → mode **Test** (lecture/écriture publiques 30 jours).

### 2. Récupérer la configuration (1 min)

Roue dentée (haut-gauche) → **Paramètres du projet** → faire défiler jusqu'à *Vos applications* → cliquer sur l'icône web `</>` → nommer `postcard` → valider. Firebase affiche un bloc `firebaseConfig`. Copier les 5 valeurs : `apiKey`, `authDomain`, `databaseURL`, `projectId`, `appId`.

### 3. Coller dans `index.html` (1 min)

Ouvrir `index.html`, repérer le bloc :

```js
const FB_CONFIG = {
  apiKey:       "",
  authDomain:   "",
  databaseURL:  "",
  projectId:    "",
  appId:        ""
};
```

Coller les valeurs Firebase entre les guillemets, commit, push. GitHub Pages redéploie automatiquement en 30 secondes.

## Animation pendant le séminaire

**Avant l'ouverture** — Ouvrir l'URL GitHub Pages dans un navigateur, brancher la projection, basculer en plein écran (F11). Le QR code s'affiche en haut à droite et pointe vers la version mobile.

**Lancement (1 min)** — « Avant d'entrer dans le vif, je vous propose un voyage. Vous êtes en 2028. La feuille de route est livrée. Vous prenez une carte postale et vous vous l'écrivez à vous-mêmes : un emoji qui dit l'ambiance, un mot qui dit l'espoir. Scannez le QR. »

**Pendant (2 min)** — Les cartes apparaissent une à une avec une animation de chute douce. Laisser le silence travailler. Si le rythme ralentit, lire deux ou trois cartes à voix haute.

**Bouclage (1-2 min)** — « Voilà notre boussole pour la journée. Si à 17 h on a écrit ces mots ensemble, on aura bien travaillé. » Garder l'écran ouvert toute la journée — il sert de générique entre les séquences.

**À la fin** — La console discrète en bas à gauche permet d'effacer toutes les cartes (RAZ). Si Firebase est activé, supprimer aussi la base ou la désactiver.

## Console animateur

Au survol du coin inférieur gauche, une mini-console apparaît :

- **Vue** — bascule entre vue projection et vue mobile (utile pour tester)
- **Démo +1** — ajoute une carte pré-écrite (12 messages variés en rotation)
- **RAZ** — efface toutes les cartes après confirmation

Idéal pour piloter en mode hybride : Firebase activé + démo en ceinture-bretelles si le Wi-Fi flanche.

## Personnaliser

Les 12 emojis disponibles sont définis dans le code (`const EMOJIS = […]`). Modifier la liste pour adapter au contexte. La couleur principale (orange OPTA-S #FF6600) et la couleur titre (navy #002D69) sont des variables CSS en haut du fichier (`:root { --orange: …; --navy: … }`).

## Crédits

OPTA-S × Région Réunion — Séminaire DGA DEI · 17 juin 2026
