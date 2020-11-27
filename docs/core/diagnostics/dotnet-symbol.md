---
title: Diagnosetool „dotnet-symbol“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-symbol“ installieren und zum Herunterladen von Dateien verwenden, die für das Debuggen von .NET-Speicherabbildern und Minidumps erforderlich sind.
ms.date: 11/17/2020
ms.openlocfilehash: 8ea694e5331f1e4e75b3b3ad644428568e515331
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825337"
---
# <a name="symbol-downloader-dotnet-symbol"></a>Symboldownloadprogramm (dotnet-symbol)

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="install"></a>Installieren

Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

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

  Nur das Hostprogramm (d. h. dotnet), das lldb zum Laden von Kernspeicherabbildern benötigt, wird heruntergeladen.

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
