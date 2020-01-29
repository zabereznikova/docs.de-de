---
title: Befehl „dotnet run“
description: Der dotnet run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode.
ms.date: 10/31/2019
ms.openlocfilehash: 5920f0d1f04204b286fdf6f51f5fd13644846390
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734107"
---
# <a name="dotnet-run"></a><span data-ttu-id="2a74a-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2a74a-103">dotnet run</span></span>

<span data-ttu-id="2a74a-104">**Dieser Artikel gilt für:** ✔️ .NET Core 1.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="2a74a-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="2a74a-105">name</span><span class="sxs-lookup"><span data-stu-id="2a74a-105">Name</span></span>

<span data-ttu-id="2a74a-106">`dotnet run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.</span><span class="sxs-lookup"><span data-stu-id="2a74a-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2a74a-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2a74a-107">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="2a74a-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2a74a-108">.NET Core 3.0</span></span>](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2a74a-109">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2a74a-109">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2a74a-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2a74a-110">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2a74a-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2a74a-111">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="2a74a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a74a-112">Description</span></span>

<span data-ttu-id="2a74a-113">Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="2a74a-113">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="2a74a-114">Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="2a74a-114">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="2a74a-115">Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2a74a-115">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="2a74a-116">Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.</span><span class="sxs-lookup"><span data-stu-id="2a74a-116">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="2a74a-117">Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-117">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="2a74a-118">Angenommen, Sie haben eine `netcoreapp2.1`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp2.1` platziert.</span><span class="sxs-lookup"><span data-stu-id="2a74a-118">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="2a74a-119">Dateien werden bei Bedarf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-119">Files are overwritten as needed.</span></span> <span data-ttu-id="2a74a-120">Temporäre Dateien befinden sich im `obj`-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2a74a-120">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="2a74a-121">Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-121">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="2a74a-122">Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="2a74a-122">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="2a74a-123">Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a74a-123">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="2a74a-124">Zum Ausführen von `myapp.dll` verwenden Sie z.B.:</span><span class="sxs-lookup"><span data-stu-id="2a74a-124">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="2a74a-125">Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).</span><span class="sxs-lookup"><span data-stu-id="2a74a-125">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="2a74a-126">Der Befehl `dotnet run` löst die Abhängigkeiten der Anwendungen außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2a74a-126">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="2a74a-127">Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2a74a-127">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="2a74a-128">Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="2a74a-128">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="2a74a-129">Optionen</span><span class="sxs-lookup"><span data-stu-id="2a74a-129">Options</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="2a74a-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2a74a-130">.NET Core 3.0</span></span>](#tab/netcore30)

`--`

<span data-ttu-id="2a74a-131">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="2a74a-131">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2a74a-132">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-132">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2a74a-133">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="2a74a-133">Defines the build configuration.</span></span> <span data-ttu-id="2a74a-134">Der Standardwert für die meisten Projekte ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-134">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2a74a-135">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="2a74a-135">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2a74a-136">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a74a-136">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="2a74a-137">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2a74a-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2a74a-138">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2a74a-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2a74a-139">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2a74a-139">Prints out a short help for the command.</span></span>

`--interactive`

<span data-ttu-id="2a74a-140">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="2a74a-140">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="2a74a-141">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="2a74a-141">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="2a74a-142">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-142">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="2a74a-143">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="2a74a-143">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="2a74a-144">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="2a74a-144">Doesn't build the project before running.</span></span> <span data-ttu-id="2a74a-145">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-145">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="2a74a-146">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="2a74a-146">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="2a74a-147">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2a74a-147">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="2a74a-148">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2a74a-148">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="2a74a-149">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="2a74a-149">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="2a74a-150">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-150">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2a74a-151">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="2a74a-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2a74a-152">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2a74a-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2a74a-153">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="2a74a-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2a74a-154">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2a74a-155">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2a74a-155">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="2a74a-156">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="2a74a-156">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2a74a-157">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-157">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2a74a-158">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="2a74a-158">Defines the build configuration.</span></span> <span data-ttu-id="2a74a-159">Der Standardwert für die meisten Projekte ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-159">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2a74a-160">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="2a74a-160">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2a74a-161">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a74a-161">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="2a74a-162">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2a74a-162">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2a74a-163">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2a74a-163">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2a74a-164">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2a74a-164">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="2a74a-165">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="2a74a-165">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="2a74a-166">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-166">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="2a74a-167">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="2a74a-167">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="2a74a-168">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="2a74a-168">Doesn't build the project before running.</span></span> <span data-ttu-id="2a74a-169">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-169">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="2a74a-170">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="2a74a-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="2a74a-171">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2a74a-171">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="2a74a-172">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2a74a-172">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="2a74a-173">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="2a74a-173">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="2a74a-174">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-174">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2a74a-175">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="2a74a-175">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2a74a-176">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2a74a-176">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2a74a-177">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="2a74a-177">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2a74a-178">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-178">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2a74a-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2a74a-179">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="2a74a-180">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="2a74a-180">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2a74a-181">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-181">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2a74a-182">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="2a74a-182">Defines the build configuration.</span></span> <span data-ttu-id="2a74a-183">Der Standardwert für die meisten Projekte ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-183">The default for most projects value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2a74a-184">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="2a74a-184">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2a74a-185">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a74a-185">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="2a74a-186">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2a74a-186">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2a74a-187">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="2a74a-187">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="2a74a-188">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2a74a-188">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="2a74a-189">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="2a74a-189">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="2a74a-190">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-190">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="2a74a-191">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="2a74a-191">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="2a74a-192">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="2a74a-192">Doesn't build the project before running.</span></span> <span data-ttu-id="2a74a-193">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-193">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="2a74a-194">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="2a74a-194">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="2a74a-195">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2a74a-195">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="2a74a-196">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2a74a-196">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="2a74a-197">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="2a74a-197">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="2a74a-198">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-198">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="2a74a-199">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="2a74a-199">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2a74a-200">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="2a74a-200">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2a74a-201">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2a74a-201">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="2a74a-202">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="2a74a-202">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="2a74a-203">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="2a74a-203">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="2a74a-204">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="2a74a-204">Defines the build configuration.</span></span> <span data-ttu-id="2a74a-205">Der Standardwert für die meisten Projekte ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="2a74a-205">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="2a74a-206">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="2a74a-206">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="2a74a-207">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2a74a-207">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="2a74a-208">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="2a74a-208">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="2a74a-209">Gibt den Pfad und Namen der Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="2a74a-209">Specifies the path and name of the project file.</span></span> <span data-ttu-id="2a74a-210">(Siehe HINWEIS.) Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="2a74a-210">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="2a74a-211">Verwenden Sie den Pfad und Namen der Projektdatei mit der `-p|--project`-Option.</span><span class="sxs-lookup"><span data-stu-id="2a74a-211">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="2a74a-212">Eine Regression in der CLI verhindert, dass ein Pfad mit dem .NET Core SDK 1.x bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2a74a-212">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="2a74a-213">Weitere Informationen zu diesem Problem finden Sie unter [dotnet run -p, can not start a project (dotnet/cli #5992) (dotnet run -p, ein Projekt kann nicht gestartet werden (dotnet/cli #5992))](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="2a74a-213">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="2a74a-214">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2a74a-214">Examples</span></span>

<span data-ttu-id="2a74a-215">Führt das Projekt im aktuellen Verzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="2a74a-215">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="2a74a-216">Führt das angegebene Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="2a74a-216">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="2a74a-217">Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da die leere Option `--` verwendet wird):</span><span class="sxs-lookup"><span data-stu-id="2a74a-217">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="2a74a-218">Stellt Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis wieder her, wobei nur eine minimale Ausgabe angezeigt wird, und führt dann das Projekt aus (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="2a74a-218">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
