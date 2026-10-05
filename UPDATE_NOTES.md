# BW Inventor V6.0 — Mise à jour sécurisée

## Important pour les données
- Clé de stockage principale conservée : `mg-v3a`.
- Aucun `localStorage.removeItem("mg-v3a")` ajouté par la mise à jour.
- Une copie pré-mise-à-jour est créée au premier lancement sous `bw-inventor-preupdate-v6` si des données existent.
- L'export JSON existant reste disponible.

## Changements
- Interface modernisée avec Bootstrap 5.3.6 local/offline.
- Palette bleue : suppression de l'accent jaune/doré.
- Nouvelle créance : libellé obligatoire si un montant est saisi.
- Augmentation : libellé obligatoire.
- Paiement/remboursement : aucun libellé demandé.
- Historique : affiche le libellé et le reste après l'opération quand le rattachement au client est disponible.
- Impression historique : colonne reste ajoutée.
- Service Worker versionné pour forcer la nouvelle interface sans supprimer le localStorage.

## Mise à jour GitHub
1. Fais d'abord `Exporter JSON` depuis l'ancienne version si elle contient des données importantes.
2. Remplace les fichiers du dépôt par ceux de ce ZIP.
3. Ne change pas le domaine/origine de l'application si tu veux conserver le `localStorage`.
4. Ne supprime pas les données du navigateur/site.
5. Après déploiement, recharge l'application. Le nouveau Service Worker prendra la nouvelle interface.

## Note
GitHub ne stocke pas le `localStorage` de l'utilisateur : les données restent dans le navigateur sur le même domaine. Le ZIP protège la structure de stockage, mais une sauvegarde JSON externe reste recommandée avant toute grosse mise à jour.

## V6.1 — sans Bootstrap
- Bootstrap CSS externe a été retiré afin d'éviter toute interférence avec les boutons et la navigation.
- Les styles utilisés par BW Inventor restent dans `index.html`.
- La clé de données `mg-v3a` reste inchangée.
- Le Service Worker utilise un nouveau cache `bw-inventor-v6.1-no-bootstrap` pour forcer la nouvelle version sans toucher au `localStorage`.
- Aucun code de navigation (`nav()`) n'a été remplacé.
