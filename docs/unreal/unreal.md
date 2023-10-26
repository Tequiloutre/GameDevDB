---
layout: default
title: Unreal
nav_order: 4
has_children: true
permalink: /docs/unreal
---
# Unreal
Unreal est un moteur de jeu 2D et 3D.

## Quick tips
### Templates de classes
Lorsque vous créez une nouvelle classe, Unreal vous crée un fichier .h et .cpp pré-remplis avec certaines choses nécessaires au bon fonctionnement du moteur.

Mais il ajoute également pleins d'espaces vides et de commentaires inutiles.

Vous pouvez modifier ces templates qui se trouvent dans le dossier suivant :

`../UE_*.*/Engine/Content/Editor/Templates`

Vous pouvez alors ouvrir les fichiers `.template` sur votre IDE et les modifier

{: .warning }
Evitez de supprimer les macros entourées de % au risque d'avoir des choses manquantes et que votre code ne compile plus

### Ouvrir l'Editeur d'Asset dans un onglet
Par défaut, Unreal ouvre l'Editeur d'Asset (pour les BP par exemple) dans une nouvelle fenêtre, si comme moi vous trouvez ça ennuyant, voici comment l'ouvrir dans un nouvel onglet:

`Editor Preferences > Appearance > User Interface > Asset Editor Open Location > Main Window`

[![openInTab.png](/GameDevDB/images/unreal/openInTab.png)](/GameDevDB/images/unreal/openInTab.png)
