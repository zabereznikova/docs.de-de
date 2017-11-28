---
title: "dotnet-msbuild-Befehl – .NET Core-CLI"
description: "Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 96e4eac528abad2b336a979a98c9be2bee5d17ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Beschreibung

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf. Alle Optionen sind gleich. Informationen zu den verfügbaren Optionen finden Sie unter [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference). 

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet msbuild`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet msbuild /p:Configuration=Release`

Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:

`dotnet msbuild /pp`
