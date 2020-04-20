---
title: Befehl „dotnet nuget remove source“
description: Mit dem Befehl „dotnet nuget remove source“ wird eine vorhandene Quelle aus Ihren NuGet-Konfigurationsdateien entfernt.
ms.date: 03/20/2020
ms.openlocfilehash: b259873e1885644b272136fa31414410bdfd9f27
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463493"
---
# <a name="dotnet-nuget-remove-source"></a>dotnet nuget remove source

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen

## <a name="name"></a>Name

`dotnet nuget remove source`: Entfernen einer NuGet-Quelle.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget remove source <NAME> [--configfile <FILE>]

dotnet nuget remove source -h|--help
```

## <a name="description"></a>Beschreibung

Mit dem Befehl `dotnet nuget remove source` wird eine vorhandene Quelle aus Ihren NuGet-Konfigurationsdateien entfernt.

## <a name="arguments"></a>Argumente

- **`NAME`**

  Name der Quelle.

## <a name="options"></a>Optionen

- **`--configfile`**

  Die NuGet-Konfigurationsdatei. Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet. Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Beispiele

- Entfernen einer Quelle mit dem Namen `mySource`:

  ```dotnetcli
  dotnet nuget remove source mySource
  ```

## <a name="see-also"></a>Siehe auch

- [Paketquellenabschnitte in NuGet.config-Dateien](/nuget/reference/nuget-config-file#package-source-sections)

- [Befehl „sources“ (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
