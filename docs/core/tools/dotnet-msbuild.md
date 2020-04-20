---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 02/14/2020
ms.openlocfilehash: 88e85868e2d7de564b2e4c90ce6e78bde4cb350e
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463629"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

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
