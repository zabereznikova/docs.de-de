---
title: "dotnet-run-Befehl – .NET Core-CLI"
description: "Der dotnet-run-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode."
keywords: dotnet-run, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f0a6fce4f83808076b7cbcabdaa948badde2cf80
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-run"></a><span data-ttu-id="b5f13-104">dotnet-run</span><span class="sxs-lookup"><span data-stu-id="b5f13-104">dotnet-run</span></span>

## <a name="name"></a><span data-ttu-id="b5f13-105">Name</span><span class="sxs-lookup"><span data-stu-id="b5f13-105">Name</span></span> 

<span data-ttu-id="b5f13-106">`dotnet-run`: Führt Quellcode ohne explizite Kompilierungs- oder Startbefehle aus.</span><span class="sxs-lookup"><span data-stu-id="b5f13-106">`dotnet-run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b5f13-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b5f13-107">Synopsis</span></span>

`dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]] [-h|--help]`

## <a name="description"></a><span data-ttu-id="b5f13-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5f13-108">Description</span></span>

<span data-ttu-id="b5f13-109">Der `dotnet run`-Befehl bietet eine praktische Option zum Ausführen der Anwendung aus dem Quellcode mit einem Befehl.</span><span class="sxs-lookup"><span data-stu-id="b5f13-109">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="b5f13-110">Es empfiehlt sich für eine schnelle iterative Entwicklung aus der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="b5f13-110">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="b5f13-111">Der Befehl hängt vom [`dotnet build`](dotnet-build.md)-Befehl ab, um den Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b5f13-111">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="b5f13-112">Alle Anforderungen für den Build, z.B. dass das Projekt zuerst wiederhergestellt werden muss, werden auch auf `dotnet run` angewendet.</span><span class="sxs-lookup"><span data-stu-id="b5f13-112">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span> 

<span data-ttu-id="b5f13-113">Ausgabedateien werden im Standardspeicherort `bin/<configuration>/<target>` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5f13-113">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="b5f13-114">Angenommen, Sie haben eine `netcoreapp1.0`-Anwendung und Sie führen `dotnet run` aus, dann wird die Ausgabe in `bin/Debug/netcoreapp1.0` platziert.</span><span class="sxs-lookup"><span data-stu-id="b5f13-114">For example if you have a `netcoreapp1.0` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp1.0`.</span></span> <span data-ttu-id="b5f13-115">Dateien werden bei Bedarf überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b5f13-115">Files are overwritten as needed.</span></span> <span data-ttu-id="b5f13-116">Temporäre Dateien befinden sich im `obj`-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b5f13-116">Temporary files are placed in the `obj` directory.</span></span> 

<span data-ttu-id="b5f13-117">Wenn das Projekt mehrere Frameworks angibt, führt das Ausführen von `dotnet run` zu einem Fehler, wenn nicht die `-f|--framework <FRAMEWORK>`-Option verwendet wird, um das Framework anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5f13-117">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="b5f13-118">Der Befehl `dotnet run` wird im Kontext von Projekten verwendet, nicht von erstellten Assemblys.</span><span class="sxs-lookup"><span data-stu-id="b5f13-118">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="b5f13-119">Wenn Sie stattdessen eine Framework-abhängige DLL-Anwendung ausführen möchten, müssen Sie [dotnet](dotnet.md) ohne einen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5f13-119">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="b5f13-120">Zum Ausführen von `myapp.dll` verwenden Sie z.B.:</span><span class="sxs-lookup"><span data-stu-id="b5f13-120">For example, to run `myapp.dll`, use:</span></span>
 
```
dotnet myapp.dll
```

<span data-ttu-id="b5f13-121">Weitere Informationen zum `dotnet`-Treiber finden Sie unter dem Thema [.NET Core-Befehlszeilentools (CLI)](index.md).</span><span class="sxs-lookup"><span data-stu-id="b5f13-121">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="b5f13-122">Um die Anwendung auszuführen, löst der `dotnet run`-Befehl die Abhängigkeiten der Anwendung außerhalb der freigegebenen Laufzeit aus dem NuGet-Cache.</span><span class="sxs-lookup"><span data-stu-id="b5f13-122">In order to run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="b5f13-123">Da sie zwischengespeicherte Abhängigkeiten verwendet, wird nicht empfohlen, `dotnet run` zur Ausführung der Anwendungen in der Produktion zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5f13-123">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="b5f13-124">Stattdessen [erstellen Sie eine Bereitstellung](../deploying/index.md) mithilfe des [`dotnet publish`](dotnet-publish.md)-Befehls und stellen die veröffentlichte Ausgabe bereit.</span><span class="sxs-lookup"><span data-stu-id="b5f13-124">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span> 

## <a name="options"></a><span data-ttu-id="b5f13-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="b5f13-125">Options</span></span>

`--`

<span data-ttu-id="b5f13-126">Grenzt Argumente für `dotnet run` von Argumenten für die ausgeführte Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="b5f13-126">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="b5f13-127">Alle nachfolgenden Argumente werden der Anwendungsausführung übergeben.</span><span class="sxs-lookup"><span data-stu-id="b5f13-127">All arguments after this one are passed to the application run.</span></span> 

`-h|--help`

<span data-ttu-id="b5f13-128">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="b5f13-128">Prints out a short help for the command.</span></span>

`-c|--configuration <CONFIGURATION>`

<span data-ttu-id="b5f13-129">Konfiguration, die beim Erstellen des Projekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5f13-129">Configuration to use for building the project.</span></span> <span data-ttu-id="b5f13-130">Der Standardwert ist `Debug`.</span><span class="sxs-lookup"><span data-stu-id="b5f13-130">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b5f13-131">Erstellt und führt die Anwendung mithilfe des angegebenen [Frameworks](../../standard/frameworks.md) aus.</span><span class="sxs-lookup"><span data-stu-id="b5f13-131">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b5f13-132">Das Framework muss in der Projektdatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b5f13-132">The framework must be specified in the project file.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="b5f13-133">Gibt den Pfad und Namen der Projektdatei an.</span><span class="sxs-lookup"><span data-stu-id="b5f13-133">Specifies the path and name of the project file.</span></span> <span data-ttu-id="b5f13-134">(Siehe HINWEIS.) Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="b5f13-134">(See the NOTE.) It defaults to the current directory if not specified.</span></span>

> [!NOTE]
> <span data-ttu-id="b5f13-135">Verwenden Sie den Pfad und Namen der Projektdatei mit der `-p|--project`-Option.</span><span class="sxs-lookup"><span data-stu-id="b5f13-135">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="b5f13-136">Eine Regression in der CLI verhindert, dass zu diesem Zeitpunkt ein Pfad bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b5f13-136">A regression in the CLI prevents providing a folder path at this time.</span></span> <span data-ttu-id="b5f13-137">Weitere Informationen und eine Überwachung dieses Problems finden Sie unter [dotnet run -p, can not start a project (dotnet/cli #5992) (dotnet run -p, ein Projekt kann nicht gestartet werden (dotnet/cli #5992))](https://github.com/dotnet/cli/issues/5992).</span><span class="sxs-lookup"><span data-stu-id="b5f13-137">For more information and to track this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

## <a name="examples"></a><span data-ttu-id="b5f13-138">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b5f13-138">Examples</span></span>

<span data-ttu-id="b5f13-139">Führt das Projekt im aktuellen Verzeichnis aus:</span><span class="sxs-lookup"><span data-stu-id="b5f13-139">Run the project in the current directory:</span></span>

`dotnet run` 

<span data-ttu-id="b5f13-140">Führt das angegebene Projekt aus:</span><span class="sxs-lookup"><span data-stu-id="b5f13-140">Run the specified project:</span></span>

`dotnet run --project /projects/proj1/proj1.csproj`

<span data-ttu-id="b5f13-141">Führt das Projekt im aktuellen Verzeichnis aus (das Argument `--help` in diesem Beispiel wird der Anwendung übergeben, da das Argument `--` verwendet wird):</span><span class="sxs-lookup"><span data-stu-id="b5f13-141">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the `--` argument is used):</span></span>

`dotnet run --configuration Release -- --help`

