---
title: Befehl „dotnet run“
description: Der dotnet run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode.
ms.date: 02/19/2020
ms.openlocfilehash: e442ed56d676ffd189ef6d394d840cea671c2dc6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157075"
---
# <a name="dotnet-run"></a><span data-ttu-id="84e7a-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="84e7a-103">dotnet run</span></span>

<span data-ttu-id="84e7a-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.x SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="84e7a-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="84e7a-105">Name</span><span class="sxs-lookup"><span data-stu-id="84e7a-105">Name</span></span>

<span data-ttu-id="84e7a-106">`dotnet run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.</span><span class="sxs-lookup"><span data-stu-id="84e7a-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="84e7a-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="84e7a-107">Synopsis</span></span>

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile]
    [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project]
    [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a><span data-ttu-id="84e7a-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="84e7a-108">Description</span></span>

<span data-ttu-id="84e7a-109">Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="84e7a-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="84e7a-110">Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="84e7a-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="84e7a-111">Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="84e7a-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="84e7a-112">Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.</span><span class="sxs-lookup"><span data-stu-id="84e7a-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="84e7a-113">Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="84e7a-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="84e7a-114">Angenommen, Sie haben eine `netcoreapp2.1`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp2.1` platziert.</span><span class="sxs-lookup"><span data-stu-id="84e7a-114">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="84e7a-115">Dateien werden bei Bedarf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="84e7a-115">Files are overwritten as needed.</span></span> <span data-ttu-id="84e7a-116">Temporäre Dateien befinden sich im `obj`-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="84e7a-116">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="84e7a-117">Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.</span><span class="sxs-lookup"><span data-stu-id="84e7a-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="84e7a-118">Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="84e7a-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="84e7a-119">Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="84e7a-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="84e7a-120">Zum Ausführen von `myapp.dll` verwenden Sie z.B.:</span><span class="sxs-lookup"><span data-stu-id="84e7a-120">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="84e7a-121">Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).</span><span class="sxs-lookup"><span data-stu-id="84e7a-121">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="84e7a-122">Der Befehl `dotnet run` löst die Abhängigkeiten der Anwendungen außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="84e7a-122">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="84e7a-123">Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="84e7a-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="84e7a-124">Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="84e7a-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="84e7a-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="84e7a-125">Options</span></span>

- **`--`**

  <span data-ttu-id="84e7a-126">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="84e7a-126">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="84e7a-127">Alle Argumente nach diesem Trennzeichen werden an die Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="84e7a-127">All arguments after this delimiter are passed to the application run.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="84e7a-128">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="84e7a-128">Defines the build configuration.</span></span> <span data-ttu-id="84e7a-129">Der Standardwert für die meisten Projekte ist `Debug`, aber Sie können die Buildkonfigurationseinstellungen in Ihrem Projekt überschreiben.</span><span class="sxs-lookup"><span data-stu-id="84e7a-129">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="84e7a-130">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="84e7a-130">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="84e7a-131">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="84e7a-131">The framework must be specified in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="84e7a-132">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="84e7a-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="84e7a-133">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="84e7a-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="84e7a-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="84e7a-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="84e7a-135">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten (z.B. um die Authentifizierung abzuschließen).</span><span class="sxs-lookup"><span data-stu-id="84e7a-135">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="84e7a-136">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="84e7a-136">Available since .NET Core 3.0 SDK.</span></span>

- **`--launch-profile <NAME>`**

  <span data-ttu-id="84e7a-137">Der Name des beim Start einer Anwendung zu verwendenden Startprofils (falls vorhanden).</span><span class="sxs-lookup"><span data-stu-id="84e7a-137">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="84e7a-138">Startprofile werden in der Datei *launchSettings.json* definiert und heißen normalerweise `Development`, `Staging` und `Production`.</span><span class="sxs-lookup"><span data-stu-id="84e7a-138">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="84e7a-139">Weitere Informationen finden Sie unter [Working with multiple environments (Verwenden von mehreren Umgebungen)](/aspnet/core/fundamentals/environments).</span><span class="sxs-lookup"><span data-stu-id="84e7a-139">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

- **`--no-build`**

  <span data-ttu-id="84e7a-140">Erstellt das Projekt nicht vor der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="84e7a-140">Doesn't build the project before running.</span></span> <span data-ttu-id="84e7a-141">Das `--no-restore`-Flag wird implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84e7a-141">It also implicit sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="84e7a-142">Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.</span><span class="sxs-lookup"><span data-stu-id="84e7a-142">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

- **`--no-launch-profile`**

  <span data-ttu-id="84e7a-143">Versucht nicht, die Anwendung mit *launchSettings.json* zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="84e7a-143">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

- **`--no-restore`**

  <span data-ttu-id="84e7a-144">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="84e7a-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-p|--project <PATH>`**

  <span data-ttu-id="84e7a-145">Gibt den Pfad der auszuführenden Projektdatei an (Ordnername oder vollständiger Pfad).</span><span class="sxs-lookup"><span data-stu-id="84e7a-145">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="84e7a-146">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="84e7a-146">If not specified, it defaults to the current directory.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="84e7a-147">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="84e7a-147">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="84e7a-148">Eine Liste der Runtime-IDs (RIDs) finden Sie im [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="84e7a-148">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="84e7a-149">Die Kurzoption `-r` ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="84e7a-149">`-r` short option available since .NET Core 3.0 SDK.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="84e7a-150">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="84e7a-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="84e7a-151">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="84e7a-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="84e7a-152">Der Standardwert ist `m`.</span><span class="sxs-lookup"><span data-stu-id="84e7a-152">The default value is `m`.</span></span> <span data-ttu-id="84e7a-153">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="84e7a-153">Available since .NET Core 2.1 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="84e7a-154">Beispiele</span><span class="sxs-lookup"><span data-stu-id="84e7a-154">Examples</span></span>

- <span data-ttu-id="84e7a-155">Führt das Projekt im aktuellen Verzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="84e7a-155">Run the project in the current directory:</span></span>

  ```dotnetcli
  dotnet run
  ```

- <span data-ttu-id="84e7a-156">Führt das angegebene Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="84e7a-156">Run the specified project:</span></span>

  ```dotnetcli
  dotnet run --project ./projects/proj1/proj1.csproj
  ```

- <span data-ttu-id="84e7a-157">Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da die leere Option `--` verwendet wird):</span><span class="sxs-lookup"><span data-stu-id="84e7a-157">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

  ```dotnetcli
  dotnet run --configuration Release -- --help
  ```

- <span data-ttu-id="84e7a-158">Stellt Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis wieder her, wobei nur eine minimale Ausgabe angezeigt wird, und führt dann das Projekt aus (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="84e7a-158">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

  ```dotnetcli
  dotnet run --verbosity m
  ```
