---
title: .NET Core CLI
titleSuffix: ''
description: Eine Übersicht über die .NET Core-CLI und ihre Features.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920482"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="a2641-103">Übersicht über die .NET Core-CLI</span><span class="sxs-lookup"><span data-stu-id="a2641-103">.NET Core CLI overview</span></span>

<span data-ttu-id="a2641-104">Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine plattformübergreifende Toolkette zum Entwicklung, Erstellen, Ausführen und Veröffentlichen von .NET Core-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="a2641-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="a2641-105">Die .NET Core-CLI ist im [.NET Core SDK](../sdk.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="a2641-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="a2641-106">Informationen zum Installieren des .NET Core SDK finden Sie unter [Installieren des .NET Core SDK](../install/sdk.md).</span><span class="sxs-lookup"><span data-stu-id="a2641-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="a2641-107">CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="a2641-107">CLI commands</span></span>

<span data-ttu-id="a2641-108">Die folgenden Befehle werden standardmäßig erstellt:</span><span class="sxs-lookup"><span data-stu-id="a2641-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="a2641-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a2641-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="a2641-110">**Grundlegende Befehle**</span><span class="sxs-lookup"><span data-stu-id="a2641-110">**Basic commands**</span></span>

- [<span data-ttu-id="a2641-111">Neu</span><span class="sxs-lookup"><span data-stu-id="a2641-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="a2641-112">restore</span><span class="sxs-lookup"><span data-stu-id="a2641-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="a2641-113">build</span><span class="sxs-lookup"><span data-stu-id="a2641-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="a2641-114">publish</span><span class="sxs-lookup"><span data-stu-id="a2641-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="a2641-115">run</span><span class="sxs-lookup"><span data-stu-id="a2641-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="a2641-116">test</span><span class="sxs-lookup"><span data-stu-id="a2641-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="a2641-117">vstest</span><span class="sxs-lookup"><span data-stu-id="a2641-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="a2641-118">pack</span><span class="sxs-lookup"><span data-stu-id="a2641-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="a2641-119">Migrieren</span><span class="sxs-lookup"><span data-stu-id="a2641-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="a2641-120">clean</span><span class="sxs-lookup"><span data-stu-id="a2641-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="a2641-121">sln</span><span class="sxs-lookup"><span data-stu-id="a2641-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="a2641-122">help</span><span class="sxs-lookup"><span data-stu-id="a2641-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="a2641-123">store</span><span class="sxs-lookup"><span data-stu-id="a2641-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="a2641-124">**Befehle zur Projektänderung**</span><span class="sxs-lookup"><span data-stu-id="a2641-124">**Project modification commands**</span></span>

- [<span data-ttu-id="a2641-125">add package</span><span class="sxs-lookup"><span data-stu-id="a2641-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="a2641-126">add reference</span><span class="sxs-lookup"><span data-stu-id="a2641-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="a2641-127">remove package</span><span class="sxs-lookup"><span data-stu-id="a2641-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="a2641-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="a2641-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="a2641-129">list reference</span><span class="sxs-lookup"><span data-stu-id="a2641-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="a2641-130">**Erweiterte Befehle**</span><span class="sxs-lookup"><span data-stu-id="a2641-130">**Advanced commands**</span></span>

- [<span data-ttu-id="a2641-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="a2641-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="a2641-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="a2641-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="a2641-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="a2641-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="a2641-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="a2641-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="a2641-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="a2641-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a2641-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a2641-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="a2641-137">**Grundlegende Befehle**</span><span class="sxs-lookup"><span data-stu-id="a2641-137">**Basic commands**</span></span>

- [<span data-ttu-id="a2641-138">Neu</span><span class="sxs-lookup"><span data-stu-id="a2641-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="a2641-139">restore</span><span class="sxs-lookup"><span data-stu-id="a2641-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="a2641-140">build</span><span class="sxs-lookup"><span data-stu-id="a2641-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="a2641-141">publish</span><span class="sxs-lookup"><span data-stu-id="a2641-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="a2641-142">run</span><span class="sxs-lookup"><span data-stu-id="a2641-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="a2641-143">test</span><span class="sxs-lookup"><span data-stu-id="a2641-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="a2641-144">vstest</span><span class="sxs-lookup"><span data-stu-id="a2641-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="a2641-145">pack</span><span class="sxs-lookup"><span data-stu-id="a2641-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="a2641-146">Migrieren</span><span class="sxs-lookup"><span data-stu-id="a2641-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="a2641-147">clean</span><span class="sxs-lookup"><span data-stu-id="a2641-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="a2641-148">sln</span><span class="sxs-lookup"><span data-stu-id="a2641-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="a2641-149">**Befehle zur Projektänderung**</span><span class="sxs-lookup"><span data-stu-id="a2641-149">**Project modification commands**</span></span>

- [<span data-ttu-id="a2641-150">add package</span><span class="sxs-lookup"><span data-stu-id="a2641-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="a2641-151">add reference</span><span class="sxs-lookup"><span data-stu-id="a2641-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="a2641-152">remove package</span><span class="sxs-lookup"><span data-stu-id="a2641-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="a2641-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="a2641-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="a2641-154">list reference</span><span class="sxs-lookup"><span data-stu-id="a2641-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="a2641-155">**Erweiterte Befehle**</span><span class="sxs-lookup"><span data-stu-id="a2641-155">**Advanced commands**</span></span>

- [<span data-ttu-id="a2641-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="a2641-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="a2641-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="a2641-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="a2641-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="a2641-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="a2641-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="a2641-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="a2641-160">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="a2641-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="a2641-161">Die CLI übernimmt ein Erweiterbarkeitsmodell, mit dem Sie zusätzliche Tools für Ihre Projekte angeben können.</span><span class="sxs-lookup"><span data-stu-id="a2641-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="a2641-162">Weitere Informationen finden Sie im Thema [.NET Core CLI extensibility model (.NET Core-CLI-Erweiterbarkeitsmodell)](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="a2641-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="a2641-163">Befehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="a2641-163">Command structure</span></span>

<span data-ttu-id="a2641-164">Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options).</span><span class="sxs-lookup"><span data-stu-id="a2641-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="a2641-165">Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a2641-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="a2641-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="a2641-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a2641-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a2641-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="a2641-168">Treiber</span><span class="sxs-lookup"><span data-stu-id="a2641-168">Driver</span></span>

<span data-ttu-id="a2641-169">Der Treiber trägt den Namen [dotnet](dotnet.md) und hat zwei Aufgaben, entweder die Ausführung einer [Framework-abhängigen Anwendung](../deploying/index.md) oder die Ausführung eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="a2641-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="a2641-170">Geben Sie zur Ausführung einer Framework-abhängigen Anwendung nach dem Treiber die Anwendung an, z.B. `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="a2641-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="a2641-171">Führen Sie beim Ausführen des Befehls aus dem Ordner, in dem sich die DLL der Anwendung befindet, einfach `dotnet my_app.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="a2641-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="a2641-172">Wenn Sie eine bestimmte Version der .NET Core-Runtime verwenden möchten, verwenden Sie die `--fx-version <VERSION>`-Option (weitere Informationen dazu finden Sie in der [Referenz zum dotnet-Befehl](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="a2641-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="a2641-173">Wenn Sie einen Befehl an den Treiber geben, startet `dotnet.exe` den Ausführungsprozess des CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="a2641-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="a2641-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a2641-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="a2641-175">Zunächst bestimmt der Treiber die zu verwendende SDK-Version.</span><span class="sxs-lookup"><span data-stu-id="a2641-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="a2641-176">Wenn keine [„global.json“](global-json.md)-Datei vorhanden ist, wird die neueste Version des verfügbaren SDK verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2641-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="a2641-177">Dabei handelt es sich entweder um eine Vorschauversion oder eine stabile Version, je nachdem, welche Version sich aktuell auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="a2641-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="a2641-178">Sobald die SDK-Version bestimmt ist, wird der Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a2641-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="a2641-179">Get-Help</span><span class="sxs-lookup"><span data-stu-id="a2641-179">Command</span></span>

<span data-ttu-id="a2641-180">Über den Befehl wird eine Aktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a2641-180">The command performs an action.</span></span> <span data-ttu-id="a2641-181">Beispielsweise erstellt der Befehl `dotnet build` Code und</span><span class="sxs-lookup"><span data-stu-id="a2641-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="a2641-182">der Befehl `dotnet publish` veröffentlicht Code.</span><span class="sxs-lookup"><span data-stu-id="a2641-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="a2641-183">Die Befehle werden mit einer `dotnet {command}`-Konvention als Konsolenanwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="a2641-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="a2641-184">Argumente</span><span class="sxs-lookup"><span data-stu-id="a2641-184">Arguments</span></span>

<span data-ttu-id="a2641-185">Die Argumente, die Sie in der Befehlszeile übergeben, sind die Argumente für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="a2641-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="a2641-186">Wenn Sie z.B. `dotnet publish my_app.csproj` ausführen, gibt das `my_app.csproj`-Argument das zu veröffentlichende Projekt an und wird an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="a2641-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="a2641-187">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a2641-187">Options</span></span>

<span data-ttu-id="a2641-188">Die Optionen, die Sie in der Befehlszeile übergeben, sind die Optionen für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="a2641-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="a2641-189">Wenn Sie z.B. `dotnet publish --output /build_output` ausführen, werden die `--output`-Option und ihr Wert an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="a2641-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="a2641-190">Migration von project.json</span><span class="sxs-lookup"><span data-stu-id="a2641-190">Migration from project.json</span></span>

<span data-ttu-id="a2641-191">Wenn Sie Preview 2-Tools verwendet haben, um *project.json*-basierte Projekte zu erzeugen, finden Sie im Thema [dotnet-migrate](dotnet-migrate.md) Informationen zur Migration eines Projekts zu MSBuild/*.csproj* für die Verwendung mit Versionstools.</span><span class="sxs-lookup"><span data-stu-id="a2641-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="a2641-192">Aktualisieren Sie für .NET Core-Projekte, die vor der Veröffentlichung der Vorschau 2-Tools erstellt wurden, das Projekt entweder manuell anhand der Anweisungen in [Migrieren von DNX zur .NET Core-CLI (project.json)](../migration/from-dnx.md) und verwenden dann `dotnet migrate`, oder führen Sie direkt ein Upgrade für die Projekte durch.</span><span class="sxs-lookup"><span data-stu-id="a2641-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2641-193">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a2641-193">See also</span></span>

- [<span data-ttu-id="a2641-194">GitHub-Repository „dotnet/sdk“</span><span class="sxs-lookup"><span data-stu-id="a2641-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="a2641-195">.NET Core installation guide (.NET Core-Installationshandbuch)</span><span class="sxs-lookup"><span data-stu-id="a2641-195">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
