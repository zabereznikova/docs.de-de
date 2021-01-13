---
title: Diagnosetool „dotnet-sos“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-sos“ installieren und zum Verwalten der SOS-Debuggererweiterung verwenden, die unter Windows und Linux mit nativen Debuggern verwendet wird.
ms.date: 11/17/2020
ms.openlocfilehash: 09e8228c47bdc632bccf3c9ad2296d55fe420060
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/24/2020
ms.locfileid: "97765006"
---
# <a name="sos-installer-dotnet-sos"></a>SOS-Installer (dotnet-sos)

**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen

## <a name="install"></a>Installieren

Es gibt zwei Möglichkeiten, `dotnet-sos` herunterzuladen und zu installieren:

- **Globales dotnet-Tool:**

  Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- **Direkter Download:**

  Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:

  | OS  | Plattform |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-sos/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64) |

## <a name="synopsis"></a>Übersicht

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Beschreibung

Über das globale `dotnet-sos`-Tool wird die [SOS-Debuggererweiterung](sos-debugging-extension.md) installiert. Mit dieser Erweiterung können Sie den verwalteten .NET Core-Status von nativen Debuggern wie LLDB und WinDbg überprüfen.

> [!NOTE]
> Die Installation von SOS über das Tool `dotnet-sos` wird nur unter Linux oder macOS benötigt.  Sie ist möglicherweise auch unter Windows erforderlich, wenn Sie ältere Debuggingtools verwenden. In den letzten Versionen des [Windows-Debuggers](/windows-hardware/drivers/debugger/debugger-download-tools) (ab Version 10.0.18317.1001 von WinDbg oder CDB) wird SOS automatisch aus dem Microsoft-Erweiterungskatalog geladen.  

## <a name="options"></a>Optionen

- **`--version`**

  Zeigt Versionsinformationen an.

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="dotnet-sos-install"></a>dotnet-sos install

Mit diesem Befehl wird die [SOS-Erweiterung](sos-debugging-extension.md) zum Debuggen von.NET Core-Prozessen lokal installiert. Unter macOS und Linux wird die *LLDBINIT*-Datei so aktualisiert, dass die Erweiterung beim Starten von LLDB automatisch geladen wird. Wenn Sie SOS unter Windows mit älteren Debuggingtools (niedriger als Version 10.0.18317.1001) installieren, müssen Sie die Erweiterung manuell in WinDbg oder CDB laden, indem Sie `.load %USERPROFILE%\.dotnet\sos\sos.dll` im Debugger ausführen.

### <a name="synopsis"></a>Übersicht

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a>Optionen

- **`--architecture <arch>`**

  Gibt die Prozessorarchitektur der zu installierenden SOS-Binärdateien an. Standardmäßig installiert `dotnet-sos` die Architektur des Hostcomputers. Verwenden Sie diese Option, wenn Sie SOS für eine Architektur installieren möchten, die sich von der dotnet-Hostarchitektur unterscheidet. Wenn Sie beispielsweise Arm32-Binärdateien über einen Arm64-Host ausführen, müssen Sie SOS mit `dotnet-sos install --architecture Arm` installieren.

  Die folgenden Architekturen sind verfügbar:

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a>dotnet-sos uninstall

Mit diesem Befehl wird die [SOS-Erweiterung](sos-debugging-extension.md) deinstalliert und unter Linux und macOS aus der LLDB-Konfiguration entfernt.

### <a name="synopsis"></a>Übersicht

```console
dotnet-sos uninstall
```
