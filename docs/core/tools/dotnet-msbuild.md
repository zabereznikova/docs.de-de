---
title: Befehl dotnet-msbuild | Microsoft-Dokumentation
description: "Der Befehl dotnet-msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile."
keywords: dotnet-msmsbuild, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: a000e49a8672affe5b3bb9bd8a5f7e8095ab0aa9
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-msbuild"></a>dotnet-msbuild

## <a name="name"></a>Name

`dotnet-msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

```
dotnet msbuild <msbuild_arguments>
dotnet msbuild [-h]
```

## <a name="description"></a>Beschreibung

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz 

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf. Alle Optionen sind gleich. Sie können sich mithilfe der [MSBuild-Befehlszeilenreferenz](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) mit den Optionen vertraut machen. 

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet msbuild`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet msbuild /p:Configuration=Release`

Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`
