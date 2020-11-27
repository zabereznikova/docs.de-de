---
title: Diagnosetool „dotnet-sos“ – .NET-CLI
description: Hier erfahren Sie, wie Sie das CLI-Tool „dotnet-sos“ installieren und zum Verwalten der SOS-Debuggererweiterung verwenden, die unter Windows und Linux mit nativen Debuggern verwendet wird.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825441"
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

Das globale Tool `dotnet-sos` installiert die [SOS-Debuggererweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md), die die [Überprüfung des verwalteten .NET Core-Zustands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) über native Debugger wie WinDbg/cdb unter Windows und lldb unter Linux und macOS ermöglicht. In den aktuellen Versionen des Windows-Debuggers (Version 10.0.18317.1001 und höher von WinDbg oder cdb) wird SOS automatisch aus dem Microsoft-Erweiterungskatalog geladen. Die Installation von SOS über das Tool `dotnet-sos` ist daher nur unter Linux und macOS erforderlich oder bei Verwendung älterer Debugtools unter Windows.

## <a name="options"></a>Optionen

- **`--version`**

  Zeigt Versionsinformationen an.

- **`-h|--help`**

  Zeigt die Hilfe für die Befehlszeile an.

## <a name="dotnet-sos-install"></a>dotnet-sos install

Mit diesem Befehl wird die [SOS-Erweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) zum Debuggen von.NET Core-Prozessen lokal installiert. Unter macOS und Linux wird die .lldbinit-Datei so aktualisiert, dass die Erweiterung beim Starten von lldb automatisch geladen wird. Wenn Sie SOS unter Windows mit älteren Debugtools (niedriger als Version 10.0.18317.1001) installieren, müssen Sie die Erweiterung manuell in WinDbg oder cdb laden, indem Sie im Debugger `.load %USERPROFILE%\.dotnet\sos\sos.dll` ausführen.

### <a name="synopsis"></a>Übersicht

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>dotnet-sos uninstall

Mit diesem Befehl wird die [SOS-Erweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) deinstalliert und unter Linux und macOS aus der lldb-Konfiguration entfernt.

### <a name="synopsis"></a>Übersicht

```console
dotnet-sos uninstall
```
