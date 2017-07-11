---
title: "Befehl „dotnet-msbuild“ – .NET Core-CLI | Microsoft-Dokumentation"
description: "Der Befehl dotnet-msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile."
keywords: dotnet-msmsbuild, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: ffdc40ba-ef33-463e-aa35-b0af1fe615a2
ms.translationtype: Human Translation
ms.sourcegitcommit: df4b2ddd322e4bd2ebaf444439107e88a983f988
ms.openlocfilehash: 2267ef0b5785959456ea443405b6708a423d00ba
ms.contentlocale: de-de
ms.lasthandoff: 05/30/2017

---

<a id="dotnet-msbuild" class="xliff"></a>

# dotnet-msbuild

<a id="name" class="xliff"></a>

## Name

`dotnet-msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

<a id="synopsis" class="xliff"></a>

## Übersicht

`dotnet msbuild <msbuild_arguments> [-h]`

<a id="description" class="xliff"></a>

## Beschreibung

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf. Alle Optionen sind gleich. Informationen zu den verfügbaren Optionen finden Sie unter [MSBuild-Befehlszeilenreferenz](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

<a id="examples" class="xliff"></a>

## Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet msbuild`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet msbuild /p:Configuration=Release`

Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:

`dotnet msbuild /pp`
