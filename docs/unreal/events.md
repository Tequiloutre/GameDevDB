---
layout: default
title: Events
parent: Unreal
---

# Events
## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

## En gros
Souvent, il va être trop couteux de vérifier la valeur d'une variable en tick dans l'attente que celle-ci change.
Par exemple, avec un component de vision, on ne va demander en tick au component si il a vu quelque-chose, on va plutôt utiliser un évènement.

## Declaration
Une évènement est constitué de 3 choses :
- Un type
- Un nom
- Des paramètres (facultatif)

On doit tout d'abord déclarer un type de variable pour que le moteur sache à quoi s'attendre.
Il existe de nombreuses macros pour déclarer un évènement selon le nombre de paramètres que l'on veut récupérer :
```cpp
DECLARE_DYNAMIC_MULTICAST_DELEGATE(Name);
DECLARE_DYNAMIC_MULTICAST_DELEGATE_OneParam(Name, Param1Type, Param1Name);
DECLARE_DYNAMIC_MULTICAST_DELEGATE_TwoParams(Name, Param1Type, Param1Name, Param2Type, etc...);
// attention au 's' de Params
etc...
```

*SomeClass.h*
```cpp
DECLARE_DYNAMIC_MULTICAST_DELEGATE_OneParam(FIntEvent, int, _value);
```
``
Cette macro à ralonge sert à déclarer le type d'évènement
``

