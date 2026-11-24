# Beach Tennis · Gestion de tournoi

Application web pour organiser un tournoi de beach tennis : inscriptions, tirage, poules et tableaux, programmation sur les terrains, saisie des scores, classements et communication aux joueurs. Une seule page HTML, sans serveur : elle fonctionne dans un navigateur, hors ligne, et se range sur l'écran d'accueil d'un téléphone.

**Version actuelle : 4.4** (24/11/2026). La version s'affiche en bas de chaque page.

## Fichiers

- `index.html` : la page servie (par exemple par GitHub Pages).
- `beach-tennis-v4.html` : même application, version publiée de l'artefact.

Les données restent dans le navigateur (clé `bt-tournoi-v2`). Aucune donnée n'est envoyée sur un serveur.

## Utiliser l'application

1. Ouvrir la page dans le navigateur du téléphone, de la tablette ou de l'ordinateur.
2. Sur iPhone : Partager → « Sur l'écran d'accueil ». Sur Android : menu → « Ajouter à l'écran d'accueil ».
3. Créer un tournoi dans « Mes tournois » (2 tournois actifs au maximum, les autres s'archivent en lecture seule).

## Fonctionnalités

### Tournoi FFT (BT25 à BT1000)
- **Catégories** : BT25, BT100, BT250, BT500, BT1000, en double messieurs, dames ou mixte. Le cahier des charges de la catégorie est vérifié (terrains, cut, juge-arbitre, durée, balles, etc.) et signale les écarts.
- **Équipes** : saisie à la main avec licences et classements, import d'une liste (texte), import de l'export d'inscriptions de la FFT (fichier `.xls`, `.xlsx` ou `.csv`). Seuls noms, licences, clubs et classements sont repris : courriels, téléphones et dates de naissance du fichier sont ignorés.
- **Poids et têtes de série** : poids d'une équipe = somme des classements des deux joueurs, têtes de série selon la taille du tableau, égalités ordonnées à la main ou au sort.
- **Formats proposés** : poule unique, poules + phase finale, tournoi multi-chances (TMC), avec estimation du nombre de matchs, de la durée et du minimum de matchs par équipe.
- **Formats de jeu** : découverte, 3, 4, 5, 6, avec les contraintes de la catégorie. En « Poules + phase finale », trois réglages distincts : format des poules, du tableau principal et des matchs de classement. Le mode Automatique reprend le format des poules, la finale ou le tableau principal restant en format 4 là où la catégorie l'impose. Un choix différent est gardé et signalé dans le cahier des charges.
- **Tirage extérieur** : saisie d'un tirage réalisé hors de l'application, pour les poules (nombre de poules, poule de chaque équipe, tableaux de phase finale) ou pour le tableau final direct (têtes de série, places du premier tour, exempts). Les écarts au règlement sont signalés en direct sans jamais bloquer : taille des poules, une tête de série par poule, TS1 en bas et TS2 en haut du tableau, exempts d'abord aux têtes de série, équipes d'une même poule qui se rencontrent dès le premier tour, poids des têtes de série. Les alertes restent visibles après la génération, et le tirage est figé dès qu'un résultat est saisi.
- **Programmation** : planning sur 1 à 8 terrains, avec durées par format et repos minimum entre deux matchs. Le planning se recalcule à chaque changement de format ou de durée.
- **Ordre des matchs modifiable** : flèches ▲ ▼ sur les matchs à jouer. Horaires et terrains sont recalculés, les matchs joués ne bougent pas. Les repos non respectés, dépendances et chevauchements sont signalés par « À vérifier », sans rien bloquer. « Revenir à l'ordre automatique » annule la modification.
- **Saisie des scores** : set par set, avec des scores rapides à toucher, super jeu décisif affiché seulement à un set partout, forfait (WO). Un score reste modifiable même si des matchs suivants sont joués : seuls les matchs dont les équipes changent sont à rejouer, après confirmation.
- **Poules et tableaux** : classements de poules en direct, tableaux avec consolantes et classement complet, points de classement FFT indicatifs.

### Américano loisir
- Format loisir pour des joueurs individuels : les partenaires changent à chaque match et les points gagnés se cumulent par joueur.
- Réglages : 4 à 40 joueurs, terrains, nombre de tours, total de points par match (16, 20, 24, 32 ou libre), classement par total ou par moyenne, durée et heure de départ.
- Tirage des tours sans partenaire répété quand l'effectif s'y prête, repos à tour de rôle quand il y a plus de joueurs que de places.
- Classement individuel (points, matchs, victoires, différence, moyenne), partage des résultats, affichage public, PDF.

### Communication et diffusion
- **WhatsApp** : mobiles des joueurs, préparation du groupe, invitations, convocations individuelles, messages prêts à envoyer (convocation, programme, prochains matchs, résultats).
- **Partage** : texte de classement et de résultats à envoyer par Messages ou WhatsApp.
- **Affichage public** : plein écran pour l'écran du club, avec rotation automatique du programme, des tableaux, des poules et du classement. L'écran reste allumé quand le navigateur l'autorise.
- **Export PDF** : tableaux, poules, programme et classement aux couleurs du club.
- **Club** : nom, logo et couleurs appliqués à l'application, aux PDF et à l'affichage public.

### Données
- Plusieurs tournois, archivage en lecture seule.
- Sauvegarde et restauration par fichier ou par copie de texte.
- Mode sombre et affichage adapté au téléphone.

## Limites de la version navigateur

Certaines fonctions sont grisées dans un navigateur et réservées à une coque native (application iOS) :
- rappels de match (notifications), car une page web ne peut pas notifier quand elle est fermée ;
- lecture des PDF de classement FFT et recherche du classement par licence ;
- export PDF et téléchargement de sauvegarde quand l'impression ou le téléchargement sont bloqués (par exemple dans un artefact).

Safari peut effacer les données d'un site après environ une semaine sans usage : exporter régulièrement une sauvegarde.

## Règles appliquées

Règlement sportif et guide de la compétition beach tennis de la FFT (art. 210 à 214 et 225 à 232, règles du jeu). Application indépendante, non affiliée à la Fédération Française de Tennis et non approuvée par elle : vérifier les règles avant toute homologation.

## Modifier l'application

Toute l'interface et les règles sont dans `index.html`. Conserver la clé de stockage `bt-tournoi-v2` pour garder les tournois existants, et mettre à jour `APP_VER` et `APP_DATE` à chaque évolution.
