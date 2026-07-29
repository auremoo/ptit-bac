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

**Option 1 — le fichier seul.** Télécharge `index.html` et ouvre-le : tout le jeu est
dedans, il fonctionne sans connexion et sans installation.

**Option 2 — installer la PWA.** Ouvre le site, puis « Ajouter à l'écran d'accueil »
(Safari : bouton Partager ; Chrome : menu ⋮). L'application est alors mise en cache par
`sw.js` et se lance en plein écran, même en mode avion.

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
| `.github/workflows/pages.yml` | Déploiement automatique sur GitHub Pages |

## Auteur & licence

**Aurélien Moote - Moo - 2026**

Copyright (c) 2026 Aurélien Moote ("Moo"). Distribué sous **licence MIT** (voir
[`LICENSE`](LICENSE)) : libre de réutilisation, de modification et de redistribution,
à condition de conserver la mention de l'auteur — Aurélien Moote - Moo - 2026 —
et l'avis de licence. Voir aussi [`NOTICE`](NOTICE) et [`AUTHORS`](AUTHORS).
