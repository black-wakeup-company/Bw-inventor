# BW Inventor — PWA V5.2

Version PWA mobile-first de BW Inventor — Black Wakeup Company.

## Structure

```text
/
├── index.html
├── manifest.json
├── sw.js
└── icons/
    └── logo.jpg
```

## Lancer la PWA

La PWA doit être servie depuis **HTTPS** ou `localhost`. Une ouverture directe en `file://` permet de lire la page mais ne donne pas un vrai contexte PWA.

Sur GitHub Pages, l'adresse du dépôt peut être utilisée directement depuis le navigateur puis installée via le bouton d'installation ou le menu du navigateur.

## Données

Les données de l'application restent dans `localStorage` sur l'appareil. Le bouton **Exporter JSON** crée une sauvegarde complète et **Restaurer JSON** permet de la réimporter.

Le réglage du PIN est inclus dans le JSON. Le délai de verrouillage est également conservé dans les paramètres.

## Sauvegarde dans un dossier

Quand le navigateur supporte `showDirectoryPicker`, **Choisir un dossier** permet de sélectionner un emplacement. Le handle du dossier est conservé dans IndexedDB afin que l'application puisse retrouver ce choix après redémarrage, sous réserve que le navigateur conserve l'autorisation.

Sur Android, le sélecteur peut afficher Google Drive si le fournisseur de fichiers est disponible. Une PWA ne peut pas imposer Google Drive comme emplacement système par défaut sans intégration Google Drive/OAuth dédiée.

Si le navigateur ne prend pas en charge le sélecteur de dossier, **Sauvegarder maintenant** télécharge automatiquement le JSON.

## PIN

Le PIN peut être demandé :

- immédiatement à chaque ouverture ;
- après 1 minute ;
- après 5 minutes ;
- après 15 minutes ;
- après 30 minutes.

Le dernier déverrouillage est conservé localement sur l'appareil afin de déterminer quand verrouiller à nouveau.

## PWA / hors connexion

Le Service Worker met en cache l'interface et le logo. Les navigations utilisent le réseau en priorité puis le cache en cas de coupure, ce qui évite de rester bloqué sur une ancienne version après une mise à jour publiée.
