# BW Inventor — PWA complète

Version PWA mobile-first de BW Inventor, basée sur la structure de données V3 (`mg-v3a`).

## Utilisation
Servir le dossier via HTTPS (ou localhost) pour obtenir une vraie PWA installable. L'ouverture directe en `file://` permet de voir l'interface mais ne constitue pas un contexte PWA installable.

## Données
Les données restent dans `localStorage` sur l'appareil. Exporter/Restaurer utilise un fichier JSON.

## Fonctionnalités
Inventaire hebdomadaire, FC/USD, dettes clients, dettes à payer, dépenses, historique, rapports, PIN, bienvenue vocale, export/restauration, service worker et interface mobile.


## Version adaptative / sauvegarde dossier
L'interface est renforcée pour les petits téléphones, tablettes et grands écrans.
Le bouton « Choisir un dossier » utilise le sélecteur de dossier du navigateur lorsqu'il est disponible. Sur Android, Google Drive peut apparaître dans ce sélecteur selon la configuration de l'appareil. Une PWA ne peut pas imposer Drive comme emplacement système par défaut sans intégration OAuth/API Google Drive.
Le bouton « Sauvegarder maintenant » écrit `BW_Inventor_backup.json` dans le dossier choisi, sinon propose un téléchargement JSON classique.
