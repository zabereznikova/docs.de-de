---
title: .NET Core-CLI
titleSuffix: ''
description: Eine Übersicht über die .NET Core-CLI und ihre Features.
ms.date: 02/13/2020
ms.openlocfilehash: c491088f26a9aa1c065414e76fb0b80d554380b4
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2020
ms.locfileid: "77625981"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="e8eb9-103">Übersicht über die .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="e8eb9-103">.NET Core CLI overview</span></span>

<span data-ttu-id="e8eb9-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.1 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="e8eb9-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="e8eb9-105">Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine plattformübergreifende Toolkette zum Entwicklung, Erstellen, Ausführen und Veröffentlichen von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="e8eb9-106">Die .NET Core-CLI ist im [.NET Core SDK](../sdk.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="e8eb9-107">Informationen zum Installieren des .NET Core SDK finden Sie unter [Installieren des .NET Core SDK](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="e8eb9-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="e8eb9-108">CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="e8eb9-108">CLI commands</span></span>

<span data-ttu-id="e8eb9-109">Die folgenden Befehle werden standardmäßig erstellt:</span><span class="sxs-lookup"><span data-stu-id="e8eb9-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="e8eb9-110">Grundlegende Befehle</span><span class="sxs-lookup"><span data-stu-id="e8eb9-110">Basic commands</span></span>

- [<span data-ttu-id="e8eb9-111">new</span><span class="sxs-lookup"><span data-stu-id="e8eb9-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="e8eb9-112">restore</span><span class="sxs-lookup"><span data-stu-id="e8eb9-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="e8eb9-113">build</span><span class="sxs-lookup"><span data-stu-id="e8eb9-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="e8eb9-114">publish</span><span class="sxs-lookup"><span data-stu-id="e8eb9-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="e8eb9-115">run</span><span class="sxs-lookup"><span data-stu-id="e8eb9-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="e8eb9-116">test</span><span class="sxs-lookup"><span data-stu-id="e8eb9-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="e8eb9-117">vstest</span><span class="sxs-lookup"><span data-stu-id="e8eb9-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="e8eb9-118">pack</span><span class="sxs-lookup"><span data-stu-id="e8eb9-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="e8eb9-119">migrate</span><span class="sxs-lookup"><span data-stu-id="e8eb9-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="e8eb9-120">clean</span><span class="sxs-lookup"><span data-stu-id="e8eb9-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="e8eb9-121">sln</span><span class="sxs-lookup"><span data-stu-id="e8eb9-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="e8eb9-122">help</span><span class="sxs-lookup"><span data-stu-id="e8eb9-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="e8eb9-123">store</span><span class="sxs-lookup"><span data-stu-id="e8eb9-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="e8eb9-124">Befehle zur Projektänderung</span><span class="sxs-lookup"><span data-stu-id="e8eb9-124">Project modification commands</span></span>

- [<span data-ttu-id="e8eb9-125">add package</span><span class="sxs-lookup"><span data-stu-id="e8eb9-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="e8eb9-126">add reference</span><span class="sxs-lookup"><span data-stu-id="e8eb9-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="e8eb9-127">remove package</span><span class="sxs-lookup"><span data-stu-id="e8eb9-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="e8eb9-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="e8eb9-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="e8eb9-129">list reference</span><span class="sxs-lookup"><span data-stu-id="e8eb9-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="e8eb9-130">Erweiterte Befehle</span><span class="sxs-lookup"><span data-stu-id="e8eb9-130">Advanced commands</span></span>

- [<span data-ttu-id="e8eb9-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="e8eb9-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="e8eb9-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="e8eb9-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="e8eb9-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="e8eb9-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="e8eb9-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="e8eb9-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="e8eb9-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="e8eb9-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="e8eb9-136">Befehle für die Toolverwaltung</span><span class="sxs-lookup"><span data-stu-id="e8eb9-136">Tool management commands</span></span>

- [<span data-ttu-id="e8eb9-137">tool install</span><span class="sxs-lookup"><span data-stu-id="e8eb9-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="e8eb9-138">tool list</span><span class="sxs-lookup"><span data-stu-id="e8eb9-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="e8eb9-139">tool update</span><span class="sxs-lookup"><span data-stu-id="e8eb9-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="e8eb9-140">[tool restore](global-tools.md#install-a-local-tool) **Verfügbar ab .NET Core SDK 3.0**</span><span class="sxs-lookup"><span data-stu-id="e8eb9-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="e8eb9-141">[tool run](global-tools.md#invoke-a-local-tool) **Verfügbar ab .NET Core SDK 3.0**</span><span class="sxs-lookup"><span data-stu-id="e8eb9-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="e8eb9-142">tool uninstall</span><span class="sxs-lookup"><span data-stu-id="e8eb9-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="e8eb9-143">Tools sind Konsolenanwendungen, die über NuGet-Pakete installiert und über die Eingabeaufforderung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="e8eb9-144">Sie können Tools selbst schreiben oder Drittanbietertools installieren.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="e8eb9-145">Tools werden auch als globale Tools, Toolpfadtools und lokale Tools bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="e8eb9-146">Weitere Informationen finden Sie unter [Übersicht über .NET Core-Tools](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e8eb9-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="e8eb9-147">Befehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="e8eb9-147">Command structure</span></span>

<span data-ttu-id="e8eb9-148">Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options).</span><span class="sxs-lookup"><span data-stu-id="e8eb9-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="e8eb9-149">Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e8eb9-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="e8eb9-150">Treiber</span><span class="sxs-lookup"><span data-stu-id="e8eb9-150">Driver</span></span>

<span data-ttu-id="e8eb9-151">Der Treiber trägt den Namen [dotnet](dotnet.md) und hat zwei Aufgaben, entweder die Ausführung einer [Framework-abhängigen Anwendung](../deploying/index.md) oder die Ausführung eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="e8eb9-152">Geben Sie zur Ausführung einer Framework-abhängigen Anwendung nach dem Treiber die Anwendung an, z.B. `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="e8eb9-153">Führen Sie beim Ausführen des Befehls aus dem Ordner, in dem sich die DLL der Anwendung befindet, einfach `dotnet my_app.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="e8eb9-154">Wenn Sie eine bestimmte Version der .NET Core-Runtime verwenden möchten, verwenden Sie die `--fx-version <VERSION>`-Option (weitere Informationen dazu finden Sie in der [Referenz zum dotnet-Befehl](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="e8eb9-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="e8eb9-155">Wenn Sie einen Befehl an den Treiber geben, startet `dotnet.exe` den Ausführungsprozess des CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="e8eb9-156">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8eb9-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="e8eb9-157">Zunächst bestimmt der Treiber die zu verwendende SDK-Version.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="e8eb9-158">Wenn keine [global.json](global-json.md)-Datei vorhanden ist, wird die neueste Version des verfügbaren SDK verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-158">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="e8eb9-159">Dabei handelt es sich entweder um eine Vorschauversion oder eine stabile Version, je nachdem, welche Version sich aktuell auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="e8eb9-160">Sobald die SDK-Version bestimmt ist, wird der Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="e8eb9-161">Befehl</span><span class="sxs-lookup"><span data-stu-id="e8eb9-161">Command</span></span>

<span data-ttu-id="e8eb9-162">Über den Befehl wird eine Aktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-162">The command performs an action.</span></span> <span data-ttu-id="e8eb9-163">Beispielsweise erstellt der Befehl `dotnet build` Code und</span><span class="sxs-lookup"><span data-stu-id="e8eb9-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="e8eb9-164">der Befehl `dotnet publish` veröffentlicht Code.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="e8eb9-165">Die Befehle werden mit einer `dotnet {command}`-Konvention als Konsolenanwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="e8eb9-166">Argumente</span><span class="sxs-lookup"><span data-stu-id="e8eb9-166">Arguments</span></span>

<span data-ttu-id="e8eb9-167">Die Argumente, die Sie in der Befehlszeile übergeben, sind die Argumente für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="e8eb9-168">Wenn Sie z.B. `dotnet publish my_app.csproj` ausführen, gibt das `my_app.csproj`-Argument das zu veröffentlichende Projekt an und wird an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="e8eb9-169">Optionen</span><span class="sxs-lookup"><span data-stu-id="e8eb9-169">Options</span></span>

<span data-ttu-id="e8eb9-170">Die Optionen, die Sie in der Befehlszeile übergeben, sind die Optionen für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="e8eb9-171">Wenn Sie z.B. `dotnet publish --output /build_output` ausführen, werden die `--output`-Option und ihr Wert an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="e8eb9-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8eb9-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8eb9-172">See also</span></span>

- [<span data-ttu-id="e8eb9-173">GitHub-Repository „dotnet/sdk“</span><span class="sxs-lookup"><span data-stu-id="e8eb9-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="e8eb9-174">.NET Core installation guide (.NET Core-Installationshandbuch)</span><span class="sxs-lookup"><span data-stu-id="e8eb9-174">.NET Core installation guide</span></span>](../install/sdk.md)
