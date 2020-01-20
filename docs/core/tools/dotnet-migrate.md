---
title: Befehl „dotnet migrate“
description: Der dotnet migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten.
ms.date: 01/07/2020
ms.openlocfilehash: d746069b897a7458e0262663e96cc8743a586aa9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740511"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="95ec8-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="95ec8-103">dotnet migrate</span></span>

<span data-ttu-id="95ec8-104">**Dieser Artikel gilt für: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="95ec8-104">**This article applies to: ✓** .NET Core 1.x SDK **✓** .NET Core 2.x SDK</span></span>

## <a name="name"></a><span data-ttu-id="95ec8-105">name</span><span class="sxs-lookup"><span data-stu-id="95ec8-105">Name</span></span>

<span data-ttu-id="95ec8-106">`dotnet migrate`: migriert ein .NET Core-Projekt der Vorschauversion 2 in ein SDK-Projekt für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="95ec8-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="95ec8-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="95ec8-107">Synopsis</span></span>

```dotnetcli
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="95ec8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95ec8-108">Description</span></span>

<span data-ttu-id="95ec8-109">Dieser Befehl ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="95ec8-109">This command is deprecated.</span></span> <span data-ttu-id="95ec8-110">Der `dotnet migrate`-Befehl ist im .NET Core 3.0 SDK und in neueren Versionen nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="95ec8-110">The `dotnet migrate` command is no longer available starting with .NET Core 3.0 SDK.</span></span> <span data-ttu-id="95ec8-111">Er kann nur ein .NET Core-Projekt von Vorschau 2 zu einem .NET Core-Projekt der Version 1. x migrieren, was nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="95ec8-111">It can only migrate a Preview 2 .NET Core project to a 1.x .NET Core project, which is out of support.</span></span>

<span data-ttu-id="95ec8-112">Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält.</span><span class="sxs-lookup"><span data-stu-id="95ec8-112">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="95ec8-113">Dieses Verhalten ist mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="95ec8-113">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="95ec8-114">Die Migration kann auf den folgenden Objekten ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="95ec8-114">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="95ec8-115">Ein einzelnes Projekt durch Angabe der zu migrierenden *project.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="95ec8-115">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="95ec8-116">Alle Verzeichnisse, die in der *global.json*-Datei angegeben sind, indem ein Pfad zur *global.json*-Datei übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="95ec8-116">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="95ec8-117">Ein *solution.sln*-Datei, in dem die Projekte, auf die in der Projektmappe verwiesen wird, migriert werden.</span><span class="sxs-lookup"><span data-stu-id="95ec8-117">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="95ec8-118">Rekursiv für alle Unterverzeichnisse im angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="95ec8-118">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="95ec8-119">Der `dotnet migrate`-Befehl speichert die migrierte *project.json*-Datei in einem `backup`-Verzeichnis, das erstellt wird, falls das Verzeichnis noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="95ec8-119">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="95ec8-120">Das Verhalten wird mithilfe der `--skip-backup`-Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="95ec8-120">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="95ec8-121">Standardmäßig gibt der Migrationsvorgang den Status der Migration in die Standardausgabe (STDOUT) aus.</span><span class="sxs-lookup"><span data-stu-id="95ec8-121">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="95ec8-122">Bei Verwendung der `--report-file <REPORT_FILE>`-Option wird die Ausgabe in die angegebene Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="95ec8-122">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="95ec8-123">Der `dotnet migrate`-Befehl unterstützt nur gültige *project.json*-basiere Projekte von Preview 2.</span><span class="sxs-lookup"><span data-stu-id="95ec8-123">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="95ec8-124">Dies bedeutet, dass Sie ihn nicht zum Migrieren von *project.json*-basierten Projekte von DNX oder Preview 1 direkt an MSBuild/csproj-Projekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="95ec8-124">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="95ec8-125">Sie müssen zuerst das Projekt manuell auf ein *project.json*-basiertes Projekt von Preview 2 migrieren und anschließend den `dotnet migrate`-Befehl verwenden, um das Projekt zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="95ec8-125">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="95ec8-126">Argumente</span><span class="sxs-lookup"><span data-stu-id="95ec8-126">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="95ec8-127">Der Pfad zu einem der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="95ec8-127">The path to one of the following:</span></span>

* <span data-ttu-id="95ec8-128">eine *project.json*-Datei zum Migrieren.</span><span class="sxs-lookup"><span data-stu-id="95ec8-128">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="95ec8-129">eine *global.json*-Datei. Die in *global.json* angegebenen Ordner werden migriert.</span><span class="sxs-lookup"><span data-stu-id="95ec8-129">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="95ec8-130">eine *solution.sln*-Datei. Die in der Projektmappe referenzierten Projekte werden migriert.</span><span class="sxs-lookup"><span data-stu-id="95ec8-130">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="95ec8-131">ein zu migrierendes Verzeichnis. Sucht rekursiv nach *project.json*-Dateien, um diese im angegebenen Verzeichnis zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="95ec8-131">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="95ec8-132">Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="95ec8-132">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="95ec8-133">Optionen</span><span class="sxs-lookup"><span data-stu-id="95ec8-133">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="95ec8-134">Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="95ec8-134">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="95ec8-135">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="95ec8-135">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="95ec8-136">Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="95ec8-136">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="95ec8-137">Die Migration von Projektverweisen wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="95ec8-137">Skip migrating project references.</span></span> <span data-ttu-id="95ec8-138">Standardmäßig werden Projektverweise rekursiv migriert.</span><span class="sxs-lookup"><span data-stu-id="95ec8-138">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="95ec8-139">Das Verschieben der Dateien *project.json*, *global.json* und *\*.xproj* in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="95ec8-139">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="95ec8-140">Für die Migration zu verwendende CSPROJ-Vorlagendatei.</span><span class="sxs-lookup"><span data-stu-id="95ec8-140">Template csproj file to use for migration.</span></span> <span data-ttu-id="95ec8-141">Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="95ec8-141">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="95ec8-142">Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="95ec8-142">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="95ec8-143">Der Standardwert ist die Version des SDK in `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="95ec8-143">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="95ec8-144">Der Pfad zur XPROJ-Datei, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="95ec8-144">The path to the xproj file to use.</span></span> <span data-ttu-id="95ec8-145">Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="95ec8-145">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="95ec8-146">Beispiele</span><span class="sxs-lookup"><span data-stu-id="95ec8-146">Examples</span></span>

<span data-ttu-id="95ec8-147">Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="95ec8-147">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="95ec8-148">Migrieren Sie alle Projekte, die die *global.json*-Datei umfasst:</span><span class="sxs-lookup"><span data-stu-id="95ec8-148">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="95ec8-149">Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten (P2P).</span><span class="sxs-lookup"><span data-stu-id="95ec8-149">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="95ec8-150">Verwenden Sie außerdem eine bestimmte SDK-Version:</span><span class="sxs-lookup"><span data-stu-id="95ec8-150">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
