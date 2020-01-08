---
title: Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)
description: Dies ist ein Überblick über die Tools und Funktionen der .NET Core-Befehlszeilenschnittstelle (Command-Line Interface, CLI).
ms.date: 08/14/2017
ms.openlocfilehash: b3bffb47ff973bd0da90e3f943e817756e563138
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714147"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="23fff-103">Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)</span><span class="sxs-lookup"><span data-stu-id="23fff-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="23fff-104">Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine neue plattformübergreifende Toolkette zur Entwicklung von .NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="23fff-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="23fff-105">Die CLI ist eine Grundlage, auf der Tools höherer Ebene wie z.B. integrierte Entwicklungsumgebungen (Integrated Development Environments, IDEs), Editoren und Build-Koordinatoren aufbauen können.</span><span class="sxs-lookup"><span data-stu-id="23fff-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="23fff-106">Installation</span><span class="sxs-lookup"><span data-stu-id="23fff-106">Installation</span></span>

<span data-ttu-id="23fff-107">Verwenden Sie entweder die nativen Installer oder die Installations-Shellskripts:</span><span class="sxs-lookup"><span data-stu-id="23fff-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="23fff-108">Die nativen Installer werden vor allem auf Entwicklercomputern verwendet und verwenden den nativen Installationsmechanismus der jeweiligen unterstützten Plattform, z.B. DEB-Pakete unter Ubuntu oder MSI-Bündel unter Windows.</span><span class="sxs-lookup"><span data-stu-id="23fff-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="23fff-109">Diese Installer installieren und konfigurieren die Umgebung für sofortige Verwendung durch den Entwickler, erfordern jedoch Administratorrechte auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="23fff-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="23fff-110">Die Installationsanweisungen finden Sie im [.NET Core-Installationshandbuch](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="23fff-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="23fff-111">Shellskripts werden hauptsächlich für die Einrichtung von Buildservern verwendet, oder wenn Sie die Tools ohne Administratorrechte installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="23fff-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="23fff-112">Installationsskripts installieren keine erforderlichen Komponenten auf dem Computer, diese müssen manuell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="23fff-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="23fff-113">Weitere Informationen finden Sie unter [install script reference (Referenz zu Installationsskripts)](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="23fff-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="23fff-114">Informationen zum Einrichten der CLI auf dem Buildserver der fortlaufenden Integration (Continuous Integration, CI) finden Sie unter [Verwenden des .NET Core SDK und der entsprechenden Tools in Continuous Integration (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="23fff-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="23fff-115">Standardmäßig installiert die CLI in paralleler Ausführung (side-by-side, SxS), sodass mehrere Versionen der CLI-Tools auf einem einzelnen Computer gleichzeitig vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="23fff-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="23fff-116">Wie bestimmt wird, welche Version auf einem Computer verwendet wird, auf dem mehrere Versionen installiert sind, wird im Abschnitt [Treiber](#driver) ausführlicher erklärt.</span><span class="sxs-lookup"><span data-stu-id="23fff-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="23fff-117">CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="23fff-117">CLI commands</span></span>

<span data-ttu-id="23fff-118">Die folgenden Befehle werden standardmäßig erstellt:</span><span class="sxs-lookup"><span data-stu-id="23fff-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="23fff-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="23fff-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="23fff-120">**Grundlegende Befehle**</span><span class="sxs-lookup"><span data-stu-id="23fff-120">**Basic commands**</span></span>

- [<span data-ttu-id="23fff-121">new</span><span class="sxs-lookup"><span data-stu-id="23fff-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="23fff-122">restore</span><span class="sxs-lookup"><span data-stu-id="23fff-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="23fff-123">build</span><span class="sxs-lookup"><span data-stu-id="23fff-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="23fff-124">publish</span><span class="sxs-lookup"><span data-stu-id="23fff-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="23fff-125">run</span><span class="sxs-lookup"><span data-stu-id="23fff-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="23fff-126">test</span><span class="sxs-lookup"><span data-stu-id="23fff-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="23fff-127">vstest</span><span class="sxs-lookup"><span data-stu-id="23fff-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="23fff-128">pack</span><span class="sxs-lookup"><span data-stu-id="23fff-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="23fff-129">migrate</span><span class="sxs-lookup"><span data-stu-id="23fff-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="23fff-130">clean</span><span class="sxs-lookup"><span data-stu-id="23fff-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="23fff-131">sln</span><span class="sxs-lookup"><span data-stu-id="23fff-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="23fff-132">help</span><span class="sxs-lookup"><span data-stu-id="23fff-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="23fff-133">store</span><span class="sxs-lookup"><span data-stu-id="23fff-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="23fff-134">**Befehle zur Projektänderung**</span><span class="sxs-lookup"><span data-stu-id="23fff-134">**Project modification commands**</span></span>

- [<span data-ttu-id="23fff-135">add package</span><span class="sxs-lookup"><span data-stu-id="23fff-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="23fff-136">add reference</span><span class="sxs-lookup"><span data-stu-id="23fff-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="23fff-137">remove package</span><span class="sxs-lookup"><span data-stu-id="23fff-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="23fff-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="23fff-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="23fff-139">list reference</span><span class="sxs-lookup"><span data-stu-id="23fff-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="23fff-140">**Erweiterte Befehle**</span><span class="sxs-lookup"><span data-stu-id="23fff-140">**Advanced commands**</span></span>

- [<span data-ttu-id="23fff-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="23fff-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="23fff-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="23fff-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="23fff-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="23fff-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="23fff-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="23fff-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="23fff-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="23fff-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="23fff-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="23fff-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="23fff-147">**Grundlegende Befehle**</span><span class="sxs-lookup"><span data-stu-id="23fff-147">**Basic commands**</span></span>

- [<span data-ttu-id="23fff-148">new</span><span class="sxs-lookup"><span data-stu-id="23fff-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="23fff-149">restore</span><span class="sxs-lookup"><span data-stu-id="23fff-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="23fff-150">build</span><span class="sxs-lookup"><span data-stu-id="23fff-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="23fff-151">publish</span><span class="sxs-lookup"><span data-stu-id="23fff-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="23fff-152">run</span><span class="sxs-lookup"><span data-stu-id="23fff-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="23fff-153">test</span><span class="sxs-lookup"><span data-stu-id="23fff-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="23fff-154">vstest</span><span class="sxs-lookup"><span data-stu-id="23fff-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="23fff-155">pack</span><span class="sxs-lookup"><span data-stu-id="23fff-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="23fff-156">migrate</span><span class="sxs-lookup"><span data-stu-id="23fff-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="23fff-157">clean</span><span class="sxs-lookup"><span data-stu-id="23fff-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="23fff-158">sln</span><span class="sxs-lookup"><span data-stu-id="23fff-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="23fff-159">**Befehle zur Projektänderung**</span><span class="sxs-lookup"><span data-stu-id="23fff-159">**Project modification commands**</span></span>

- [<span data-ttu-id="23fff-160">add package</span><span class="sxs-lookup"><span data-stu-id="23fff-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="23fff-161">add reference</span><span class="sxs-lookup"><span data-stu-id="23fff-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="23fff-162">remove package</span><span class="sxs-lookup"><span data-stu-id="23fff-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="23fff-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="23fff-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="23fff-164">list reference</span><span class="sxs-lookup"><span data-stu-id="23fff-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="23fff-165">**Erweiterte Befehle**</span><span class="sxs-lookup"><span data-stu-id="23fff-165">**Advanced commands**</span></span>

- [<span data-ttu-id="23fff-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="23fff-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="23fff-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="23fff-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="23fff-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="23fff-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="23fff-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="23fff-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="23fff-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="23fff-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="23fff-171">Die CLI übernimmt ein Erweiterbarkeitsmodell, mit dem Sie zusätzliche Tools für Ihre Projekte angeben können.</span><span class="sxs-lookup"><span data-stu-id="23fff-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="23fff-172">Weitere Informationen finden Sie im Thema [.NET Core CLI extensibility model (.NET Core-CLI-Erweiterbarkeitsmodell)](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="23fff-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="23fff-173">Befehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="23fff-173">Command structure</span></span>

<span data-ttu-id="23fff-174">Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options).</span><span class="sxs-lookup"><span data-stu-id="23fff-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="23fff-175">Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="23fff-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="23fff-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="23fff-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="23fff-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="23fff-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="23fff-178">Treiber</span><span class="sxs-lookup"><span data-stu-id="23fff-178">Driver</span></span>

<span data-ttu-id="23fff-179">Der Treiber trägt den Namen [dotnet](dotnet.md) und hat zwei Aufgaben, entweder die Ausführung einer [Framework-abhängigen Anwendung](../deploying/index.md) oder die Ausführung eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="23fff-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="23fff-180">Geben Sie zur Ausführung einer Framework-abhängigen Anwendung nach dem Treiber die Anwendung an, z.B. `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="23fff-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="23fff-181">Führen Sie beim Ausführen des Befehls aus dem Ordner, in dem sich die DLL der Anwendung befindet, einfach `dotnet my_app.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="23fff-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="23fff-182">Wenn Sie eine bestimmte Version der .NET Core-Runtime verwenden möchten, verwenden Sie die `--fx-version <VERSION>`-Option (weitere Informationen dazu finden Sie in der [Referenz zum dotnet-Befehl](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="23fff-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="23fff-183">Wenn Sie einen Befehl an den Treiber geben, startet `dotnet.exe` den Ausführungsprozess des CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="23fff-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="23fff-184">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="23fff-184">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="23fff-185">Zunächst bestimmt der Treiber die zu verwendende SDK-Version.</span><span class="sxs-lookup"><span data-stu-id="23fff-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="23fff-186">Wenn keine [„global.json“](global-json.md)-Datei vorhanden ist, wird die neueste Version des verfügbaren SDK verwendet.</span><span class="sxs-lookup"><span data-stu-id="23fff-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="23fff-187">Dabei handelt es sich entweder um eine Vorschauversion oder eine stabile Version, je nachdem, welche Version sich aktuell auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="23fff-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="23fff-188">Sobald die SDK-Version bestimmt ist, wird der Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23fff-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="23fff-189">Befehl</span><span class="sxs-lookup"><span data-stu-id="23fff-189">Command</span></span>

<span data-ttu-id="23fff-190">Über den Befehl wird eine Aktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="23fff-190">The command performs an action.</span></span> <span data-ttu-id="23fff-191">Beispielsweise erstellt der Befehl `dotnet build` Code und</span><span class="sxs-lookup"><span data-stu-id="23fff-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="23fff-192">der Befehl `dotnet publish` veröffentlicht Code.</span><span class="sxs-lookup"><span data-stu-id="23fff-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="23fff-193">Die Befehle werden mit einer `dotnet {command}`-Konvention als Konsolenanwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="23fff-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="23fff-194">Argumente</span><span class="sxs-lookup"><span data-stu-id="23fff-194">Arguments</span></span>

<span data-ttu-id="23fff-195">Die Argumente, die Sie in der Befehlszeile übergeben, sind die Argumente für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="23fff-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="23fff-196">Wenn Sie z.B. `dotnet publish my_app.csproj` ausführen, gibt das `my_app.csproj`-Argument das zu veröffentlichende Projekt an und wird an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="23fff-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="23fff-197">Optionen</span><span class="sxs-lookup"><span data-stu-id="23fff-197">Options</span></span>

<span data-ttu-id="23fff-198">Die Optionen, die Sie in der Befehlszeile übergeben, sind die Optionen für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="23fff-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="23fff-199">Wenn Sie z.B. `dotnet publish --output /build_output` ausführen, werden die `--output`-Option und ihr Wert an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="23fff-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="23fff-200">Migration von project.json</span><span class="sxs-lookup"><span data-stu-id="23fff-200">Migration from project.json</span></span>

<span data-ttu-id="23fff-201">Wenn Sie Preview 2-Tools verwendet haben, um *project.json*-basierte Projekte zu erzeugen, finden Sie im Thema [dotnet-migrate](dotnet-migrate.md) Informationen zur Migration eines Projekts zu MSBuild/ *.csproj* für die Verwendung mit Versionstools.</span><span class="sxs-lookup"><span data-stu-id="23fff-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="23fff-202">Aktualisieren Sie für .NET Core-Projekte, die vor der Veröffentlichung der Vorschau 2-Tools erstellt wurden, das Projekt entweder manuell anhand der Anweisungen in [Migrieren von DNX zur .NET Core-CLI (project.json)](../migration/from-dnx.md) und verwenden dann `dotnet migrate`, oder führen Sie direkt ein Upgrade für die Projekte durch.</span><span class="sxs-lookup"><span data-stu-id="23fff-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="23fff-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23fff-203">See also</span></span>

- [<span data-ttu-id="23fff-204">dotnet/CLI GitHub Repository (dotnet/CLI-GitHub-Repository)</span><span class="sxs-lookup"><span data-stu-id="23fff-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="23fff-205">.NET Core installation guide (.NET Core-Installationshandbuch)</span><span class="sxs-lookup"><span data-stu-id="23fff-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
