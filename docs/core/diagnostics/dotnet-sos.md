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
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="408fa-103">SOS-Installer (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="408fa-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="408fa-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="408fa-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="408fa-105">Installieren</span><span class="sxs-lookup"><span data-stu-id="408fa-105">Install</span></span>

<span data-ttu-id="408fa-106">Es gibt zwei Möglichkeiten, `dotnet-sos` herunterzuladen und zu installieren:</span><span class="sxs-lookup"><span data-stu-id="408fa-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="408fa-107">**Globales dotnet-Tool:**</span><span class="sxs-lookup"><span data-stu-id="408fa-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="408fa-108">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-sos) `dotnet-sos` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="408fa-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="408fa-109">**Direkter Download:**</span><span class="sxs-lookup"><span data-stu-id="408fa-109">**Direct download:**</span></span>

  <span data-ttu-id="408fa-110">Laden Sie die ausführbare Datei für das Tool herunter, die Ihrer Plattform entspricht:</span><span class="sxs-lookup"><span data-stu-id="408fa-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="408fa-111">OS</span><span class="sxs-lookup"><span data-stu-id="408fa-111">OS</span></span>  | <span data-ttu-id="408fa-112">Plattform</span><span class="sxs-lookup"><span data-stu-id="408fa-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="408fa-113">Windows</span><span class="sxs-lookup"><span data-stu-id="408fa-113">Windows</span></span> | <span data-ttu-id="408fa-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="408fa-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="408fa-115">macOS</span><span class="sxs-lookup"><span data-stu-id="408fa-115">macOS</span></span>   | [<span data-ttu-id="408fa-116">x64</span><span class="sxs-lookup"><span data-stu-id="408fa-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="408fa-117">Linux</span><span class="sxs-lookup"><span data-stu-id="408fa-117">Linux</span></span>   | <span data-ttu-id="408fa-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="408fa-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="408fa-119">Übersicht</span><span class="sxs-lookup"><span data-stu-id="408fa-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="408fa-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="408fa-120">Description</span></span>

<span data-ttu-id="408fa-121">Das globale Tool `dotnet-sos` installiert die [SOS-Debuggererweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md), die die [Überprüfung des verwalteten .NET Core-Zustands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) über native Debugger wie WinDbg/cdb unter Windows und lldb unter Linux und macOS ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="408fa-121">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="408fa-122">In den aktuellen Versionen des Windows-Debuggers (Version 10.0.18317.1001 und höher von WinDbg oder cdb) wird SOS automatisch aus dem Microsoft-Erweiterungskatalog geladen. Die Installation von SOS über das Tool `dotnet-sos` ist daher nur unter Linux und macOS erforderlich oder bei Verwendung älterer Debugtools unter Windows.</span><span class="sxs-lookup"><span data-stu-id="408fa-122">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="408fa-123">Optionen</span><span class="sxs-lookup"><span data-stu-id="408fa-123">Options</span></span>

- **`--version`**

  <span data-ttu-id="408fa-124">Zeigt Versionsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="408fa-124">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="408fa-125">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="408fa-125">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="408fa-126">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="408fa-126">dotnet-sos install</span></span>

<span data-ttu-id="408fa-127">Mit diesem Befehl wird die [SOS-Erweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) zum Debuggen von.NET Core-Prozessen lokal installiert.</span><span class="sxs-lookup"><span data-stu-id="408fa-127">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="408fa-128">Unter macOS und Linux wird die .lldbinit-Datei so aktualisiert, dass die Erweiterung beim Starten von lldb automatisch geladen wird.</span><span class="sxs-lookup"><span data-stu-id="408fa-128">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="408fa-129">Wenn Sie SOS unter Windows mit älteren Debugtools (niedriger als Version 10.0.18317.1001) installieren, müssen Sie die Erweiterung manuell in WinDbg oder cdb laden, indem Sie im Debugger `.load %USERPROFILE%\.dotnet\sos\sos.dll` ausführen.</span><span class="sxs-lookup"><span data-stu-id="408fa-129">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="408fa-130">Übersicht</span><span class="sxs-lookup"><span data-stu-id="408fa-130">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="408fa-131">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="408fa-131">dotnet-sos uninstall</span></span>

<span data-ttu-id="408fa-132">Mit diesem Befehl wird die [SOS-Erweiterung](../../framework/tools/sos-dll-sos-debugging-extension.md) deinstalliert und unter Linux und macOS aus der lldb-Konfiguration entfernt.</span><span class="sxs-lookup"><span data-stu-id="408fa-132">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="408fa-133">Übersicht</span><span class="sxs-lookup"><span data-stu-id="408fa-133">Synopsis</span></span>

```console
dotnet-sos uninstall
```
