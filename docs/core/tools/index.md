---
title: .NET CLI
titleSuffix: ''
description: Eine Übersicht über die .NET-CLI und ihre Features.
ms.topic: overview
ms.date: 02/13/2020
ms.openlocfilehash: 6a12e2d16afe36092c10e14a7465fa3bdbb23f32
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633855"
---
# <a name="net-cli-overview"></a><span data-ttu-id="fd3ba-103">Übersicht über die .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="fd3ba-103">.NET CLI overview</span></span>

<span data-ttu-id="fd3ba-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="fd3ba-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="fd3ba-105">Die .NET-Befehlszeilenschnittstelle (CLI) ist eine plattformübergreifende Toolkette zum Entwicklung, Erstellen, Ausführen und Veröffentlichen von .NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-105">The .NET command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET applications.</span></span>

<span data-ttu-id="fd3ba-106">Die .NET-CLI ist im [.NET SDK](../sdk.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-106">The .NET CLI is included with the [.NET SDK](../sdk.md).</span></span> <span data-ttu-id="fd3ba-107">Informationen zum Installieren des .NET SDK finden Sie unter [Installieren von .NET Core](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ba-107">To learn how to install the .NET SDK, see [Install .NET Core](../install/windows.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="fd3ba-108">CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="fd3ba-108">CLI commands</span></span>

<span data-ttu-id="fd3ba-109">Die folgenden Befehle werden standardmäßig erstellt:</span><span class="sxs-lookup"><span data-stu-id="fd3ba-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="fd3ba-110">Grundlegende Befehle</span><span class="sxs-lookup"><span data-stu-id="fd3ba-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="fd3ba-111">Befehle zur Projektänderung</span><span class="sxs-lookup"><span data-stu-id="fd3ba-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="fd3ba-112">Erweiterte Befehle</span><span class="sxs-lookup"><span data-stu-id="fd3ba-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="fd3ba-113">Befehle für die Toolverwaltung</span><span class="sxs-lookup"><span data-stu-id="fd3ba-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="fd3ba-114">[`tool restore`](global-tools.md#install-a-local-tool) Verfügbar ab .NET Core SDK  3.0.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="fd3ba-115">[`tool run`](global-tools.md#invoke-a-local-tool) Verfügbar ab .NET Core SDK  3.0.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="fd3ba-116">Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="fd3ba-117">Sie können Tools selbst schreiben oder Drittanbietertools installieren.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="fd3ba-118">Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="fd3ba-119">Weitere Informationen finden Sie unter [Übersicht über .NET-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="fd3ba-119">For more information, see [.NET tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="fd3ba-120">Befehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="fd3ba-120">Command structure</span></span>

<span data-ttu-id="fd3ba-121">Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options).</span><span class="sxs-lookup"><span data-stu-id="fd3ba-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="fd3ba-122">Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="fd3ba-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="fd3ba-123">Treiber</span><span class="sxs-lookup"><span data-stu-id="fd3ba-123">Driver</span></span>

<span data-ttu-id="fd3ba-124">Der Treiber trägt den Namen [dotnet](dotnet.md) und hat zwei Aufgaben, entweder die Ausführung einer [Framework-abhängigen Anwendung](../deploying/index.md) oder die Ausführung eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="fd3ba-125">Geben Sie zur Ausführung einer Framework-abhängigen Anwendung nach dem Treiber die Anwendung an, z.B. `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="fd3ba-126">Führen Sie beim Ausführen des Befehls aus dem Ordner, in dem sich die DLL der Anwendung befindet, einfach `dotnet my_app.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="fd3ba-127">Wenn Sie eine bestimmte Version der .NET-Runtime verwenden möchten, verwenden Sie die `--fx-version <VERSION>`-Option (weitere Informationen dazu finden Sie in der [Referenz zum dotnet-Befehl](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="fd3ba-127">If you want to use a specific version of the .NET Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="fd3ba-128">Wenn Sie einen Befehl an den Treiber geben, startet `dotnet.exe` den Ausführungsprozess des CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="fd3ba-129">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fd3ba-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="fd3ba-130">Zunächst bestimmt der Treiber die zu verwendende SDK-Version.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="fd3ba-131">Wenn keine [global.json](global-json.md)-Datei vorhanden ist, wird die neueste Version des verfügbaren SDK verwendet.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="fd3ba-132">Dabei handelt es sich entweder um eine Vorschauversion oder eine stabile Version, je nachdem, welche Version sich aktuell auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="fd3ba-133">Sobald die SDK-Version bestimmt ist, wird der Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="fd3ba-134">Befehl</span><span class="sxs-lookup"><span data-stu-id="fd3ba-134">Command</span></span>

<span data-ttu-id="fd3ba-135">Über den Befehl wird eine Aktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-135">The command performs an action.</span></span> <span data-ttu-id="fd3ba-136">Beispielsweise erstellt der Befehl `dotnet build` Code und</span><span class="sxs-lookup"><span data-stu-id="fd3ba-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="fd3ba-137">der Befehl `dotnet publish` veröffentlicht Code.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="fd3ba-138">Die Befehle werden mit einer `dotnet {command}`-Konvention als Konsolenanwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="fd3ba-139">Argumente</span><span class="sxs-lookup"><span data-stu-id="fd3ba-139">Arguments</span></span>

<span data-ttu-id="fd3ba-140">Die Argumente, die Sie in der Befehlszeile übergeben, sind die Argumente für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="fd3ba-141">Wenn Sie z. B. `dotnet publish my_app.csproj` ausführen, gibt das `my_app.csproj`-Argument das zu veröffentlichende Projekt an und wird an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="fd3ba-142">Optionen</span><span class="sxs-lookup"><span data-stu-id="fd3ba-142">Options</span></span>

<span data-ttu-id="fd3ba-143">Die Optionen, die Sie in der Befehlszeile übergeben, sind die Optionen für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="fd3ba-144">Wenn Sie z. B. `dotnet publish --output /build_output` ausführen, werden die `--output`-Option und ihr Wert an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="fd3ba-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd3ba-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd3ba-145">See also</span></span>

- [<span data-ttu-id="fd3ba-146">GitHub-Repository „dotnet/sdk“</span><span class="sxs-lookup"><span data-stu-id="fd3ba-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="fd3ba-147">.NET-Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="fd3ba-147">.NET installation guide</span></span>](../install/windows.md)
