---
title: dotnet run-Befehl – .NET Core-CLI
description: Der dotnet run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.openlocfilehash: b45d6772cabd6be90ea8e8b5da57c16692b20322
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-run"></a><span data-ttu-id="e1857-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e1857-103">dotnet run</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e1857-104">name</span><span class="sxs-lookup"><span data-stu-id="e1857-104">Name</span></span>

<span data-ttu-id="e1857-105">`dotnet run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.</span><span class="sxs-lookup"><span data-stu-id="e1857-105">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e1857-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e1857-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e1857-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e1857-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e1857-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e1857-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e1857-109">description</span><span class="sxs-lookup"><span data-stu-id="e1857-109">Description</span></span>

<span data-ttu-id="e1857-110">Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="e1857-110">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="e1857-111">Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="e1857-111">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="e1857-112">Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1857-112">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="e1857-113">Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.</span><span class="sxs-lookup"><span data-stu-id="e1857-113">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="e1857-114">Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1857-114">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="e1857-115">Angenommen, Sie haben eine `netcoreapp1.0`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp1.0` platziert.</span><span class="sxs-lookup"><span data-stu-id="e1857-115">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="e1857-116">Dateien werden bei Bedarf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="e1857-116">Files are overwritten as needed.</span></span> <span data-ttu-id="e1857-117">Temporäre Dateien befinden sich im `obj`-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e1857-117">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="e1857-118">Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.</span><span class="sxs-lookup"><span data-stu-id="e1857-118">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="e1857-119">Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="e1857-119">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="e1857-120">Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1857-120">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="e1857-121">Zum Ausführen von `myapp.dll` verwenden Sie z.B.:</span><span class="sxs-lookup"><span data-stu-id="e1857-121">For example, to run `myapp.dll`, use:</span></span>

```
dotnet myapp.dll
```

<span data-ttu-id="e1857-122">Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).</span><span class="sxs-lookup"><span data-stu-id="e1857-122">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="e1857-123">Um die Anwendung auszuführen, löst der `dotnet run`-Befehl die Abhängigkeiten der Anwendung außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache.</span><span class="sxs-lookup"><span data-stu-id="e1857-123">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="e1857-124">Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1857-124">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="e1857-125">Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="e1857-125">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="e1857-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="e1857-126">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e1857-127">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e1857-127">.NET Core 2.x</span></span>](#tab/netcore2x)

`--`

<span data-ttu-id="e1857-128">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="e1857-128">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e1857-129">Alle nachfolgenden Argumente werden der Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="e1857-129">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e1857-130">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="e1857-130">Defines the build configuration.</span></span> <span data-ttu-id="e1857-131">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e1857-131">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e1857-132">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e1857-132">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e1857-133">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1857-133">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="e1857-134">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="e1857-134">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="e1857-135">Dies entspricht dem Löschen von *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="e1857-135">This is equivalent to deleting *project.assets.json*.</span></span>

`-h|--help`

<span data-ttu-id="e1857-136">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e1857-136">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="e1857-137">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="e1857-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="e1857-138">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="e1857-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging` and `Production`.</span></span> <span data-ttu-id="e1857-139">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="e1857-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="e1857-140">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="e1857-140">Doesn't build the project before running.</span></span>

`--no-dependencies`

<span data-ttu-id="e1857-141">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="e1857-141">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="e1857-142">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e1857-142">Doesn't attempt to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="e1857-143">Führt kein implizites Wiederherstellen durch, wenn der Befehl ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="e1857-143">Doesn't perform an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="e1857-144">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="e1857-144">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="e1857-145">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="e1857-145">It defaults to the current directory if not specified.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="e1857-146">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="e1857-146">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="e1857-147">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="e1857-147">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e1857-148">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e1857-148">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="e1857-149">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="e1857-149">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="e1857-150">Alle nachfolgenden Argumente werden der Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="e1857-150">All arguments after this one are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="e1857-151">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="e1857-151">Defines the build configuration.</span></span> <span data-ttu-id="e1857-152">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="e1857-152">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="e1857-153">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e1857-153">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="e1857-154">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e1857-154">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="e1857-155">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e1857-155">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="e1857-156">Gibt den Pfad und Namen der Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="e1857-156">Specifies the path and name of the project file.</span></span> <span data-ttu-id="e1857-157">(Siehe HINWEIS.) Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="e1857-157">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="e1857-158">Verwenden Sie den Pfad und Namen der Projektdatei mit der `-p|--project`-Option.</span><span class="sxs-lookup"><span data-stu-id="e1857-158">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="e1857-159">Eine Regression in der CLI verhindert, dass ein Pfad mit dem .NET Core SDK 1.x bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e1857-159">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="e1857-160">Weitere Informationen zu diesem Problem finden Sie unter [dotnet run -p, can not start a project (dotnet/cli #5992) (dotnet run -p, ein Projekt kann nicht gestartet werden (dotnet/cli #5992))](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="e1857-160">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="e1857-161">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e1857-161">Examples</span></span>

<span data-ttu-id="e1857-162">Führt das Projekt im aktuellen Verzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="e1857-162">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="e1857-163">Führt das angegebene Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="e1857-163">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="e1857-164">Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da das Argument `--` verwendet wird):</span><span class="sxs-lookup"><span data-stu-id="e1857-164">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="e1857-165">Stellt Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis wieder her, wobei nur eine minimale Ausgabe angezeigt wird, und führt dann das Projekt aus (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="e1857-165">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`