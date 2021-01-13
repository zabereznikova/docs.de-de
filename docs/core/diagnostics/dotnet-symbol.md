---
title: Diagnosetool „dotnet-symbol“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-symbol“ installieren und zum Herunterladen von Dateien verwenden, die für das Debuggen von .NET-Speicherabbildern und Minidumps erforderlich sind.
ms.date: 11/17/2020
ms.openlocfilehash: 69c05544e886d9d41113c8a2383f760b85d01124
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "97764993"
---
# <a name="symbol-downloader-dotnet-symbol"></a>Symboldownloadprogramm (dotnet-symbol)

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="install"></a>Installieren

Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-symbol) `dotnet-symbol` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-symbol
```

## <a name="synopsis"></a>Übersicht

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a>Beschreibung

Das globale Tool `dotnet-symbol` lädt Dateien (Symbole, DAC, Module usw.) herunter, die zum Debuggen von Kernspeicherabbildern und Minidumps benötigt werden. Dies kann nützlich sein, wenn Sie auf einem anderen Computer erfasste Speicherabbilder debuggen. `dotnet-symbol` kann Module und Symbole herunterladen, die zum Analysieren des Speicherabbilds benötigt werden.

## <a name="options"></a>Optionen

- **`--microsoft-symbol-server`**

  Hinzufügen des Symbolserverpfads 'http://msdl.microsoft.com/download/symbols' (Standard)

- **`--server-path <symbol server path>`**

  Hinzufügen eines Symbolservers zum Serverpfad

- **`authenticated-server-path <pat> <server path>`**

  Hinzufügen eines authentifizierten Symbolservers zum Serverpfad mit einem persönlichen Zugriffstoken (Personal Access Token, PAT)

- **`--cache-directory <file cache directory>`**

  Hinzufügen eines Cacheverzeichnisses

- **`--recurse-subdirectories`**

  Verarbeiten von Eingabedateien in allen Unterverzeichnissen

- **`--host-only`**

  Nur das Hostprogramm (d. h. dotnet), das LLDB zum Laden von Kernspeicherabbildern benötigt, wird heruntergeladen.

- **`--symbols`**

  Herunterladen von Symboldateien (.pdb, .dbg, .dwarf)

- **`--modules`**

  Herunterladen der Moduldateien (.dll, .so, .dylib)

- **`--debugging`**

  Herunterladen der speziellen Debugmodule (DAC, DBI, SOS)

- **`--windows-pdbs`**

  Erzwingen des Herunterladens der Windows-PDB-Dateien, wenn auch portierbare PDB-Dateien verfügbar sind

- **`-o, --output <output directory>`**

  Mit dieser Option wird ein Ausgabeverzeichnis festgelegt. Andernfalls wird der Speicherort der Eingabedatei verwendet (Standard).

- **`-d, --diagnostics`**

  Aktivieren der Diagnoseausgabe

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="download-symbols"></a>Herunterladen von Symbolen

Wenn Sie `dotnet-symbol` für eine Speicherabbilddatei ausführen, werden standardmäßig alle Module, Symbole und DAC-/DBI-Dateien heruntergeladen, die zum Debuggen dieses Speicherabbilds benötigt werden, einschließlich der verwalteten Assemblys. Da SOS nun bei Bedarf Symbole herunterladen kann, kann bei der Analyse der meisten Linux-Kernspeicherabbilder lldb mit nur dem Host (dotnet) und den Debugmodulen verwendet werden. Führen Sie den folgenden Befehl aus, um diese für die Diagnose eines Kernspeicherabbilds mit lldb erforderlichen Dateien abzurufen:

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a>Problembehandlung

- „404 Nicht gefunden“ beim Herunterladen von Symbolen

   Das Herunterladen von Symbolen wird nur für offizielle Versionen der .NET Core-Runtime unterstützt, die über offizielle Kanäle wie [die offizielle Website](https://dotnet.microsoft.com/download/dotnet-core) und die [Standardquellen in den dotnet-Installationsskripts](../tools/dotnet-install-script.md) erworben wurden. Der Fehler 404 beim Herunterladen von Debugdateien kann ein Hinweis darauf sein, dass das Speicherabbild mit einer .NET Core-Runtime aus einer anderen Quelle erstellt wurde, z. B. mit einer lokal vollständig selbst erstellten Version oder einer für eine bestimmte Linux-Distribution oder von Communitysites wie archlinux. In diesen Fällen sollten die für das Debuggen erforderlichen Dateien (dotnet, libcoreclr.so und libmscordaccore.so) aus diesen Quellen kopiert werden oder aus der Umgebung, in der die Speicherabbilddatei erstellt wurde.

## <a name="see-also"></a>Siehe auch

* [Debuggen mit Symbolen](/windows/win32/dxtecharts/debugging-with-symbols)
* [Portable PDB-Dateien](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md)
