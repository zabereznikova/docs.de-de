---
title: "dotnet-new-Befehl – .NET Core-CLI"
description: Der dotnet-new-Befehl erstellt neue .NET Core-Projekte im aktuellen Verzeichnis.
keywords: dotnet-new, CLI, CLI-Befehl, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56033295b2448b045d5a51dbd84d5429aed77451
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-new"></a><span data-ttu-id="8e69b-104">dotnet-new</span><span class="sxs-lookup"><span data-stu-id="8e69b-104">dotnet-new</span></span>

## <a name="name"></a><span data-ttu-id="8e69b-105">Name</span><span class="sxs-lookup"><span data-stu-id="8e69b-105">Name</span></span>

<span data-ttu-id="8e69b-106">`dotnet-new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="8e69b-106">`dotnet-new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8e69b-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8e69b-107">Synopsis</span></span>

```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="8e69b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8e69b-108">Description</span></span>

<span data-ttu-id="8e69b-109">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="8e69b-109">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="8e69b-110">Der Befehl ruft das [Vorlagenmodul](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="8e69b-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="8e69b-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="8e69b-111">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="8e69b-112">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8e69b-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="8e69b-113">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="8e69b-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="8e69b-114">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="8e69b-114">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="8e69b-115">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="8e69b-115">The command contains a default list of templates.</span></span> <span data-ttu-id="8e69b-116">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8e69b-116">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="8e69b-117">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="8e69b-117">The following table shows the templates that come pre-installed with the SDK.</span></span> <span data-ttu-id="8e69b-118">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8e69b-118">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="8e69b-119">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="8e69b-119">Template description</span></span>  | <span data-ttu-id="8e69b-120">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="8e69b-120">Template name</span></span>  | <span data-ttu-id="8e69b-121">Sprachen</span><span class="sxs-lookup"><span data-stu-id="8e69b-121">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="8e69b-122">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="8e69b-122">Console application</span></span>  | <span data-ttu-id="8e69b-123">Konsole</span><span class="sxs-lookup"><span data-stu-id="8e69b-123">console</span></span>        | <span data-ttu-id="8e69b-124">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e69b-124">[C#], F#</span></span>  |
| <span data-ttu-id="8e69b-125">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="8e69b-125">Class library</span></span>        | <span data-ttu-id="8e69b-126">classlib</span><span class="sxs-lookup"><span data-stu-id="8e69b-126">classlib</span></span>       | <span data-ttu-id="8e69b-127">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e69b-127">[C#], F#</span></span>  |
| <span data-ttu-id="8e69b-128">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="8e69b-128">Unit test project</span></span>    | <span data-ttu-id="8e69b-129">mstest</span><span class="sxs-lookup"><span data-stu-id="8e69b-129">mstest</span></span>         | <span data-ttu-id="8e69b-130">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e69b-130">[C#], F#</span></span>  |
| <span data-ttu-id="8e69b-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="8e69b-131">xUnit test project</span></span>   | <span data-ttu-id="8e69b-132">xunit</span><span class="sxs-lookup"><span data-stu-id="8e69b-132">xunit</span></span>          | <span data-ttu-id="8e69b-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e69b-133">[C#], F#</span></span>  |
| <span data-ttu-id="8e69b-134">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="8e69b-134">ASP.NET Core empty</span></span>   | <span data-ttu-id="8e69b-135">Web</span><span class="sxs-lookup"><span data-stu-id="8e69b-135">web</span></span>            | <span data-ttu-id="8e69b-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e69b-136">[C#]</span></span>      |
| <span data-ttu-id="8e69b-137">ASP.NET Core-Webapp</span><span class="sxs-lookup"><span data-stu-id="8e69b-137">ASP.NET Core web app</span></span> | <span data-ttu-id="8e69b-138">MVC</span><span class="sxs-lookup"><span data-stu-id="8e69b-138">mvc</span></span>            | <span data-ttu-id="8e69b-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8e69b-139">[C#], F#</span></span>  |
| <span data-ttu-id="8e69b-140">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="8e69b-140">ASP.NET Core web api</span></span> | <span data-ttu-id="8e69b-141">Web-API</span><span class="sxs-lookup"><span data-stu-id="8e69b-141">webapi</span></span>         | <span data-ttu-id="8e69b-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="8e69b-142">[C#]</span></span>      |
| <span data-ttu-id="8e69b-143">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8e69b-143">Nuget config</span></span>         | <span data-ttu-id="8e69b-144">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="8e69b-144">nugetconfig</span></span>    |           |
| <span data-ttu-id="8e69b-145">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8e69b-145">Web config</span></span>           | <span data-ttu-id="8e69b-146">webconfig</span><span class="sxs-lookup"><span data-stu-id="8e69b-146">webconfig</span></span>      |           |
| <span data-ttu-id="8e69b-147">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="8e69b-147">Solution file</span></span>        | <span data-ttu-id="8e69b-148">sln</span><span class="sxs-lookup"><span data-stu-id="8e69b-148">sln</span></span>            |           |

## <a name="options"></a><span data-ttu-id="8e69b-149">Optionen</span><span class="sxs-lookup"><span data-stu-id="8e69b-149">Options</span></span>

`-h|--help`

<span data-ttu-id="8e69b-150">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8e69b-150">Prints out help for the command.</span></span> <span data-ttu-id="8e69b-151">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8e69b-151">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="8e69b-152">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e69b-152">Lists templates containing the specified name.</span></span> <span data-ttu-id="8e69b-153">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8e69b-153">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8e69b-154">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="8e69b-154">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="8e69b-155">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="8e69b-155">The language of the template to create.</span></span> <span data-ttu-id="8e69b-156">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="8e69b-156">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8e69b-157">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="8e69b-157">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8e69b-158">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8e69b-158">The name for the created output.</span></span> <span data-ttu-id="8e69b-159">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e69b-159">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8e69b-160">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="8e69b-160">Location to place the generated output.</span></span> <span data-ttu-id="8e69b-161">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8e69b-161">The default is the current directory.</span></span>

`-all|--show-all`

<span data-ttu-id="8e69b-162">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="8e69b-162">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="8e69b-163">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="8e69b-163">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="8e69b-164">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="8e69b-164">This is required when the output directory already contains a project.</span></span>

## <a name="template-options"></a><span data-ttu-id="8e69b-165">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="8e69b-165">Template options</span></span>

<span data-ttu-id="8e69b-166">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="8e69b-166">Each project template may have additional options available.</span></span> <span data-ttu-id="8e69b-167">Die Core-Vorlagen haben die folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="8e69b-167">The core templates have the following options:</span></span>

<span data-ttu-id="8e69b-168">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="8e69b-168">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="8e69b-169">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e69b-169">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e69b-170">Werte: `netcoreapp1.0` oder `netcoreapp1.1` (Standard: `netcoreapp1.0`)</span><span class="sxs-lookup"><span data-stu-id="8e69b-170">Values: `netcoreapp1.0` or `netcoreapp1.1` (Default: `netcoreapp1.0`)</span></span>

<span data-ttu-id="8e69b-171">**mvc**</span><span class="sxs-lookup"><span data-stu-id="8e69b-171">**mvc**</span></span>

<span data-ttu-id="8e69b-172">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e69b-172">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e69b-173">Werte: `netcoreapp1.0` oder `netcoreapp1.1` (`Default: netcoreapp1.0`)</span><span class="sxs-lookup"><span data-stu-id="8e69b-173">Values: `netcoreapp1.0` or `netcoreapp1.1` (`Default: netcoreapp1.0`)</span></span>

<span data-ttu-id="8e69b-174">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="8e69b-174">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="8e69b-175">Werte: `None` oder `Individual` (Standard: `None`)</span><span class="sxs-lookup"><span data-stu-id="8e69b-175">Values: `None` or `Individual` (Default: `None`)</span></span>

<span data-ttu-id="8e69b-176">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e69b-176">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="8e69b-177">Werte: `true` oder `false` (Standard: `false`)</span><span class="sxs-lookup"><span data-stu-id="8e69b-177">Values: `true` or `false` (Default: `false`)</span></span>

<span data-ttu-id="8e69b-178">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8e69b-178">**classlib**</span></span>

<span data-ttu-id="8e69b-179">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8e69b-179">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8e69b-180">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6` (Standard: `netstandard1.4`)</span><span class="sxs-lookup"><span data-stu-id="8e69b-180">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6` (Default: `netstandard1.4`)</span></span>

## <a name="examples"></a><span data-ttu-id="8e69b-181">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8e69b-181">Examples</span></span>

<span data-ttu-id="8e69b-182">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="8e69b-182">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#` 
   
<span data-ttu-id="8e69b-183">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 1.0 verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="8e69b-183">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 1.0:</span></span>  

`dotnet new mvc -au None -f netcoreapp1.0`
 
<span data-ttu-id="8e69b-184">Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 1.1 vorgesehen ist:</span><span class="sxs-lookup"><span data-stu-id="8e69b-184">Create a new xUnit application targeting .NET Core 1.1:</span></span>

`dotnet new xunit --framework netcoreapp1.1`

<span data-ttu-id="8e69b-185">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="8e69b-185">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

