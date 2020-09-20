---
title: dotnet-sos – .NET Core
description: Hier erfahren Sie, wie Sie das Befehlszeilentool dotnet-sos installieren und verwenden.
ms.date: 08/26/2020
ms.openlocfilehash: ba83105718909038ca56129ed8a5063aeff12e89
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065083"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="d43ed-103">SOS-Installer (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="d43ed-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="d43ed-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="d43ed-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-sos"></a><span data-ttu-id="d43ed-105">Installieren von dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="d43ed-105">Install dotnet-sos</span></span>

<span data-ttu-id="d43ed-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="d43ed-106">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a><span data-ttu-id="d43ed-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d43ed-107">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="d43ed-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d43ed-108">Description</span></span>

<span data-ttu-id="d43ed-109">Das globale Tool `dotnet-sos` installiert die [SOS-Debuggererweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md), die die [Überprüfung des verwalteten .NET Core-Zustands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) über native Debugger wie WinDbg/cdb unter Windows und lldb unter Linux und macOS ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="d43ed-109">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="d43ed-110">In den aktuellen Versionen des Windows-Debuggers (Version 10.0.18317.1001 und höher von WinDbg oder cdb) wird SOS automatisch aus dem Microsoft-Erweiterungskatalog geladen. Die Installation von SOS über das Tool `dotnet-sos` ist daher nur unter Linux und macOS erforderlich oder bei Verwendung älterer Debugtools unter Windows.</span><span class="sxs-lookup"><span data-stu-id="d43ed-110">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="d43ed-111">Optionen</span><span class="sxs-lookup"><span data-stu-id="d43ed-111">Options</span></span>

- **`--version`**

  <span data-ttu-id="d43ed-112">Zeigt Versionsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="d43ed-112">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d43ed-113">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="d43ed-113">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="d43ed-114">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="d43ed-114">dotnet-sos install</span></span>

<span data-ttu-id="d43ed-115">Mit diesem Befehl wird die [SOS-Erweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) zum Debuggen von.NET Core-Prozessen lokal installiert.</span><span class="sxs-lookup"><span data-stu-id="d43ed-115">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="d43ed-116">Unter macOS und Linux wird die .lldbinit-Datei so aktualisiert, dass die Erweiterung beim Starten von lldb automatisch geladen wird.</span><span class="sxs-lookup"><span data-stu-id="d43ed-116">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="d43ed-117">Wenn Sie SOS unter Windows mit älteren Debugtools (niedriger als Version 10.0.18317.1001) installieren, müssen Sie die Erweiterung manuell in WinDbg oder cdb laden, indem Sie im Debugger `.load %USERPROFILE%\.dotnet\sos\sos.dll` ausführen.</span><span class="sxs-lookup"><span data-stu-id="d43ed-117">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d43ed-118">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d43ed-118">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="d43ed-119">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="d43ed-119">dotnet-sos uninstall</span></span>

<span data-ttu-id="d43ed-120">Mit diesem Befehl wird die [SOS-Erweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) deinstalliert und unter Linux und macOS aus der lldb-Konfiguration entfernt.</span><span class="sxs-lookup"><span data-stu-id="d43ed-120">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d43ed-121">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d43ed-121">Synopsis</span></span>

```console
dotnet-sos uninstall
```
