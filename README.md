# Revue de plans

Valider ou renvoyer des plans de fabrication d'un geste, façon swipe.

- Glisser à droite : plan validé.
- Glisser à gauche : plan à reprendre. On annote le plan avec quatre outils (repère, zone, flèche, main levée). Chaque annotation a son commentaire, une catégorie (cote, tolérance, matière…), une gravité (bloquant ou mineur) et des images jointes (capture d'écran, photo de la pièce). Sur ordinateur, une capture copiée se colle directement (Ctrl+V / ⌘V).
- À la fin : récapitulatif avec vignettes annotées et texte prêt à copier pour le bureau d'études.

Formats acceptés : PDF (une carte par page) et images. Tout reste dans le navigateur : aucun plan n'est envoyé sur un serveur. La revue en cours est gardée (IndexedDB), y compris une remarque en cours d'écriture, jusqu'à « Nouvelle revue ».

Raccourcis clavier : `←` à reprendre, `→` valider, `Espace` agrandir, `Retour arrière` annuler.

## Mise en ligne (GitHub Pages)

Settings → Pages → Source : « Deploy from a branch », branche `main`, dossier `/ (root)`.
L'appli est ensuite à l'adresse `https://<utilisateur>.github.io/<dépôt>/`.

## En local

```bash
python3 -m http.server 8000
```

puis ouvrir http://localhost:8000. Pas de build, pas de dépendance à installer.

## Contenu

- `index.html` : toute l'appli (HTML, CSS, JS).
- `vendor/pdfjs/` : pdf.js 3.11.174 (Mozilla, licence Apache 2.0) pour lire les PDF.
