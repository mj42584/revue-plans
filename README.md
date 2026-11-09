# 📐 Revue de plans

**Vos plans de fabrication, validés d'un swipe.**
À droite, c'est bon. À gauche, on annote et on renvoie. Rien à installer, rien qui sort du navigateur.

> 👉 Glissez vos PDF, swipez, exportez. Une revue complète en quelques minutes, sur ordinateur comme sur iPhone.

---

## Pourquoi c'est pratique

- **🔒 Confidentiel par construction** : vos plans ne quittent jamais votre appareil. Aucun serveur, aucun compte, aucun envoi.
- **⚡ Zéro friction** : un seul fichier HTML. Pas de build, pas d'installation, pas de compte.
- **💾 Rien ne se perd** : la revue en cours est sauvegardée automatiquement, jusqu'à la remarque en cours d'écriture.
- **🤖 Prêt pour l'IA** : un export .zip qu'un agent sait lire et corriger directement.

## Comment ça marche

### 1. Swipez
| Geste | Clavier | Résultat |
|---|---|---|
| ➡️ Glisser à droite | `→` | Plan validé |
| ⬅️ Glisser à gauche | `←` | Plan à reprendre, on passe à l'annotation |
| | `Espace` | Agrandir le plan |
| | `Retour arrière` | Annuler |

Formats acceptés : **PDF** (une carte par page) et **images**.

### 2. Annotez avec précision
- **Quatre outils** : repère, zone, flèche, main levée.
- **Zoom jusqu'à 400 %** pour pointer la plus petite cote.
- Chaque remarque a son **commentaire**, sa **catégorie** (cote, tolérance, matière…), sa **gravité** (bloquant ou mineur) et ses **images jointes** (capture d'écran, photo de la pièce).
- Une capture copiée se **colle directement** (Ctrl+V / ⌘V).
- Une **check-list de contrôle** sous chaque plan (cartouche, échelle, tolérances…), modifiable à volonté.

### 3. Relisez, puis exportez
Le récapitulatif montre chaque plan avec ses vignettes annotées. Un plan se rouvre en un clic pour ajuster ses remarques (sans remarque, il repasse en validé).

Puis, au choix :

| Export | Pour qui |
|---|---|
| 📋 **Texte** prêt à copier | Un message rapide, un ticket |
| 📝 **Markdown** (.md) | Un tableau des remarques par plan |
| 📄 **PDF** | Le rapport à envoyer : une page par plan, images jointes en annexe |
| 🤖 **Pack IA** (.zip) | Un agent qui corrige les plans tout seul |

Sur iPhone, les fichiers s'ouvrent dans la feuille de partage (Mail, WhatsApp, Fichiers…).

#### Le pack IA en détail
- `PROMPT.md` : la consigne prête à donner à n'importe quel agent.
- `revue.json` : toutes les données structurées.
- Les plans annotés, un zoom sur chaque remarque et les images jointes.
- Chaque remarque porte un identifiant stable (`REF-R1`), sa gravité, sa catégorie, sa « correction attendue » et **sa position en mm sur la feuille**, lue dans le PDF.

---

## 🚀 Mise en ligne en 30 secondes (GitHub Pages)

Settings → Pages → Source : « Deploy from a branch », branche `main`, dossier `/ (root)`.
L'appli est ensuite en ligne à `https://<utilisateur>.github.io/<dépôt>/`.

## 💻 En local

```bash
python3 -m http.server 8000
```

Puis ouvrir http://localhost:8000. C'est tout.

## Sous le capot

- `index.html` : toute l'appli (HTML, CSS, JS), sans framework.
- `vendor/pdfjs/` : pdf.js 3.11.174 (Mozilla, licence Apache 2.0) pour lire les PDF.
- `vendor/jspdf/` : jsPDF 2.5.1 (licence MIT) pour produire le rapport PDF.
- `vendor/jszip/` : JSZip 3.10.1 (licence MIT) pour l'export .zip.
