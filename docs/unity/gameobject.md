---
layout: default
title: GameObject
parent: Unity
---
# GameObject
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Résumé
Sur Unity, un GameObject désigne tout objet se trouvant dans le scène.

Un GameObject peut posséder des scripts de type [**MonoBehaviour**](/docs/unity/monobehaviour).

Il possède par défaut un [**Transform**](/docs/unity/transform) qui ne peut être retiré  
et qui est directement accessible :
```cs
transform.position = new Vector3(2, 0, 0);
```