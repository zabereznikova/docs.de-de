---
title: Befehl „dotnet nuget disable source“
description: Mit dem Befehl „dotnet nuget enable source“ wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien deaktiviert.
ms.date: 03/20/2020
ms.openlocfilehash: af37a6589cebaf0501ee5647ebadb83125d0f56e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537950"
---
# <a name="dotnet-nuget-disable-source"></a>dotnet nuget disable source

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet nuget disable source`: Deaktivieren einer NuGet-Quelle.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget disable source <NAME> [--configfile <FILE>]

dotnet nuget disable source -h|--help
```

## <a name="description"></a>Beschreibung

Mit dem Befehl `dotnet nuget disable source` wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien deaktiviert.

## <a name="arguments"></a>Argumente

- **`NAME`**

  Name der Quelle.

## <a name="options"></a>Optionen

- **`--configfile <FILE>`**

  Die NuGet-Konfigurationsdatei. Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet. Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Beispiele

- Deaktivieren einer Quelle mit dem Namen `mySource`:

  ```dotnetcli
  dotnet nuget disable source mySource
  ```

## <a name="see-also"></a>Siehe auch

- [Paketquellenabschnitte in NuGet.config-Dateien](/nuget/reference/nuget-config-file#package-source-sections)

- [Befehl „sources“ (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
