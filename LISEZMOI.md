# Bâtir Sûr — installer l'application

Ce dossier est une application web installable (PWA). Une fois installée, elle s'ouvre comme une vraie application, avec son icône, **et fonctionne sans internet**.

## Contenu

| Fichier | Rôle |
| --- | --- |
| `index.html` | L'application complète |
| `manifest.webmanifest` | Nom, icône et couleurs de l'application installée |
| `sw.js` | Fait marcher l'application hors ligne |
| `icon-*.png`, `apple-touch-icon-180.png` | Icônes |

## 1. Mettre en ligne sur GitHub Pages (gratuit)

1. Sur github.com, créez un dépôt public nommé `batir-sur`.
2. **Add file → Upload files**, glissez **tous les fichiers de ce dossier** (pas le dossier lui-même), puis **Commit changes**.
3. **Settings → Pages** : Source = *Deploy from a branch*, Branch = `main`, dossier `/ (root)`, **Save**.
4. Après 1 à 2 minutes, l'application est en ligne à l'adresse :
   `https://<votre-nom-github>.github.io/batir-sur/`

Avec le terminal, c'est la même chose :

```bash
cd batir-sur-pwa
git init && git add . && git commit -m "Bâtir Sûr"
git branch -M main
git remote add origin https://github.com/<votre-nom-github>/batir-sur.git
git push -u origin main
```

## 2. Installer

- **Android (Chrome)** : ouvrez l'adresse → bouton **📲 Installer l'application** en haut, ou menu ⋮ → **Installer l'application**.
- **iPhone (Safari)** : ouvrez l'adresse → bouton Partager → **Sur l'écran d'accueil**.
- **PC (Chrome ou Edge)** : icône d'installation à droite de la barre d'adresse.

Ouvrez-la une fois avec internet : ensuite elle marche hors ligne. Ouvrez une fois l'export Excel avec internet pour que le module Excel soit aussi gardé hors ligne.

## 3. Fichier APK pour Android (optionnel)

1. Allez sur **pwabuilder.com**, collez l'adresse GitHub Pages, cliquez **Start**.
2. **Package for stores → Android → Generate**.
3. Vous obtenez un `.apk` à installer directement, et un `.aab` pour le Play Store.

## 4. Mettre à jour

Remplacez `index.html` sur GitHub, et changez `batir-sur-v1` en `batir-sur-v2` dans `sw.js` pour forcer la mise à jour sur les téléphones.

## Vos données

- Dans l'application installée, tout (calculs, devis, journal, photos) est enregistré **sur l'appareil**. Chaque téléphone ou PC a ses propres données.
- Pour passer d'un appareil à l'autre, ou depuis la version Claude : **📂 Importer / Exporter** → Excel ou Markdown, puis importez le fichier sur l'autre appareil. Les photos ne sont pas incluses dans ces fichiers.
- Si vous désinstallez l'application ou videz les données du navigateur, tout est effacé : exportez régulièrement.
