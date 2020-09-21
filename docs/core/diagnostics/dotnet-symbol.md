---
title: dotnet-symbol – .NET Core
description: Hier erfahren Sie mehr über das Installieren und Verwenden des Befehlszeilentools „dotnet-symbol“.
ms.date: 08/26/2020
ms.openlocfilehash: 5a96306fc96525b00e57eda089a45b730a7e3e8c
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679187"
---
# <a name="symbol-downloader-dotnet-symbol"></a><span data-ttu-id="2644a-103">Symboldownloadprogramm (dotnet-symbol)</span><span class="sxs-lookup"><span data-stu-id="2644a-103">Symbol downloader (dotnet-symbol)</span></span>

<span data-ttu-id="2644a-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="2644a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-symbol"></a><span data-ttu-id="2644a-105">Installieren von dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="2644a-105">Install dotnet-symbol</span></span>

<span data-ttu-id="2644a-106">Verwenden Sie zum Installieren der neuesten Releaseversion des [NuGet-Pakets](https://www.nuget.org/packages/dotnet-symbol) `dotnet-symbol` den Befehl [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="2644a-106">To install the latest release version of the `dotnet-symbol` [NuGet package](https://www.nuget.org/packages/dotnet-symbol), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-symbol
```

## <a name="synopsis"></a><span data-ttu-id="2644a-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2644a-107">Synopsis</span></span>

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a><span data-ttu-id="2644a-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2644a-108">Description</span></span>

<span data-ttu-id="2644a-109">Das globale Tool `dotnet-symbol` lädt Dateien (Symbole, DAC, Module usw.) herunter, die zum Debuggen von Kernspeicherabbildern und Minidumps benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2644a-109">The `dotnet-symbol` global tool downloads files (symbols, DAC, modules, etc.) needed for debugging core dumps and minidumps.</span></span> <span data-ttu-id="2644a-110">Dies kann nützlich sein, wenn Sie auf einem anderen Computer erfasste Speicherabbilder debuggen.</span><span class="sxs-lookup"><span data-stu-id="2644a-110">This can be useful when debugging dumps captured on another machine.</span></span> <span data-ttu-id="2644a-111">`dotnet-symbol` kann Module und Symbole herunterladen, die zum Analysieren des Speicherabbilds benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2644a-111">`dotnet-symbol` can download modules and symbols needed to analyze the dump.</span></span>

## <a name="options"></a><span data-ttu-id="2644a-112">Optionen</span><span class="sxs-lookup"><span data-stu-id="2644a-112">Options</span></span>

- **`--microsoft-symbol-server`**

  <span data-ttu-id="2644a-113">Hinzufügen des Symbolserverpfads http://msdl.microsoft.com/download/symbols (Standard)</span><span class="sxs-lookup"><span data-stu-id="2644a-113">Add 'http://msdl.microsoft.com/download/symbols' symbol server path (default).</span></span>

- **`--server-path <symbol server path>`**

  <span data-ttu-id="2644a-114">Hinzufügen eines Symbolservers zum Serverpfad</span><span class="sxs-lookup"><span data-stu-id="2644a-114">Add a symbol server to the server path.</span></span>

- **`authenticated-server-path <pat> <server path>`**

  <span data-ttu-id="2644a-115">Hinzufügen eines authentifizierten Symbolservers zum Serverpfad mit einem persönlichen Zugriffstoken (Personal Access Token, PAT)</span><span class="sxs-lookup"><span data-stu-id="2644a-115">Add an authenticated symbol server to the server path using a personal access token (PAT).</span></span>

- **`--cache-directory <file cache directory>`**

  <span data-ttu-id="2644a-116">Hinzufügen eines Cacheverzeichnisses</span><span class="sxs-lookup"><span data-stu-id="2644a-116">Adds a cache directory.</span></span>

- **`--recurse-subdirectories`**

  <span data-ttu-id="2644a-117">Verarbeiten von Eingabedateien in allen Unterverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="2644a-117">Process input files in all subdirectories.</span></span>

- **`--host-only`**

  <span data-ttu-id="2644a-118">Nur das Hostprogramm (d. h. dotnet), das lldb zum Laden von Kernspeicherabbildern benötigt, wird heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="2644a-118">Download only the host program (i.e. dotnet) that lldb needs for loading core dumps.</span></span>

- **`--symbols`**

  <span data-ttu-id="2644a-119">Herunterladen von Symboldateien (.pdb, .dbg, .dwarf)</span><span class="sxs-lookup"><span data-stu-id="2644a-119">Download symbol files (.pdb, .dbg, .dwarf).</span></span>

- **`--modules`**

  <span data-ttu-id="2644a-120">Herunterladen der Moduldateien (.dll, .so, .dylib)</span><span class="sxs-lookup"><span data-stu-id="2644a-120">Download the module files (.dll, .so, .dylib).</span></span>

- **`--debugging`**

  <span data-ttu-id="2644a-121">Herunterladen der speziellen Debugmodule (DAC, DBI, SOS)</span><span class="sxs-lookup"><span data-stu-id="2644a-121">Download the special debugging modules (DAC, DBI, SOS).</span></span>

- **`--windows-pdbs`**

  <span data-ttu-id="2644a-122">Erzwingen des Herunterladens der Windows-PDB-Dateien, wenn auch portierbare PDB-Dateien verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="2644a-122">Force the downloading of the Windows PDBs when Portable PDBs are also available.</span></span>

- **`-o, --output <output directory>`**

  <span data-ttu-id="2644a-123">Mit dieser Option wird ein Ausgabeverzeichnis festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2644a-123">Set the output directory.</span></span> <span data-ttu-id="2644a-124">Andernfalls wird der Speicherort der Eingabedatei verwendet (Standard).</span><span class="sxs-lookup"><span data-stu-id="2644a-124">Otherwise, write next to the input file (default).</span></span>

- **`-d, --diagnostics`**

  <span data-ttu-id="2644a-125">Aktivieren der Diagnoseausgabe</span><span class="sxs-lookup"><span data-stu-id="2644a-125">Enable diagnostic output.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2644a-126">Zeigt die Hilfe für die Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="2644a-126">Shows command-line help.</span></span>

## <a name="download-symbols"></a><span data-ttu-id="2644a-127">Herunterladen von Symbolen</span><span class="sxs-lookup"><span data-stu-id="2644a-127">Download symbols</span></span>

<span data-ttu-id="2644a-128">Wenn Sie `dotnet-symbol` für eine Speicherabbilddatei ausführen, werden standardmäßig alle Module, Symbole und DAC-/DBI-Dateien heruntergeladen, die zum Debuggen dieses Speicherabbilds benötigt werden, einschließlich der verwalteten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="2644a-128">Running `dotnet-symbol` against a dump file will, by default, download all the modules, symbols, and DAC/DBI files needed to debug the dump including the managed assemblies.</span></span> <span data-ttu-id="2644a-129">Da SOS nun bei Bedarf Symbole herunterladen kann, kann bei der Analyse der meisten Linux-Kernspeicherabbilder lldb mit nur dem Host (dotnet) und den Debugmodulen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2644a-129">Because SOS can now download symbols when needed, most Linux core dumps can be analyzed using lldb with only the host (dotnet) and debugging modules.</span></span> <span data-ttu-id="2644a-130">Führen Sie den folgenden Befehl aus, um diese für die Diagnose eines Kernspeicherabbilds mit lldb erforderlichen Dateien abzurufen:</span><span class="sxs-lookup"><span data-stu-id="2644a-130">To get these files necessary for diagnosing a core dump with lldb run:</span></span>

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a><span data-ttu-id="2644a-131">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="2644a-131">Troubleshoot</span></span>

- <span data-ttu-id="2644a-132">„404 Nicht gefunden“ beim Herunterladen von Symbolen</span><span class="sxs-lookup"><span data-stu-id="2644a-132">404 Not Found while downloading symbols.</span></span>

   <span data-ttu-id="2644a-133">Das Herunterladen von Symbolen wird nur für offizielle Versionen der .NET Core-Runtime unterstützt, die über offizielle Kanäle wie [die offizielle Website](https://dotnet.microsoft.com/download/dotnet-core) und die [Standardquellen in den dotnet-Installationsskripts](../tools/dotnet-install-script.md) erworben wurden.</span><span class="sxs-lookup"><span data-stu-id="2644a-133">Symbol download is only supported for official .NET Core runtime versions acquired through official channels such as [the official web site](https://dotnet.microsoft.com/download/dotnet-core) and the [default sources in the dotnet installation scripts](../tools/dotnet-install-script.md).</span></span> <span data-ttu-id="2644a-134">Der Fehler 404 beim Herunterladen von Debugdateien kann ein Hinweis darauf sein, dass das Speicherabbild mit einer .NET Core-Runtime aus einer anderen Quelle erstellt wurde, z. B. mit einer lokal vollständig selbst erstellten Version oder einer für eine bestimmte Linux-Distribution oder von Communitysites wie archlinux.</span><span class="sxs-lookup"><span data-stu-id="2644a-134">A 404 error while downloading debugging files may indicate that the dump was created with a .NET Core runtime from another source, such as one built from source locally or for a particular Linux distro, or from community sites like archlinux.</span></span> <span data-ttu-id="2644a-135">In diesen Fällen sollten die für das Debuggen erforderlichen Dateien (dotnet, libcoreclr.so und libmscordaccore.so) aus diesen Quellen kopiert werden oder aus der Umgebung, in der die Speicherabbilddatei erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2644a-135">In such cases, file necessary for debugging (dotnet, libcoreclr.so, and libmscordaccore.so) should be copied from those sources or from the environment the dump file was created in.</span></span>
