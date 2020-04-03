---
title: Befehl „dotnet nuget list source“
description: Mit dem Befehl „dotnet nuget list source“ werden alle vorhandenen Quellen aus Ihren NuGet-Konfigurationsdateien aufgelistet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148495"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet nuget list source`: Auflisten aller konfigurierten NuGet-Quellen.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a>Beschreibung

Mit dem Befehl `dotnet nuget list source` werden alle vorhandenen Quellen aus Ihren NuGet-Konfigurationsdateien aufgelistet.

## <a name="options"></a>Optionen

- **`--configfile`**

  Die NuGet-Konfigurationsdatei. Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet. Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`--format`**

  Das Format der Ausgabe des Auflistungsbefehls: `Detailed` (Standardwert) und `Short`.

## <a name="examples"></a>Beispiele

- Auflisten konfigurierter Quellen aus dem aktuellen Verzeichnis:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>Siehe auch

- [Paketquellenabschnitte in NuGet.config-Dateien](/nuget/reference/nuget-config-file#package-source-sections)

- [Befehl „sources“ (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
