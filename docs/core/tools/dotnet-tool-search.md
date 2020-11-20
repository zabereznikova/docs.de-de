---
title: Befehl „dotnet tool search“
description: Der Befehl „dotnet tool search“ durchsucht die .NET-Tools, die auf NuGet.org veröffentlicht wurden.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634141"
---
# <a name="dotnet-tool-search"></a>dotnet tool search

**Dieser Artikel gilt für:** ✔️ .NET 5.0 SDK und höhere Versionen

## <a name="name"></a>Name

`dotnet tool search`: Der Befehl durchsucht alle [.NET-Tools](global-tools.md), die auf NuGet veröffentlicht wurden.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a>Beschreibung

Der Befehl `dotnet tool search` bietet Ihnen die Möglichkeit, NuGet nach Tools zu durchsuchen, die als globale, tool-path- oder lokale .NET-Tools verwendet werden können. Der Befehl durchsucht die Toolnamen und Metadaten, z. B. Titel, Beschreibungen und Tags.

Der Befehl verwendet die [NuGet-Such-API](/nuget/api/search-query-service-resource#search-for-packages). Er filtert nach `packageType=dotnettool`, um nur .NET-Toolpakete auszuwählen.

## <a name="options"></a>Optionen

- **`--detail`**

  Zeigt detaillierte Ergebnisse der Abfrage an

- **`--prerelease`**

  Enthält Vorabversionen von Paketen

- **`--skip <NUMBER>`**

  Gibt die Anzahl der zu überspringenden Abfrageergebnisse an Wird für die Paginierung verwendet

- **`--take <NUMBER>`**

  Gibt die Anzahl der anzuzeigenden Abfrageergebnisse an Wird für die Paginierung verwendet

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="examples"></a>Beispiele

- Suchen Sie auf NuGet.org nach .NET-Tools, deren Paketname oder Beschreibung „format“ enthält:

  ```dotnetcli
  dotnet tool search format
  ```

  Die Ausgabe sieht wie folgt aus:

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- Suchen Sie NuGet.org nach .NET-Tools, deren Paketname oder Metadaten „format“ enthält, zeigen Sie nur das erste Ergebnis an, und rufen Sie eine detaillierte Ansicht auf.

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  Die Ausgabe sieht wie folgt aus:

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a>Siehe auch

- [.NET-Tools](global-tools.md)
- [Tutorial: Installieren und Verwenden eines globalen .NET-Tools mithilfe der .NET-CLI](global-tools-how-to-use.md)
- [Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI](local-tools-how-to-use.md)
