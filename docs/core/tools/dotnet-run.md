---
title: dotnet run-Befehl – .NET Core-CLI
description: Der dotnet run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: f560e6f795f00488818647a4b5c711dcf9d59dcd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45687646"
---
# <a name="dotnet-run"></a><span data-ttu-id="8142d-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="8142d-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8142d-104">name</span><span class="sxs-lookup"><span data-stu-id="8142d-104">Name</span></span>

<span data-ttu-id="8142d-105">`dotnet run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.</span><span class="sxs-lookup"><span data-stu-id="8142d-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8142d-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8142d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8142d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8142d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8142d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8142d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8142d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8142d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="8142d-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="8142d-110">Description</span></span>

<span data-ttu-id="8142d-111">Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="8142d-111">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="8142d-112">Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="8142d-112">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="8142d-113">Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8142d-113">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="8142d-114">Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.</span><span class="sxs-lookup"><span data-stu-id="8142d-114">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="8142d-115">Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8142d-115">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="8142d-116">Angenommen, Sie haben eine `netcoreapp2.1`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp2.1` platziert.</span><span class="sxs-lookup"><span data-stu-id="8142d-116">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="8142d-117">Dateien werden bei Bedarf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="8142d-117">Files are overwritten as needed.</span></span> <span data-ttu-id="8142d-118">Temporäre Dateien befinden sich im `obj`-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8142d-118">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="8142d-119">Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8142d-119">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="8142d-120">Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="8142d-120">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="8142d-121">Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="8142d-121">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="8142d-122">Zum Ausführen von `myapp.dll` verwenden Sie z.B.:</span><span class="sxs-lookup"><span data-stu-id="8142d-122">For example, to run `myapp.dll`, use:</span></span>

```console
dotnet myapp.dll
```

<span data-ttu-id="8142d-123">Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).</span><span class="sxs-lookup"><span data-stu-id="8142d-123">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="8142d-124">Der Befehl `dotnet run` löst die Abhängigkeiten der Anwendungen außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8142d-124">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="8142d-125">Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8142d-125">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="8142d-126">Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="8142d-126">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="8142d-127">Optionen</span><span class="sxs-lookup"><span data-stu-id="8142d-127">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8142d-128">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8142d-128">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="8142d-129">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="8142d-129">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8142d-130">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="8142d-130">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8142d-131">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="8142d-131">Defines the build configuration.</span></span> <span data-ttu-id="8142d-132">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8142d-132">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8142d-133">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="8142d-133">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8142d-134">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8142d-134">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="8142d-135">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8142d-135">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8142d-136">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8142d-136">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="8142d-137">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8142d-137">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="8142d-138">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="8142d-138">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="8142d-139">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="8142d-139">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="8142d-140">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="8142d-140">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="8142d-141">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="8142d-141">Doesn't build the project before running.</span></span> <span data-ttu-id="8142d-142">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8142d-142">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="8142d-143">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="8142d-143">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="8142d-144">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8142d-144">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="8142d-145">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8142d-145">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="8142d-146">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="8142d-146">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="8142d-147">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="8142d-147">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="8142d-148">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="8142d-148">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="8142d-149">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8142d-149">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="8142d-150">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="8142d-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8142d-151">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8142d-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8142d-152">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8142d-152">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="8142d-153">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="8142d-153">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8142d-154">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="8142d-154">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8142d-155">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="8142d-155">Defines the build configuration.</span></span> <span data-ttu-id="8142d-156">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8142d-156">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8142d-157">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="8142d-157">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8142d-158">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8142d-158">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="8142d-159">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8142d-159">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8142d-160">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8142d-160">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="8142d-161">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8142d-161">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="8142d-162">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="8142d-162">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="8142d-163">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="8142d-163">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="8142d-164">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="8142d-164">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="8142d-165">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="8142d-165">Doesn't build the project before running.</span></span> <span data-ttu-id="8142d-166">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8142d-166">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="8142d-167">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="8142d-167">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="8142d-168">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8142d-168">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="8142d-169">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8142d-169">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="8142d-170">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="8142d-170">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="8142d-171">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="8142d-171">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="8142d-172">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="8142d-172">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="8142d-173">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8142d-173">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8142d-174">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8142d-174">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="8142d-175">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="8142d-175">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="8142d-176">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="8142d-176">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="8142d-177">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="8142d-177">Defines the build configuration.</span></span> <span data-ttu-id="8142d-178">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="8142d-178">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="8142d-179">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="8142d-179">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="8142d-180">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8142d-180">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="8142d-181">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8142d-181">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="8142d-182">Gibt den Pfad und Namen der Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="8142d-182">Specifies the path and name of the project file.</span></span> <span data-ttu-id="8142d-183">(Siehe HINWEIS.) Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="8142d-183">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="8142d-184">Verwenden Sie den Pfad und Namen der Projektdatei mit der `-p|--project`-Option.</span><span class="sxs-lookup"><span data-stu-id="8142d-184">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="8142d-185">Eine Regression in der CLI verhindert, dass ein Pfad mit dem .NET Core SDK 1.x bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8142d-185">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="8142d-186">Weitere Informationen zu diesem Problem finden Sie unter [dotnet run -p, can not start a project (dotnet/cli #5992) (dotnet run -p, ein Projekt kann nicht gestartet werden (dotnet/cli #5992))](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="8142d-186">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="8142d-187">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8142d-187">Examples</span></span>

<span data-ttu-id="8142d-188">Führt das Projekt im aktuellen Verzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="8142d-188">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="8142d-189">Führt das angegebene Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="8142d-189">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="8142d-190">Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da die leere Option `--` verwendet wird):</span><span class="sxs-lookup"><span data-stu-id="8142d-190">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="8142d-191">Stellt Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis wieder her, wobei nur eine minimale Ausgabe angezeigt wird, und führt dann das Projekt aus (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="8142d-191">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`