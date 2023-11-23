---
layout: default
title: Transform
parent: Unity
---
# Transform
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Résumé
Le Transform est un **Component** obligatoire sur tout [**GameObject**](/docs/unity/gameobject).

On ne peut ni l'ajouter, ni le retirer.

Le Transform sert à identifier et modifier les coordonnées d'un [**GameObject**](/docs/unity/gameobject) dans la scène,  
il possède 3 variables importantes :
```cs
Vector3 position;
Quaternion rotation;
Vector3 scale;
```
