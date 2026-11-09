# Revue de plans

Valider ou renvoyer des plans de fabrication d'un geste, façon swipe.

- Glisser à droite : plan validé.
- Glisser à gauche : plan à reprendre. On annote le plan avec quatre outils (repère, zone, flèche, main levée). Chaque annotation a son commentaire, une catégorie (cote, tolérance, matière…), une gravité (bloquant ou mineur) et des images jointes (capture d'écran, photo de la pièce). Sur ordinateur, une capture copiée se colle directement (Ctrl+V / ⌘V).
- Zoom dans l'éditeur (jusqu'à 400 %) pour annoter une petite cote.
- Contrôles : une check-list à cocher sous chaque plan (cartouche, échelle, tolérances…), modifiable.
- Dans le récap, chaque plan se rouvre pour modifier ses remarques avant l'export (« Modifier les remarques », ou « Ajouter des remarques » sur un plan validé). Sans remarque, le plan repasse en validé.
- À la fin : récapitulatif avec vignettes annotées, texte prêt à copier, export Markdown (.md, un tableau des remarques par plan) et export PDF (une page par plan, images jointes en annexe). Sur iPhone, les fichiers s'ouvrent dans la feuille de partage (Mail, WhatsApp, Fichiers…).
- Export pour l'IA (.zip) : `PROMPT.md` (consigne prête à donner à n'importe quel agent), `revue.json` (données structurées), plans annotés, zoom sur chaque remarque et images jointes. Chaque remarque a un identifiant stable (`REF-R1`), sa gravité, sa catégorie, sa « correction attendue » et sa position en mm sur la feuille (lue dans le PDF).

Formats acceptés : PDF (une carte par page), DXF et images. Un DXF est dessiné en noir sur blanc depuis l'espace objet (géométrie, blocs, textes, cotations ; calques masqués ignorés), et l'export pour l'IA donne alors les positions dans le repère du dessin, avec ses unités. Tout reste dans le navigateur : aucun plan n'est envoyé sur un serveur. La revue en cours est gardée (IndexedDB), y compris une remarque en cours d'écriture, jusqu'à « Nouvelle revue ».

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
- `vendor/jspdf/` : jsPDF 2.5.1 (licence MIT) pour produire le rapport PDF.
- `vendor/jszip/` : JSZip 3.10.1 (licence MIT) pour l'export .zip.
- `vendor/dxf/` : dxf 5.3.1 (licence MIT) pour lire les DXF.
