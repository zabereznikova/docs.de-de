---
title: Befehl „dotnet migrate“
description: Der dotnet migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten.
ms.date: 06/26/2019
ms.openlocfilehash: 86f11592e774da12b010886aaa1e30cee063fea6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202537"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="a7734-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="a7734-103">dotnet migrate</span></span>

<span data-ttu-id="a7734-104">**Dieses Thema gilt für: ✓**.NET Core 1.x SDK und spätere Versionen</span><span class="sxs-lookup"><span data-stu-id="a7734-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="a7734-105">name</span><span class="sxs-lookup"><span data-stu-id="a7734-105">Name</span></span>

<span data-ttu-id="a7734-106">`dotnet migrate`: migriert ein .NET Core-Projekt der Vorschauversion 2 in ein SDK-Projekt für .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a7734-106">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK-style project.</span></span>

> [!NOTE]
> <span data-ttu-id="a7734-107">`dotnet migrate` wird aus der nächsten Vorschauversion des SDK für .NET Core 3.0 entfernt.</span><span class="sxs-lookup"><span data-stu-id="a7734-107">`dotnet migrate` will be removed from the .NET Core 3.0 SDK in the next preview release.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a7734-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a7734-108">Synopsis</span></span>

```console
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a7734-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7734-109">Description</span></span>

<span data-ttu-id="a7734-110">Der Befehl `dotnet migrate` migriert ein gültiges *project.json*-basiertes Projekt für die Vorschauversion 2 in ein gültiges *csproj*-Projekt für das .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="a7734-110">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK-style *csproj* project.</span></span>

<span data-ttu-id="a7734-111">Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält.</span><span class="sxs-lookup"><span data-stu-id="a7734-111">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="a7734-112">Dieses Verhalten ist mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a7734-112">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="a7734-113">Die Migration kann auf den folgenden Objekten ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="a7734-113">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="a7734-114">Ein einzelnes Projekt durch Angabe der zu migrierenden *project.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="a7734-114">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="a7734-115">Alle Verzeichnisse, die in der *global.json*-Datei angegeben sind, indem ein Pfad zur *global.json*-Datei übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a7734-115">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="a7734-116">Ein *solution.sln*-Datei, in dem die Projekte, auf die in der Projektmappe verwiesen wird, migriert werden.</span><span class="sxs-lookup"><span data-stu-id="a7734-116">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="a7734-117">Rekursiv für alle Unterverzeichnisse im angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a7734-117">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="a7734-118">Der `dotnet migrate`-Befehl speichert die migrierte *project.json*-Datei in einem `backup`-Verzeichnis, das erstellt wird, falls das Verzeichnis noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a7734-118">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="a7734-119">Das Verhalten wird mithilfe der `--skip-backup`-Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7734-119">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="a7734-120">Standardmäßig gibt der Migrationsvorgang den Status der Migration in die Standardausgabe (STDOUT) aus.</span><span class="sxs-lookup"><span data-stu-id="a7734-120">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="a7734-121">Bei Verwendung der `--report-file <REPORT_FILE>`-Option wird die Ausgabe in die angegebene Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a7734-121">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="a7734-122">Der `dotnet migrate`-Befehl unterstützt nur gültige *project.json*-basiere Projekte von Preview 2.</span><span class="sxs-lookup"><span data-stu-id="a7734-122">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="a7734-123">Dies bedeutet, dass Sie ihn nicht zum Migrieren von *project.json*-basierten Projekte von DNX oder Preview 1 direkt an MSBuild/csproj-Projekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a7734-123">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="a7734-124">Sie müssen zuerst das Projekt manuell auf ein *project.json*-basiertes Projekt von Preview 2 migrieren und anschließend den `dotnet migrate`-Befehl verwenden, um das Projekt zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="a7734-124">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="a7734-125">Argumente</span><span class="sxs-lookup"><span data-stu-id="a7734-125">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="a7734-126">Der Pfad zu einem der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="a7734-126">The path to one of the following:</span></span>

* <span data-ttu-id="a7734-127">eine *project.json*-Datei zum Migrieren.</span><span class="sxs-lookup"><span data-stu-id="a7734-127">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="a7734-128">eine *global.json*-Datei. Die in *global.json* angegebenen Ordner werden migriert.</span><span class="sxs-lookup"><span data-stu-id="a7734-128">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="a7734-129">eine *solution.sln*-Datei. Die in der Projektmappe referenzierten Projekte werden migriert.</span><span class="sxs-lookup"><span data-stu-id="a7734-129">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="a7734-130">ein zu migrierendes Verzeichnis. Sucht rekursiv nach *project.json*-Dateien, um diese im angegebenen Verzeichnis zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="a7734-130">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="a7734-131">Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="a7734-131">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="a7734-132">Optionen</span><span class="sxs-lookup"><span data-stu-id="a7734-132">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="a7734-133">Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a7734-133">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="a7734-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="a7734-134">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="a7734-135">Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a7734-135">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="a7734-136">Die Migration von Projektverweisen wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="a7734-136">Skip migrating project references.</span></span> <span data-ttu-id="a7734-137">Standardmäßig werden Projektverweise rekursiv migriert.</span><span class="sxs-lookup"><span data-stu-id="a7734-137">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="a7734-138">Das Verschieben der Dateien *project.json*, *global.json* und *\*.xproj* in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="a7734-138">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="a7734-139">Für die Migration zu verwendende CSPROJ-Vorlagendatei.</span><span class="sxs-lookup"><span data-stu-id="a7734-139">Template csproj file to use for migration.</span></span> <span data-ttu-id="a7734-140">Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a7734-140">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="a7734-141">Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a7734-141">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="a7734-142">Der Standardwert ist die Version des SDK in `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="a7734-142">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="a7734-143">Der Pfad zur XPROJ-Datei, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7734-143">The path to the xproj file to use.</span></span> <span data-ttu-id="a7734-144">Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a7734-144">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="a7734-145">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a7734-145">Examples</span></span>

<span data-ttu-id="a7734-146">Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="a7734-146">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="a7734-147">Migrieren Sie alle Projekte, die die *global.json*-Datei umfasst:</span><span class="sxs-lookup"><span data-stu-id="a7734-147">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="a7734-148">Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten (P2P).</span><span class="sxs-lookup"><span data-stu-id="a7734-148">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="a7734-149">Verwenden Sie außerdem eine bestimmte SDK-Version:</span><span class="sxs-lookup"><span data-stu-id="a7734-149">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
