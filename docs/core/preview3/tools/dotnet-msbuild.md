---
title: Befehl dotnet-msbuild | Microsoft-Dokumentation
description: "Der Befehl dotnet-msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile."
keywords: dotnet-msmsbuild, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 06d4210e5dff97d3e96efff8ae8e84efc27fb7d2
ms.lasthandoff: 01/21/2017

---

#<a name="dotnet-msbuild"></a>dotnet-msbuild

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Name 
dotnet-msbuild: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

`dotnet msbuild <msbuild_arguments>`

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

