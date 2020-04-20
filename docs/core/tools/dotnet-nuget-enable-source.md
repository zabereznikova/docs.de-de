---
title: Befehl „dotnet nuget enable source“
description: Mit dem Befehl „dotnet nuget enable source“ wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktiviert.
ms.date: 03/20/2020
ms.openlocfilehash: 38fb5917361bd7952fef9c31ed897fb81f005155
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463561"
---
# <a name="dotnet-nuget-enable-source"></a>dotnet nuget enable source

**Dieser Artikel gilt für:** ✔️ .NET Core 3.1.200 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet nuget enable source`: Aktivieren einer NuGet-Quelle.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a>Beschreibung

Mit dem Befehl `dotnet nuget enable source` wird eine vorhandene Quelle in Ihren NuGet-Konfigurationsdateien aktiviert.

## <a name="arguments"></a>Argumente

- **`NAME`**

  Name der Quelle.

## <a name="options"></a>Optionen

- **`--configfile <FILE>`**

  Die NuGet-Konfigurationsdatei. Sofern angegeben, werden nur die Einstellungen aus dieser Datei verwendet. Falls nicht angegeben, wird die Hierarchie der Konfigurationsdateien aus dem aktuellen Verzeichnis verwendet. Weitere Informationen finden Sie unter [Gängige NuGet-Konfigurationen](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Beispiele

- Aktivieren einer Quelle mit dem Namen `mySource`:

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>Siehe auch

- [Paketquellenabschnitte in NuGet.config-Dateien](/nuget/reference/nuget-config-file#package-source-sections)

- [Befehl „sources“ (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
