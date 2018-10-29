---
title: dotnet-msbuild-Befehl – .NET Core-CLI
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 76165590478b0e76d19d546c87e012da4716b6db
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583709"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Beschreibung 

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient auf. Alle Optionen sind gleich. Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).

## <a name="examples"></a>Beispiele

Erstellt ein Projekt und seine Abhängigkeiten:

`dotnet msbuild`

Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

`dotnet msbuild -p:Configuration=Release`

Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

`dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64`

Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:

`dotnet msbuild -pp`
