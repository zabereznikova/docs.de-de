---
title: Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)
description: Dies ist ein Überblick über die Tools und Funktionen der .NET Core-Befehlszeilenschnittstelle (Command-Line Interface, CLI).
ms.date: 08/14/2017
ms.openlocfilehash: f19dcb19fb9d0203b3d3795c3fdc0b026c4c60e3
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163214"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="84f45-103">Tools für die .NET Core-Befehlszeilenschnittstelle (command-line interface, CLI)</span><span class="sxs-lookup"><span data-stu-id="84f45-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="84f45-104">Die .NET Core-Befehlszeilenschnittstelle (CLI) ist eine plattformübergreifende Toolkette zur Entwicklung von .NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="84f45-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="84f45-105">Die CLI ist eine Grundlage, auf der Tools höherer Ebene wie z. B. integrierte Entwicklungsumgebungen (Integrated Development Environments, IDEs), Editoren und Buildorchestratoren aufbauen können.</span><span class="sxs-lookup"><span data-stu-id="84f45-105">The CLI is a foundation upon which higher-level tools, such as integrated development environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="84f45-106">Installation</span><span class="sxs-lookup"><span data-stu-id="84f45-106">Installation</span></span>

<span data-ttu-id="84f45-107">Verwenden Sie entweder die nativen Installer oder die Installations-Shellskripts:</span><span class="sxs-lookup"><span data-stu-id="84f45-107">Either use the native installers or use the installation shell scripts:</span></span>

- <span data-ttu-id="84f45-108">Die nativen Installer werden vor allem auf Entwicklercomputern verwendet und verwenden den nativen Installationsmechanismus der jeweiligen unterstützten Plattform, z.B. DEB-Pakete unter Ubuntu oder MSI-Bündel unter Windows.</span><span class="sxs-lookup"><span data-stu-id="84f45-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="84f45-109">Diese Installer installieren und konfigurieren die Umgebung für sofortige Verwendung durch den Entwickler, erfordern jedoch Administratorrechte auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="84f45-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="84f45-110">Die Installationsanweisungen finden Sie im [.NET Core-Installationshandbuch](https://aka.ms/dotnetcoregs).</span><span class="sxs-lookup"><span data-stu-id="84f45-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
- <span data-ttu-id="84f45-111">Shellskripts werden hauptsächlich für die Einrichtung von Buildservern verwendet, oder wenn Sie die Tools ohne Administratorrechte installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="84f45-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="84f45-112">Installationsskripts installieren keine erforderlichen Komponenten auf dem Computer, diese müssen manuell installiert werden.</span><span class="sxs-lookup"><span data-stu-id="84f45-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="84f45-113">Weitere Informationen finden Sie unter [install script reference (Referenz zu Installationsskripts)](dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="84f45-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="84f45-114">Informationen zum Einrichten der CLI auf dem Buildserver der fortlaufenden Integration (Continuous Integration, CI) finden Sie unter [Verwenden des .NET Core SDK und der entsprechenden Tools in Continuous Integration (CI)](using-ci-with-cli.md).</span><span class="sxs-lookup"><span data-stu-id="84f45-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="84f45-115">Standardmäßig installiert die CLI in paralleler Ausführung (side-by-side, SxS), sodass mehrere Versionen der CLI-Tools auf einem einzelnen Computer gleichzeitig vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="84f45-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="84f45-116">Wie bestimmt wird, welche Version auf einem Computer verwendet wird, auf dem mehrere Versionen installiert sind, wird im Abschnitt [Treiber](#driver) ausführlicher erklärt.</span><span class="sxs-lookup"><span data-stu-id="84f45-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="84f45-117">CLI-Befehle</span><span class="sxs-lookup"><span data-stu-id="84f45-117">CLI commands</span></span>

<span data-ttu-id="84f45-118">Die folgenden Befehle werden standardmäßig erstellt:</span><span class="sxs-lookup"><span data-stu-id="84f45-118">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="84f45-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="84f45-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="84f45-120">**Grundlegende Befehle**</span><span class="sxs-lookup"><span data-stu-id="84f45-120">**Basic commands**</span></span>

- [<span data-ttu-id="84f45-121">new</span><span class="sxs-lookup"><span data-stu-id="84f45-121">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="84f45-122">restore</span><span class="sxs-lookup"><span data-stu-id="84f45-122">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="84f45-123">build</span><span class="sxs-lookup"><span data-stu-id="84f45-123">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="84f45-124">publish</span><span class="sxs-lookup"><span data-stu-id="84f45-124">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="84f45-125">run</span><span class="sxs-lookup"><span data-stu-id="84f45-125">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="84f45-126">test</span><span class="sxs-lookup"><span data-stu-id="84f45-126">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="84f45-127">vstest</span><span class="sxs-lookup"><span data-stu-id="84f45-127">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="84f45-128">pack</span><span class="sxs-lookup"><span data-stu-id="84f45-128">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="84f45-129">migrate</span><span class="sxs-lookup"><span data-stu-id="84f45-129">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="84f45-130">clean</span><span class="sxs-lookup"><span data-stu-id="84f45-130">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="84f45-131">sln</span><span class="sxs-lookup"><span data-stu-id="84f45-131">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="84f45-132">help</span><span class="sxs-lookup"><span data-stu-id="84f45-132">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="84f45-133">store</span><span class="sxs-lookup"><span data-stu-id="84f45-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="84f45-134">**Befehle zur Projektänderung**</span><span class="sxs-lookup"><span data-stu-id="84f45-134">**Project modification commands**</span></span>

- [<span data-ttu-id="84f45-135">add package</span><span class="sxs-lookup"><span data-stu-id="84f45-135">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="84f45-136">add reference</span><span class="sxs-lookup"><span data-stu-id="84f45-136">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="84f45-137">remove package</span><span class="sxs-lookup"><span data-stu-id="84f45-137">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="84f45-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="84f45-138">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="84f45-139">list reference</span><span class="sxs-lookup"><span data-stu-id="84f45-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="84f45-140">**Erweiterte Befehle**</span><span class="sxs-lookup"><span data-stu-id="84f45-140">**Advanced commands**</span></span>

- [<span data-ttu-id="84f45-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="84f45-141">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="84f45-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="84f45-142">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="84f45-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="84f45-143">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="84f45-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="84f45-144">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="84f45-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="84f45-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="84f45-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="84f45-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="84f45-147">**Grundlegende Befehle**</span><span class="sxs-lookup"><span data-stu-id="84f45-147">**Basic commands**</span></span>

- [<span data-ttu-id="84f45-148">new</span><span class="sxs-lookup"><span data-stu-id="84f45-148">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="84f45-149">restore</span><span class="sxs-lookup"><span data-stu-id="84f45-149">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="84f45-150">build</span><span class="sxs-lookup"><span data-stu-id="84f45-150">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="84f45-151">publish</span><span class="sxs-lookup"><span data-stu-id="84f45-151">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="84f45-152">run</span><span class="sxs-lookup"><span data-stu-id="84f45-152">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="84f45-153">test</span><span class="sxs-lookup"><span data-stu-id="84f45-153">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="84f45-154">vstest</span><span class="sxs-lookup"><span data-stu-id="84f45-154">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="84f45-155">pack</span><span class="sxs-lookup"><span data-stu-id="84f45-155">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="84f45-156">migrate</span><span class="sxs-lookup"><span data-stu-id="84f45-156">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="84f45-157">clean</span><span class="sxs-lookup"><span data-stu-id="84f45-157">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="84f45-158">sln</span><span class="sxs-lookup"><span data-stu-id="84f45-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="84f45-159">**Befehle zur Projektänderung**</span><span class="sxs-lookup"><span data-stu-id="84f45-159">**Project modification commands**</span></span>

- [<span data-ttu-id="84f45-160">add package</span><span class="sxs-lookup"><span data-stu-id="84f45-160">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="84f45-161">add reference</span><span class="sxs-lookup"><span data-stu-id="84f45-161">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="84f45-162">remove package</span><span class="sxs-lookup"><span data-stu-id="84f45-162">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="84f45-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="84f45-163">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="84f45-164">list reference</span><span class="sxs-lookup"><span data-stu-id="84f45-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="84f45-165">**Erweiterte Befehle**</span><span class="sxs-lookup"><span data-stu-id="84f45-165">**Advanced commands**</span></span>

- [<span data-ttu-id="84f45-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="84f45-166">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="84f45-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="84f45-167">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="84f45-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="84f45-168">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="84f45-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="84f45-169">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="84f45-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="84f45-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="84f45-171">Die CLI übernimmt ein Erweiterbarkeitsmodell, mit dem Sie zusätzliche Tools für Ihre Projekte angeben können.</span><span class="sxs-lookup"><span data-stu-id="84f45-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="84f45-172">Weitere Informationen finden Sie im Thema [.NET Core CLI extensibility model (.NET Core-CLI-Erweiterbarkeitsmodell)](extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="84f45-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="84f45-173">Befehlsstruktur</span><span class="sxs-lookup"><span data-stu-id="84f45-173">Command structure</span></span>

<span data-ttu-id="84f45-174">Die CLI-Befehlsstruktur besteht aus dem [Treiber („dotnet“)](#driver), dem [Befehl](#command) und möglicherweise aus [Argumenten](#arguments) und [Optionen](#options).</span><span class="sxs-lookup"><span data-stu-id="84f45-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="84f45-175">Sie sehen dieses Muster in den meisten CLI-Vorgängen wie z.B. beim Erstellen einer neuen Konsolenanwendung und deren Ausführung von der Befehlszeile aus, wie die folgenden Befehle zeigen, wenn sie aus einem Verzeichnis mit dem Namen *my_app* ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="84f45-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="84f45-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="84f45-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="84f45-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="84f45-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="84f45-178">Treiber</span><span class="sxs-lookup"><span data-stu-id="84f45-178">Driver</span></span>

<span data-ttu-id="84f45-179">Der Treiber trägt den Namen [dotnet](dotnet.md) und hat zwei Aufgaben, entweder die Ausführung einer [Framework-abhängigen Anwendung](../deploying/index.md) oder die Ausführung eines Befehls.</span><span class="sxs-lookup"><span data-stu-id="84f45-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="84f45-180">Geben Sie zur Ausführung einer Framework-abhängigen Anwendung nach dem Treiber die Anwendung an, z.B. `dotnet /path/to/my_app.dll`.</span><span class="sxs-lookup"><span data-stu-id="84f45-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="84f45-181">Führen Sie beim Ausführen des Befehls aus dem Ordner, in dem sich die DLL der Anwendung befindet, einfach `dotnet my_app.dll` aus.</span><span class="sxs-lookup"><span data-stu-id="84f45-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="84f45-182">Wenn Sie eine bestimmte Version der .NET Core-Runtime verwenden möchten, verwenden Sie die `--fx-version <VERSION>`-Option (weitere Informationen dazu finden Sie in der [Referenz zum dotnet-Befehl](dotnet.md)).</span><span class="sxs-lookup"><span data-stu-id="84f45-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="84f45-183">Wenn Sie einen Befehl an den Treiber geben, startet `dotnet.exe` den Ausführungsprozess des CLI-Befehls.</span><span class="sxs-lookup"><span data-stu-id="84f45-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="84f45-184">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="84f45-184">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="84f45-185">Zunächst bestimmt der Treiber die zu verwendende SDK-Version.</span><span class="sxs-lookup"><span data-stu-id="84f45-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="84f45-186">Wenn keine [„global.json“](global-json.md)-Datei vorhanden ist, wird die neueste Version des verfügbaren SDK verwendet.</span><span class="sxs-lookup"><span data-stu-id="84f45-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="84f45-187">Dabei handelt es sich entweder um eine Vorschauversion oder eine stabile Version, je nachdem, welche Version sich aktuell auf dem Computer befindet.</span><span class="sxs-lookup"><span data-stu-id="84f45-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="84f45-188">Sobald die SDK-Version bestimmt ist, wird der Befehl ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="84f45-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="84f45-189">Befehl</span><span class="sxs-lookup"><span data-stu-id="84f45-189">Command</span></span>

<span data-ttu-id="84f45-190">Über den Befehl wird eine Aktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="84f45-190">The command performs an action.</span></span> <span data-ttu-id="84f45-191">Beispielsweise erstellt der Befehl `dotnet build` Code und</span><span class="sxs-lookup"><span data-stu-id="84f45-191">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="84f45-192">der Befehl `dotnet publish` veröffentlicht Code.</span><span class="sxs-lookup"><span data-stu-id="84f45-192">`dotnet publish` publishes code.</span></span> <span data-ttu-id="84f45-193">Die Befehle werden mit einer `dotnet {command}`-Konvention als Konsolenanwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="84f45-193">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="84f45-194">Argumente</span><span class="sxs-lookup"><span data-stu-id="84f45-194">Arguments</span></span>

<span data-ttu-id="84f45-195">Die Argumente, die Sie in der Befehlszeile übergeben, sind die Argumente für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="84f45-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="84f45-196">Wenn Sie z.B. `dotnet publish my_app.csproj` ausführen, gibt das `my_app.csproj`-Argument das zu veröffentlichende Projekt an und wird an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="84f45-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="84f45-197">Optionen</span><span class="sxs-lookup"><span data-stu-id="84f45-197">Options</span></span>

<span data-ttu-id="84f45-198">Die Optionen, die Sie in der Befehlszeile übergeben, sind die Optionen für den aufgerufenen Befehl.</span><span class="sxs-lookup"><span data-stu-id="84f45-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="84f45-199">Wenn Sie z.B. `dotnet publish --output /build_output` ausführen, werden die `--output`-Option und ihr Wert an den `publish`-Befehl übergeben.</span><span class="sxs-lookup"><span data-stu-id="84f45-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="84f45-200">Migration von project.json</span><span class="sxs-lookup"><span data-stu-id="84f45-200">Migration from project.json</span></span>

<span data-ttu-id="84f45-201">Wenn Sie Preview 2-Tools verwendet haben, um *project.json*-basierte Projekte zu erzeugen, finden Sie im Thema [dotnet-migrate](dotnet-migrate.md) Informationen zur Migration eines Projekts zu MSBuild/ *.csproj* für die Verwendung mit Versionstools.</span><span class="sxs-lookup"><span data-stu-id="84f45-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="84f45-202">Aktualisieren Sie für .NET Core-Projekte, die vor der Veröffentlichung der Vorschau 2-Tools erstellt wurden, das Projekt entweder manuell anhand der Anweisungen in [Migrieren von DNX zur .NET Core-CLI (project.json)](../migration/from-dnx.md) und verwenden dann `dotnet migrate`, oder führen Sie direkt ein Upgrade für die Projekte durch.</span><span class="sxs-lookup"><span data-stu-id="84f45-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="84f45-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84f45-203">See also</span></span>

- [<span data-ttu-id="84f45-204">dotnet/CLI GitHub Repository (dotnet/CLI-GitHub-Repository)</span><span class="sxs-lookup"><span data-stu-id="84f45-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="84f45-205">.NET Core installation guide (.NET Core-Installationshandbuch)</span><span class="sxs-lookup"><span data-stu-id="84f45-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
