<p align="center">
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/header/grid.svg?title=ReqXport&subtitle=Capture+%26+exporte+les+requetes+API+en+HTML.&mode=dark&theme=zinc" /><img alt="reqxport" src="https://shieldcn.dev/header/grid.svg?title=ReqXport&subtitle=Capture+%26+exporte+les+requetes+API+en+HTML.&mode=light&theme=zinc" /></picture>
</p>

<p align="center">
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/badge/chrome-bookmarklet.svg?theme=blue&mode=dark" /><img alt="chrome bookmarklet" src="https://shieldcn.dev/badge/chrome-bookmarklet.svg?theme=blue&mode=light" /></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/badge/export-html.svg?theme=green&mode=dark" /><img alt="export html" src="https://shieldcn.dev/badge/export-html.svg?theme=green&mode=light" /></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/badge/fetch-xhr.svg?theme=red&mode=dark" /><img alt="fetch xhr" src="https://shieldcn.dev/badge/fetch-xhr.svg?theme=red&mode=light" /></picture>
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://shieldcn.dev/flag/fr.svg" /><img alt="made in france" src="https://shieldcn.dev/flag/fr.svg?mode=light" /></picture>
</p>

<div align="center">

**Un favori Chrome en un seul fichier. Un clic, un bouton noir apparaît, il compte les requêtes API, un clic dessus et tout est exporté en HTML.**

</div>

---

## ✨ Ça fait quoi ?

- Un petit **bouton noir arrondi** apparaît en bas à droite dès le clic sur le favori. Il affiche **0** au début.
- Chaque requête API (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`…) fait **augmenter le compteur** : `0` → `1` → `2`…
- **Un clic sur le bouton = export** : un fichier `.html` stylé est téléchargé, avec l'interface demandée :
  - en haut, centré : **reqxport**
  - une séparation
  - toutes les requêtes en dessous, en cartes arrondies : badge de méthode coloré (vert, bleu, orange, violet, rouge), URL, pastille de statut, durée, headers, body, réponse.
- L'export reprend le style Scolup (zinc, coins arrondis, mode sombre auto).

## 📁 Contenu du dossier

| Fichier | Rôle |
|---|---|
| `reqxport.js` | **Le bookmarklet complet, prêt à l'emploi.** Commence par `javascript:` : tout copier dans l'URL du favori. |
| `README.md` | Cette doc. |

C'est tout. Deux fichiers, rien d'autre.

## 🚀 Installation (30 secondes)

1. Copier **tout le contenu** de `reqxport.js` (ça commence par `javascript:`).
2. Dans Chrome : `⋮` → **Favoris** → **Ajouter un favori** (ou `Ctrl+D`, puis modifier).
   - Nom : `ReqXport`
   - URL : coller le contenu copié.
3. Afficher la barre de favoris si besoin : `Ctrl+Shift+B`.

## 🖱️ Utilisation

1. Va sur le site à analyser.
2. Clique sur le favori **ReqXport** → le bouton noir `0` apparaît en bas à droite.
3. Navigue / clique sur le site : le compteur augmente à chaque requête (`3`, `12`, …).
4. Clique sur le bouton → le fichier `reqxport-2026-…html` est téléchargé :

```
        [logo reqxport]
  ─────────────────────────────
  12 requetes • exporte le … • https://lesite.com/…
  #1 GET /api/users → 200 (headers, body, réponse…)
  #2 POST /api/login → 200 …
```

> Re-cliquer sur le favori pendant l'enregistrement relance aussi l'export (pratique si le bouton est masqué).

## 🔍 Ce qui est capturé (par requête)

- Méthode, URL complète, statut, durée (ms), heure.
- Headers requête / réponse, corps requête, corps réponse (tronqués à ~5000 caractères pour garder le favori léger).

## ⚠️ Notes

- Seules les requêtes émises **après** le clic sont capturées (on ne peut pas relire le passé réseau).
- `window.__REQXPORT__` expose `logs`, `export()` et `clear()` pour la console.
- Sur les réponses opaques / CORS strictes, le corps peut être illisible (`[illisible]`) : méthode, URL et statut restent capturés.
- 100 % local, aucune dépendance, rien n'est envoyé ailleurs.
