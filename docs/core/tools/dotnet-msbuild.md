---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 02/14/2020
ms.openlocfilehash: 9739fe782e17db3955db087ca1781ad4280cd491
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "84803173"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen

## <a name="name"></a>name

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten Hinweis: Wenn mehrere vorhanden sind, muss möglicherweise eine Projektmappe oder eine Projektdatei angegeben werden.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet msbuild <MSBUILD_ARGUMENTS>

dotnet msbuild -h
```

## <a name="description"></a>Beschreibung

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf. Alle Optionen sind gleich. Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).

Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore`. Wenn Sie das Projekt nicht erstellen und ein bestimmtes Ziel ausführen möchten, verwenden Sie `dotnet build` oder `dotnet msbuild`, und geben Sie das Ziel an.

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
  dotnet msbuild -preprocess:<fileName>.xml
  ```
