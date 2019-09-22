---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 12/03/2018
ms.openlocfilehash: b83f1272cdd4c5fcdb6b1e34aef7692e9acc01cd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117699"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>NAME

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Zusammenfassung

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>BESCHREIBUNG

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf. Alle Optionen sind gleich. Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).

Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore -target:Build`. `dotnet build` wird häufiger zum Erstellen von Projekten verwendet, aber mit `dotnet msbuild` haben Sie mehr Kontrolle. Wenn Sie z.B. ein bestimmtes Ausführungsziel haben (ohne Ausführung des Buildziels), verwenden Sie wahrscheinlich `dotnet msbuild`.

## <a name="examples"></a>Beispiele

* Erstellt ein Projekt und seine Abhängigkeiten:

  ```dotnetcli
  dotnet msbuild
  ```

* Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

  ```dotnetcli
  dotnet msbuild -p:Configuration=Release
  ```

* Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:

  ```dotnetcli
  dotnet msbuild -pp
  ```
