# Beach Tennis · Gestion de tournoi (iOS)

Application iPhone/iPad (iOS 16+) construite à partir de l'artefact « Beach tennis · Gestion de tournoi (v2) ».
Le moteur du tournoi (règles FFT, tirage, TMC, poules, programmation, classement BT25 à BT1000) est repris
à l'identique dans `BeachTennisTournoi/index.html`, embarqué dans une coque SwiftUI native et utilisable **hors ligne**.

## Ce qui est natif
- **Sauvegarde fiable** : chaque modification est copiée dans `Application Support/tournois.json` et réinjectée au lancement.
- **Partager** les résultats : feuille de partage iOS (Messages, WhatsApp, Mail…).
- **Copier** : presse-papiers iOS.
- **Mes tournois → Exporter un fichier / Ouvrir un fichier** : sauvegarde `.json` via Fichiers, AirDrop ou mail.
- Retour **haptique** sur les confirmations, liens externes (WhatsApp, Ten'Up) ouverts hors de l'app.
- Polices système iOS (aucun appel réseau), mode sombre, zones sûres (encoche, Dynamic Island).

## Installer sur ton iPhone
1. Installer **Xcode** (App Store, gratuit), puis l'ouvrir une fois pour finir l'installation.
2. Ouvrir `BeachTennisTournoi.xcodeproj`.
3. Cible *BeachTennisTournoi* → onglet **Signing & Capabilities** → *Team* : choisir ton Apple ID
   (*Add an Account…* si besoin). Si l'identifiant est refusé, remplace `fr.beachtennis.tournoi`
   par un identifiant unique, par exemple `fr.tonnom.beachtennis`.
4. Brancher l'iPhone (ou le choisir en Wi-Fi), activer le **Mode développeur** sur l'iPhone
   (Réglages → Confidentialité et sécurité), puis ⌘R.
5. Au premier lancement : Réglages → Général → VPN et gestion de l'appareil → faire confiance au développeur.

Avec un Apple ID gratuit, l'app doit être réinstallée tous les 7 jours (les données restent). Avec un compte
Apple Developer (99 €/an), elle reste valable un an et peut être diffusée via TestFlight ou l'App Store.

## Modifier l'app
L'interface et les règles sont dans `index.html` : toute nouvelle version de l'artefact peut y être recollée
(conserver la clé de stockage `bt-tournoi-v2` pour garder les tournois existants).
