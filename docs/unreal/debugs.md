---
layout: default
title: Debugs
parent: Unreal
---
# Debugs
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

# Debugs logs & screen
On peut afficher des messages dans la console ou à l'écran, pour simplifier les choses, on va créer des macros et les placer dans un fichier "Utils" qu'on aura qu'à include où on en a besoin.

*Utils.h*
```cpp
//Message dans la console
#define DEBUG(Format, ...)\
UE_LOG(LogTemp, Display, TEXT(Format), __VA_ARGS__);

//Avertissement dans la console
#define DEBUG_WARNING(Format, ...)\
UE_LOG(LogTemp, Warning, TEXT(Format), __VA_ARGS__);

//Erreur dans la console
#define DEBUG_ERROR(Format, ...)\
UE_LOG(LogTemp, Error, TEXT(Format), __VA_ARGS__);

//Message à l'écran
#define DEBUG_SCREEN(Format, ...)\
GEngine->AddOnScreenDebugMessage(-1, 5.0f, FColor::Yellow, FString::Printf(TEXT(Format), __VA_ARGS__));
```
Grâce à ces commandes, on peut afficher des messages tout en passant simplement des valeurs de cette manière (sans oublier d'inclure Utils.h) :
```cpp
#include "Utils.h"

void ASomeActor::SomeMethod()
{
	DEBUG_WARNING("someFloat = %f", someFloat);
	DEBUG_SCREEN("someFloat = %f", someFloat);
}
```

# Debug In Editor
Pour faire des debugs sans forcément être en play, il faut indiquer au moteur que l'actor peut faire son tick, pour ça il faut override une méthode en retournant true, on préferera utilser un booléen :

*SomeActor.h*
```cpp
UPROPERTY(EditAnywhere)
bool debug = false;

virtual bool ShouldTickIfViewportsOnly() const override;
```
Et indiquer dans le constructeur de ne le faire qu'en editor :

*SomeActor.cpp*
```cpp
ASomeActor::ASomeActor()
{
	PrimaryActorTick.bCanEverTick = true;
#if WITH_EDITOR
	PrimaryActorTick.bStartWithTickEnabled = true;
#endif
}

bool ASomeActor::ShouldTickIfViewportsOnly() const
{
	return debug;
}
```
