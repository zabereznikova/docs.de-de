---
title: "dotnet-migrate-Befehl – .NET Core-CLI"
description: "Der dotnet-migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten."
keywords: dotnet-migrate, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e8491d69b2e0df7b3bd2741e34abdb9631777019
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-migrate"></a><span data-ttu-id="3583f-104">dotnet-migrate</span><span class="sxs-lookup"><span data-stu-id="3583f-104">dotnet-migrate</span></span>

## <a name="name"></a><span data-ttu-id="3583f-105">Name</span><span class="sxs-lookup"><span data-stu-id="3583f-105">Name</span></span>

<span data-ttu-id="3583f-106">`dotnet-migrate`: Migriert ein .NET Core-Projekt von Preview 2 in ein .NET Core-Projekt von SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="3583f-106">`dotnet-migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK 1.0 project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3583f-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="3583f-107">Synopsis</span></span>

`dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [-h|--help]`

## <a name="description"></a><span data-ttu-id="3583f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3583f-108">Description</span></span>

<span data-ttu-id="3583f-109">Der `dotnet migrate`-Befehl migriert ein gültiges *project.json*-basiertes Projekt von Preview 2 in ein gültiges *csproj*-Projekt von .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="3583f-109">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK 1.0 *csproj* project.</span></span> 

<span data-ttu-id="3583f-110">Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält.</span><span class="sxs-lookup"><span data-stu-id="3583f-110">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="3583f-111">Dieses Verhalten ist mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3583f-111">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span> 

<span data-ttu-id="3583f-112">Migration wird auf Folgendes ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="3583f-112">Migration is performed on the following:</span></span>

* <span data-ttu-id="3583f-113">Ein einzelnes Projekt durch Angabe der zu migrierenden *project.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="3583f-113">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="3583f-114">Alle Verzeichnisse, die in der *global.json*-Datei angegeben sind, indem ein Pfad zur *global.json*-Datei übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="3583f-114">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="3583f-115">Ein *solution.sln*-Datei, in dem die Projekte, auf die in der Projektmappe verwiesen wird, migriert werden.</span><span class="sxs-lookup"><span data-stu-id="3583f-115">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="3583f-116">Rekursiv für alle Unterverzeichnisse im angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="3583f-116">On all sub-directories of the given directory recursively.</span></span>

<span data-ttu-id="3583f-117">Der `dotnet migrate`-Befehl speichert die migrierte *project.json*-Datei in einem `backup`-Verzeichnis, das erstellt wird, falls das Verzeichnis noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3583f-117">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="3583f-118">Das Verhalten wird mithilfe der `--skip-backup`-Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="3583f-118">This behavior is overriden using the `--skip-backup` option.</span></span> 

<span data-ttu-id="3583f-119">Standardmäßig gibt der Migrationsvorgang den Status der Migration in die Standardausgabe (STDOUT) aus.</span><span class="sxs-lookup"><span data-stu-id="3583f-119">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="3583f-120">Bei Verwendung der `--report-file <REPORT_FILE>`-Option wird die Ausgabe in die angegebene Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3583f-120">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span> 

<span data-ttu-id="3583f-121">Der `dotnet migrate`-Befehl unterstützt nur gültige *project.json*-basiere Projekte von Preview 2.</span><span class="sxs-lookup"><span data-stu-id="3583f-121">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="3583f-122">Dies bedeutet, dass Sie ihn nicht zum Migrieren von *project.json*-basierten Projekte von DNX oder Preview 1 direkt an MSBuild/csproj-Projekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3583f-122">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="3583f-123">Sie müssen zuerst das Projekt manuell auf ein *project.json*-basiertes Projekt von Preview 2 migrieren und anschließend den `dotnet migrate`-Befehl verwenden, um das Projekt zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="3583f-123">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="3583f-124">Argumente</span><span class="sxs-lookup"><span data-stu-id="3583f-124">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="3583f-125">Der Pfad zu einem der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="3583f-125">The path to one of the following:</span></span>

* <span data-ttu-id="3583f-126">eine *project.json*-Datei zum Migrieren.</span><span class="sxs-lookup"><span data-stu-id="3583f-126">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="3583f-127">eine *global.json*-Datei wird die in *global.json* angegebenen Ordner migrieren.</span><span class="sxs-lookup"><span data-stu-id="3583f-127">a *global.json* file, it will migrate the folders specified in *global.json*.</span></span>
* <span data-ttu-id="3583f-128">eine *solution.sln*-Datei wird die Projekte migrieren, auf die in der Projektmappe verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3583f-128">a *solution.sln* file, it will migrate the projects referenced in the solution.</span></span>
* <span data-ttu-id="3583f-129">ein Verzeichnis zum Migrieren, das rekursiv nach *project.json*-Dateien suchen wird, um sie zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="3583f-129">a directory to migrate, it will recursively search for *project.json* files to migrate.</span></span>

<span data-ttu-id="3583f-130">Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="3583f-130">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="3583f-131">Optionen</span><span class="sxs-lookup"><span data-stu-id="3583f-131">Options</span></span>

`-h|--help`

<span data-ttu-id="3583f-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="3583f-132">Prints out a short help for the command.</span></span>  

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="3583f-133">Für die Migration zu verwendende CSPROJ-Vorlagendatei.</span><span class="sxs-lookup"><span data-stu-id="3583f-133">Template csproj file to use for migration.</span></span> <span data-ttu-id="3583f-134">Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="3583f-134">By default, the same template as the one dropped by `dotnet new console` is used.</span></span> 

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="3583f-135">Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3583f-135">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="3583f-136">Der Standardwert ist die Version des SDK in `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="3583f-136">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="3583f-137">Der Pfad zur XPROJ-Datei, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3583f-137">The path to the xproj file to use.</span></span> <span data-ttu-id="3583f-138">Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3583f-138">Required when there is more than one xproj in a project directory.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="3583f-139">Die Migration von Projektverweisen wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="3583f-139">Skip migrating project references.</span></span> <span data-ttu-id="3583f-140">Standardmäßig werden Projektverweise rekursiv migriert.</span><span class="sxs-lookup"><span data-stu-id="3583f-140">By default, project references are migrated recursively.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="3583f-141">Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3583f-141">Output migration report to a file in addition to the console.</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="3583f-142">Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3583f-142">Output migration report file as JSON rather than user messages.</span></span>

`--skip-backup`

<span data-ttu-id="3583f-143">Das Verschieben der Dateien *project.json*, *global.json* und *\*.xproj* in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="3583f-143">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

## <a name="examples"></a><span data-ttu-id="3583f-144">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3583f-144">Examples</span></span>

<span data-ttu-id="3583f-145">Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="3583f-145">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="3583f-146">Migrieren Sie alle Projekte, die die *global.json*-Datei umfasst:</span><span class="sxs-lookup"><span data-stu-id="3583f-146">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="3583f-147">Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten (P2P).</span><span class="sxs-lookup"><span data-stu-id="3583f-147">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="3583f-148">Verwenden Sie außerdem eine bestimmte SDK-Version:</span><span class="sxs-lookup"><span data-stu-id="3583f-148">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`

