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
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="02259-103">SOS-Installer (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="02259-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="02259-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="02259-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="02259-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="02259-105">Install</span></span>

<span data-ttu-id="02259-106">Es gibt zwei Möglichkeiten, `dotnet-sos` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="02259-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="02259-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="02259-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="02259-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="02259-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="02259-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="02259-109">**Direct download:**</span></span>

  <span data-ttu-id="02259-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="02259-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="02259-111">OS</span><span class="sxs-lookup"><span data-stu-id="02259-111">OS</span></span>  | <span data-ttu-id="02259-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="02259-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="02259-113">Windows</span><span class="sxs-lookup"><span data-stu-id="02259-113">Windows</span></span> | <span data-ttu-id="02259-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="02259-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="02259-115">macOS</span><span class="sxs-lookup"><span data-stu-id="02259-115">macOS</span></span>   | [<span data-ttu-id="02259-116">x64</span><span class="sxs-lookup"><span data-stu-id="02259-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="02259-117">Linux</span><span class="sxs-lookup"><span data-stu-id="02259-117">Linux</span></span>   | <span data-ttu-id="02259-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="02259-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="02259-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="02259-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="02259-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02259-120">Description</span></span>

<span data-ttu-id="02259-121">Über das globale `dotnet-sos`-Tool wird die [SOS-Debuggererweiterung](sos-debugging-extension.md) installiert.</span><span class="sxs-lookup"><span data-stu-id="02259-121">The `dotnet-sos` global tool installs the [SOS debugger extension](sos-debugging-extension.md).</span></span> <span data-ttu-id="02259-122">Mit dieser Erweiterung können Sie den verwalteten .NET Core-Status von nativen Debuggern wie LLDB und WinDbg überprüfen.</span><span class="sxs-lookup"><span data-stu-id="02259-122">This extension lets you inspect managed .NET Core state from native debuggers like lldb and windbg.</span></span>

> [!NOTE]
> <span data-ttu-id="02259-123">Die Installation von SOS über das Tool `dotnet-sos` wird nur unter Linux oder macOS benötigt.</span><span class="sxs-lookup"><span data-stu-id="02259-123">Installing SOS via the `dotnet-sos` tool is only needed on Linux or macOS.</span></span>  <span data-ttu-id="02259-124">Sie ist möglicherweise auch unter Windows erforderlich, wenn Sie ältere Debuggingtools verwenden.</span><span class="sxs-lookup"><span data-stu-id="02259-124">It may also be needed on Windows if you're using older debugging tools.</span></span> <span data-ttu-id="02259-125">In den letzten Versionen des [Windows-Debuggers](/windows-hardware/drivers/debugger/debugger-download-tools) (ab Version 10.0.18317.1001 von WinDbg oder CDB) wird SOS automatisch aus dem Microsoft-Erweiterungskatalog geladen.</span><span class="sxs-lookup"><span data-stu-id="02259-125">Recent versions of the [Windows Debugger](/windows-hardware/drivers/debugger/debugger-download-tools) (>= version 10.0.18317.1001 of WinDbg or cdb) load SOS automatically from the Microsoft extension gallery.</span></span>  

## <a name="options"></a><span data-ttu-id="02259-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="02259-126">Options</span></span>

- **`--version`**

  <span data-ttu-id="02259-127">Zeigt Versionsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="02259-127">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="02259-128">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="02259-128">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="02259-129">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="02259-129">dotnet-sos install</span></span>

<span data-ttu-id="02259-130">Mit diesem Befehl wird die [SOS-Erweiterung](sos-debugging-extension.md) zum Debuggen von.NET Core-Prozessen lokal installiert.</span><span class="sxs-lookup"><span data-stu-id="02259-130">Installs the [SOS extension](sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="02259-131">Unter macOS und Linux wird die *LLDBINIT*-Datei so aktualisiert, dass die Erweiterung beim Starten von LLDB automatisch geladen wird.</span><span class="sxs-lookup"><span data-stu-id="02259-131">On macOS and Linux, the *.lldbinit* file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="02259-132">Wenn Sie SOS unter Windows mit älteren Debuggingtools (niedriger als Version 10.0.18317.1001) installieren, müssen Sie die Erweiterung manuell in WinDbg oder CDB laden, indem Sie `.load %USERPROFILE%\.dotnet\sos\sos.dll` im Debugger ausführen.</span><span class="sxs-lookup"><span data-stu-id="02259-132">If you're installing SOS on Windows with older debugging tools (prior to version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="02259-133">Übersicht</span><span class="sxs-lookup"><span data-stu-id="02259-133">Synopsis</span></span>

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a><span data-ttu-id="02259-134">Optionen</span><span class="sxs-lookup"><span data-stu-id="02259-134">Options</span></span>

- **`--architecture <arch>`**

  <span data-ttu-id="02259-135">Gibt die Prozessorarchitektur der zu installierenden SOS-Binärdateien an.</span><span class="sxs-lookup"><span data-stu-id="02259-135">Specifies the processor architecture of the SOS binaries to install.</span></span> <span data-ttu-id="02259-136">Standardmäßig installiert `dotnet-sos` die Architektur des Hostcomputers.</span><span class="sxs-lookup"><span data-stu-id="02259-136">By default, `dotnet-sos` installs the architecture of the host machine.</span></span> <span data-ttu-id="02259-137">Verwenden Sie diese Option, wenn Sie SOS für eine Architektur installieren möchten, die sich von der dotnet-Hostarchitektur unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="02259-137">Use this option when you want to install SOS for an architecture that's different from the dotnet host architecture.</span></span> <span data-ttu-id="02259-138">Wenn Sie beispielsweise Arm32-Binärdateien über einen Arm64-Host ausführen, müssen Sie SOS mit `dotnet-sos install --architecture Arm` installieren.</span><span class="sxs-lookup"><span data-stu-id="02259-138">For example, if you're running Arm32 binaries from an Arm64 host, you will need to install SOS with `dotnet-sos install --architecture Arm`.</span></span>

  <span data-ttu-id="02259-139">Die folgenden Architekturen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="02259-139">The following architectures are available:</span></span>

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="02259-140">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="02259-140">dotnet-sos uninstall</span></span>

<span data-ttu-id="02259-141">Mit diesem Befehl wird die [SOS-Erweiterung](sos-debugging-extension.md) deinstalliert und unter Linux und macOS aus der LLDB-Konfiguration entfernt.</span><span class="sxs-lookup"><span data-stu-id="02259-141">Uninstalls the [SOS extension](sos-debugging-extension.md) and, on Linux and macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="02259-142">Übersicht</span><span class="sxs-lookup"><span data-stu-id="02259-142">Synopsis</span></span>

```console
dotnet-sos uninstall
```
