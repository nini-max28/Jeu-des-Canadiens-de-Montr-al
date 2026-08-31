# Qui est-ce du Tricolore

Jeu de type « Guess Who » sur les joueurs actuels et les légendes du Canadien de Montréal.

## Mise en ligne sur GitHub

1. Crée un dépôt public sur GitHub, par exemple `canadiens-guess-who`.
2. Mets-y ces trois fichiers : `canadiens-guess-who.html`, `content.json`, `README.md`.
3. Dans les paramètres du dépôt → **Pages** → choisis la branche `main` et le dossier `/root`.
   Le jeu sera en ligne à une adresse du type :
   `https://TONPSEUDO.github.io/canadiens-guess-who/canadiens-guess-who.html`
4. Note l'URL « raw » de `content.json` :
   `https://raw.githubusercontent.com/TONPSEUDO/canadiens-guess-who/main/content.json`
5. Ouvre `canadiens-guess-who.html`, cherche la ligne :
   ```js
   const CONTENT_URL = "";
   ```
   et colle-y l'URL raw de l'étape 4. Envoie (commit) le changement.

À partir de là, tu peux ajouter des joueurs ou des questions **en éditant seulement `content.json`** dans GitHub — pas besoin de toucher au reste du code, ni de republier une app.

## Format de content.json

```json
{
  "players": [
    {
      "id": 111,
      "name": "Guy Lapointe",
      "num": 5,
      "pos": "D",
      "posLabel": "Défenseur",
      "country": "Canada",
      "continent": "Amérique du Nord",
      "captain": null,
      "quebec": true,
      "tall": false,
      "shootsLeft": false,
      "veteran": true,
      "firstRound": false,
      "active": false,
      "numberRetired": false,
      "hallOfFame": true,
      "stanleyCup": true,
      "before1980": true,
      "era": "Légende"
    }
  ],
  "questions": [
    { "text": "A-t-il déjà porté le C ou le A sur son chandail?", "field": "captain" }
  ]
}
```

Notes :
- `id` doit être unique et différent de ceux déjà utilisés dans le jeu (1–20 pour l'effectif actuel, 101–110 pour les légendes déjà incluses). Utilise par exemple 200, 201, 202...
- Pour une question, `field` doit correspondre à un champ booléen existant sur les joueurs (`quebec`, `tall`, `shootsLeft`, `veteran`, `firstRound`, `active`, `numberRetired`, `hallOfFame`, `stanleyCup`, `before1980`, ou tout nouveau champ que tu ajoutes toi-même à des joueurs).
- Le jeu pige 12 questions au hasard dans l'ensemble (locales + celles ajoutées via `content.json`) à chaque nouvelle partie.
- Si `content.json` est vide ou inaccessible (pas de connexion), le jeu fonctionne quand même avec les 30 joueurs et 23 questions déjà intégrés.
