---
layout: default
title: La mémoire en C++
parent: C++
---
# La mémoire en C++
{: .no_toc }
En C++, le développeur doit lui même faire attention à la gestion de mémoire, à l'optimisation de celle-ci et aux pointeurs nuls.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## Comment fonctionne la mémoire ?
Lorsque l'on déclare une variable, on demande au processeur d'allouer une partie de sa mémoire pour y stocker une variable.

La quantité de mémoire nécessaire pour stocker cette variable dépend de son type.

Lorsque l'on passe une variable comme argument dans une fonction, le processeur effectue en fait une copie de cette variable et réalloue donc de la mémoire, d'où l'importance de l'[Optimisation](#optimisation).

## Optimisation
### Passage par référence
Une classe peut rapidement devenir assez lourde et on va souvent préférer utilisé des passages par référence comme arguments de fonctions.

#### Exemple
Une méthode prenant comme argument un entier :
```cpp
void SomeMethod(int _value) { }
```
Un entier a une taille de 2 ou 4 octets selon l'architecture du système (4 en général sur des pc récents).

Un pointeur, peu importe de quel type, a une taille de 8 octets.

On ne va donc pas utiliser de pointeur pour les entiers (à moins qu'on en ai précisément besoin).

Imaginons maintenant une méthode prenant comme argument une classe que nous avons créé :
```cpp
void AnotherMethod(SomeClass _class) { }
```

On peut connaître la taille de cette classe de cette manière :
```cpp
cout << sizeof(SomeClass) << endl;
```
```
4
```

Si la taille de cette classe est supérieure à 8 octets, il est plus optimisé de passer l'objet par référence plutôt qu'une copie complète *(on ajoute const pour que la valeur du pointeur ne puisse pas être modifiée)*
```cpp
void AnotherMethod(const SomeClass& _class) { }
```

#### Tableau de taille des types

|Type|Taille (octets)|Réference ?|
|:-|:-|:-|
|*|8||
|bool|1|non|
|int|4|non|
|float|4|non|
|string|40|oui|
