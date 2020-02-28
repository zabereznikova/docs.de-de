---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 02/14/2020
ms.openlocfilehash: 28a32a460d644d3e22f16b5dd9416222ae466e2e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503680"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Beschreibung

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf. Alle Optionen sind gleich. Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).

Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore -target:Build`. Der [dotnet build](dotnet-build.md)-Befehl wird häufiger zum Erstellen von Projekten verwendet, aber da dieser immer das Buildziel ausführt, können Sie `dotnet msbuild` verwenden, wenn Sie das Projekt nicht erstellen möchten. Wenn Sie z. B. ein bestimmtes Ziel haben, das Sie ausführen möchten, ohne das Projekt zu erstellen, verwenden Sie `dotnet msbuild`, und geben Sie das Ziel an.

## <a name="examples"></a>Beispiele

- Erstellt ein Projekt und seine Abhängigkeiten:

  ```dotnetcli
  dotnet msbuild
  ```

- Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
