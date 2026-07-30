# P'tit Bac 🅱️

> Créé par Aurélien Moote - Moo - 2026. Logiciel libre (licence MIT) :
> réutilisable à condition de conserver la mention de l'auteur.

Le jeu du **Petit Bac** (ou Baccalauréat) en une seule page HTML, pensée pour le
smartphone et **jouable entièrement hors ligne**.

👉 **[Jouer en ligne](https://auremoo.github.io/ptit-bac/)**

## Fonctionnalités

- **Une seule page** : `index.html` se suffit à lui-même, aucun réseau, aucune dépendance.
- **Catégories par défaut** (Prénom, Animal, Ville, Pays, Métier, Objet, Fruit ou légume, Couleur)
  que l'on peut activer, désactiver, **ajouter ou supprimer** — y compris **en pleine manche**.
- **Suggestions** de catégories en un tap (Marque, Film ou série, Sport, Plat…).
- **Tirage de lettre** animé, sans répétition tant que l'alphabet n'est pas épuisé,
  avec une option « lettres faciles » qui retire K, Q, W, X, Y, Z.
- **Chronomètre** 1:00 / 1:30 / 2:00 / 3:00 ou mode libre, avec barre de progression,
  bips des 10 dernières secondes et vibration.
- **Comptage assisté** : les réponses qui ne commencent pas par la bonne lettre sont
  signalées, le score 0 / 1 / 2 se règle d'un tap, le total de la partie est cumulé.
- **Reprise automatique** : la manche en cours et les scores sont sauvegardés localement.
- **Ergonomie mobile** : zones tactiles larges, encoche et barre gestuelle respectées,
  thème clair/sombre automatique, écran maintenu allumé pendant la manche.

## Jouer hors ligne

Tout le jeu tient dans `index.html` : aucune requête réseau, aucune dépendance, aucun
compte. Deux façons de l'emporter partout.

### 📱 iPhone / iPad (Safari) — recommandé

1. Ouvre **https://auremoo.github.io/ptit-bac/** dans **Safari** (l'installation ne
   fonctionne que depuis Safari, pas depuis Chrome ni depuis un lien ouvert dans
   Instagram, WhatsApp ou Messages — si c'est le cas, fais « Ouvrir dans Safari »).
2. Touche le bouton **Partager** (le carré avec une flèche vers le haut, en bas de
   l'écran).
3. Fais défiler et choisis **« Sur l'écran d'accueil »**, puis **Ajouter**.
4. Une icône « P'tit Bac » apparaît sur ton écran d'accueil : lance-la **une fois avec
   du réseau** pour que tout soit mis en cache.

C'est fini : l'app s'ouvre ensuite en plein écran (sans barre Safari) et fonctionne en
**mode avion, dans le métro, en voiture, à l'étranger sans data**. Les scores, les
catégories et la manche en cours sont enregistrés sur le téléphone.

> ℹ️ Sur iPhone, garde l'icône sur l'écran d'accueil : iOS peut effacer les données
> d'un site web ordinaire après quelques semaines sans visite, mais pas celles d'une app
> ajoutée à l'écran d'accueil.

### 🤖 Android (Chrome, Edge, Samsung Internet)

1. Ouvre **https://auremoo.github.io/ptit-bac/**.
2. Une bannière **« Installer l'application »** apparaît en général en bas — accepte-la.
   Sinon, menu **⋮** → **Installer l'application** / **Ajouter à l'écran d'accueil**.
3. Lance l'app une fois connecté, puis joue hors ligne à volonté.

### 💻 Ordinateur (Chrome, Edge)

Ouvre le site, clique sur l'icône **⊕ / Installer** à droite de la barre d'adresse
(ou menu ⋮ → *Installer P'tit Bac*). L'app s'ouvre dans sa propre fenêtre, hors ligne
comprise. Sur Firefox et Safari macOS, l'installation n'existe pas : utilise la méthode
« fichier seul » ci-dessous.

### 💾 Sans installation : le fichier seul

Récupère `index.html` (bouton **Code → Download ZIP** sur GitHub, ou
[téléchargement direct](https://raw.githubusercontent.com/auremoo/ptit-bac/main/index.html))
et ouvre-le d'un double-clic : le jeu fonctionne tel quel, sans réseau.

- **Sur iPhone** : enregistre le fichier dans l'app **Fichiers** (iCloud Drive ou
  « Sur mon iPhone ») et touche-le pour l'ouvrir dans Safari. Tu peux aussi l'envoyer
  par **AirDrop** à tes amis pour jouer à plusieurs, chacun sur son téléphone.
- **Partage hors ligne** : le fichier fait quelques dizaines de kilo-octets et se
  transmet par AirDrop, Bluetooth, e-mail ou clé USB. C'est le jeu complet.
- Seule différence avec la version installée : ouvert en `file://`, il reste dans
  l'onglet du navigateur (pas d'icône ni de plein écran) et chaque copie garde ses
  propres scores.

### En cas de souci

- **Rien ne s'affiche hors ligne après l'installation** : relance l'app une fois avec
  du réseau, l'écran d'accueil doit s'afficher entièrement — c'est ce passage qui
  remplit le cache (`sw.js`).
- **Une mise à jour ne s'affiche pas** : ferme complètement l'app puis rouvre-la
  connectée ; la nouvelle version est récupérée en tâche de fond et s'applique au
  lancement suivant.
- **Le bouton « Ajouter à l'écran d'accueil » est absent sur iPhone** : tu es en
  navigation privée ou dans un navigateur intégré à une autre app — rouvre le lien dans
  Safari en mode normal.

## Règles

Une lettre est tirée au sort. Chaque joueur remplit une case par catégorie avec un mot
commençant par cette lettre, avant la fin du temps. Le premier qui a tout rempli crie
« Stop ! ». Comptage : **2 points** pour une réponse unique, **1 point** en cas de
doublon avec un autre joueur, **0** si la case est vide ou invalide.

## Publication (GitHub Pages)

Le dépôt se publie tel quel : dans **Settings → Pages**, choisis la source
**GitHub Actions** (le workflow `.github/workflows/pages.yml` est fourni) ou
**Deploy from a branch → `main` / root**. Le site est alors servi sur
`https://<utilisateur>.github.io/ptit-bac/`.

## Structure

| Fichier | Rôle |
| --- | --- |
| `index.html` | Le jeu complet : HTML, CSS et JavaScript en un seul fichier |
| `manifest.webmanifest` | Manifeste PWA (nom, icônes, mode plein écran) |
| `sw.js` | Service worker : mise en cache pour le hors ligne |
| `icon-*.png`, `apple-touch-icon.png` | Icônes de l'app (écran d'accueil iOS/Android, onglet) |
| `.github/workflows/pages.yml` | Déploiement automatique sur GitHub Pages |

## Auteur & licence

**Aurélien Moote - Moo - 2026**

Copyright (c) 2026 Aurélien Moote ("Moo"). Distribué sous **licence MIT** (voir
[`LICENSE`](LICENSE)) : libre de réutilisation, de modification et de redistribution,
à condition de conserver la mention de l'auteur — Aurélien Moote - Moo - 2026 —
et l'avis de licence. Voir aussi [`NOTICE`](NOTICE) et [`AUTHORS`](AUTHORS).
