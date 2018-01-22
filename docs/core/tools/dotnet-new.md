---
title: "dotnet new Befehl – .NET Core-CLI"
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
keywords: dotnet-new, CLI, CLI-Befehl, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.workload: dotnetcore
ms.openlocfilehash: cf65dc80f135badcb1580726a12a9ae9d94ae3d7
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/20/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="9ba49-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9ba49-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9ba49-105">name</span><span class="sxs-lookup"><span data-stu-id="9ba49-105">Name</span></span>

<span data-ttu-id="9ba49-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="9ba49-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9ba49-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9ba49-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9ba49-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ba49-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="9ba49-110">description</span><span class="sxs-lookup"><span data-stu-id="9ba49-110">Description</span></span>

<span data-ttu-id="9ba49-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9ba49-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="9ba49-112">Der Befehl ruft das [Vorlagenmodul](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="9ba49-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="9ba49-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="9ba49-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="9ba49-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9ba49-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="9ba49-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="9ba49-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="9ba49-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="9ba49-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9ba49-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="9ba49-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9ba49-118">The command contains a default list of templates.</span></span> <span data-ttu-id="9ba49-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ba49-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9ba49-120">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem .NET Core 2.0 SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="9ba49-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="9ba49-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ba49-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9ba49-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9ba49-122">Template description</span></span>                          | <span data-ttu-id="9ba49-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="9ba49-123">Template name</span></span> | <span data-ttu-id="9ba49-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="9ba49-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="9ba49-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="9ba49-125">Console application</span></span>                          | `console`     | <span data-ttu-id="9ba49-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ba49-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9ba49-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ba49-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="9ba49-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ba49-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9ba49-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="9ba49-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ba49-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9ba49-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="9ba49-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ba49-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9ba49-133">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="9ba49-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="9ba49-134">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-134">[C#], F#</span></span>      |
| <span data-ttu-id="9ba49-135">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9ba49-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="9ba49-136">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-136">[C#], F#</span></span>      |
| <span data-ttu-id="9ba49-137">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="9ba49-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="9ba49-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ba49-138">[C#]</span></span>          |
| <span data-ttu-id="9ba49-139">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="9ba49-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="9ba49-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ba49-140">[C#]</span></span>          |
| <span data-ttu-id="9ba49-141">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="9ba49-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="9ba49-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ba49-142">[C#]</span></span>          |
| <span data-ttu-id="9ba49-143">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="9ba49-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="9ba49-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ba49-144">[C#]</span></span>          |
| <span data-ttu-id="9ba49-145">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="9ba49-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="9ba49-146">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-146">[C#], F#</span></span>      |
| <span data-ttu-id="9ba49-147">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="9ba49-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="9ba49-148">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ba49-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="9ba49-149">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ba49-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="9ba49-150">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="9ba49-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="9ba49-151">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="9ba49-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="9ba49-152">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="9ba49-152">MVC/ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="9ba49-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9ba49-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ba49-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9ba49-155">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9ba49-155">The command contains a default list of templates.</span></span> <span data-ttu-id="9ba49-156">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ba49-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="9ba49-157">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem .NET Core 1.x SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="9ba49-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="9ba49-158">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ba49-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9ba49-159">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="9ba49-159">Template description</span></span>  | <span data-ttu-id="9ba49-160">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="9ba49-160">Template name</span></span> | <span data-ttu-id="9ba49-161">Sprachen</span><span class="sxs-lookup"><span data-stu-id="9ba49-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="9ba49-162">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="9ba49-162">Console application</span></span>  | `console`     | <span data-ttu-id="9ba49-163">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-163">[C#], F#</span></span>  |
| <span data-ttu-id="9ba49-164">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ba49-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="9ba49-165">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-165">[C#], F#</span></span>  |
| <span data-ttu-id="9ba49-166">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="9ba49-167">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-167">[C#], F#</span></span>  |
| <span data-ttu-id="9ba49-168">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="9ba49-169">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-169">[C#], F#</span></span>  |
| <span data-ttu-id="9ba49-170">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="9ba49-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="9ba49-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ba49-171">[C#]</span></span>      |
| <span data-ttu-id="9ba49-172">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="9ba49-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="9ba49-173">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ba49-173">[C#], F#</span></span>  |
| <span data-ttu-id="9ba49-174">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="9ba49-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="9ba49-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ba49-175">[C#]</span></span>      |
| <span data-ttu-id="9ba49-176">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ba49-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="9ba49-177">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ba49-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="9ba49-178">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="9ba49-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="9ba49-179">Optionen</span><span class="sxs-lookup"><span data-stu-id="9ba49-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9ba49-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="9ba49-181">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9ba49-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9ba49-182">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9ba49-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9ba49-183">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ba49-183">Prints out help for the command.</span></span> <span data-ttu-id="9ba49-184">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ba49-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9ba49-185">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9ba49-186">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9ba49-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9ba49-187">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ba49-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="9ba49-188">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ba49-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9ba49-189">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="9ba49-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9ba49-190">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="9ba49-190">The language of the template to create.</span></span> <span data-ttu-id="9ba49-191">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9ba49-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9ba49-192">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9ba49-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9ba49-193">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-193">The name for the created output.</span></span> <span data-ttu-id="9ba49-194">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ba49-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9ba49-195">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-195">Location to place the generated output.</span></span> <span data-ttu-id="9ba49-196">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ba49-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9ba49-197">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="9ba49-197">Filters templates based on available types.</span></span> <span data-ttu-id="9ba49-198">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="9ba49-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9ba49-199">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="9ba49-200">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="9ba49-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9ba49-201">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="9ba49-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="9ba49-202">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="9ba49-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ba49-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="9ba49-204">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="9ba49-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="9ba49-205">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="9ba49-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="9ba49-206">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9ba49-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9ba49-207">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ba49-207">Prints out help for the command.</span></span> <span data-ttu-id="9ba49-208">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ba49-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="9ba49-209">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ba49-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="9ba49-210">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ba49-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9ba49-211">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="9ba49-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="9ba49-212">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="9ba49-212">The language of the template to create.</span></span> <span data-ttu-id="9ba49-213">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9ba49-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9ba49-214">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9ba49-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9ba49-215">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-215">The name for the created output.</span></span> <span data-ttu-id="9ba49-216">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ba49-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9ba49-217">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-217">Location to place the generated output.</span></span> <span data-ttu-id="9ba49-218">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ba49-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="9ba49-219">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="9ba49-219">Template options</span></span>

<span data-ttu-id="9ba49-220">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="9ba49-220">Each project template may have additional options available.</span></span> <span data-ttu-id="9ba49-221">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="9ba49-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9ba49-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="9ba49-223">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="9ba49-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="9ba49-224">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ba49-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9ba49-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9ba49-225">**classlib**</span></span>

<span data-ttu-id="9ba49-226">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ba49-227">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ba49-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9ba49-228">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9ba49-229">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ba49-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9ba49-230">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9ba49-230">**mstest, xunit**</span></span>

<span data-ttu-id="9ba49-231">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9ba49-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9ba49-232">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ba49-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9ba49-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9ba49-233">**globaljson**</span></span>

<span data-ttu-id="9ba49-234">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="9ba49-235">**web**</span><span class="sxs-lookup"><span data-stu-id="9ba49-235">**web**</span></span>

<span data-ttu-id="9ba49-236">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9ba49-237">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ba49-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9ba49-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9ba49-238">**webapi**</span></span>

<span data-ttu-id="9ba49-239">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ba49-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ba49-240">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ba49-240">The possible values are:</span></span>

- <span data-ttu-id="9ba49-241">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ba49-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ba49-242">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ba49-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ba49-243">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ba49-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ba49-244">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ba49-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ba49-245">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ba49-246">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ba49-247">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ba49-248">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ba49-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ba49-249">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ba49-250">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ba49-251">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ba49-252">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ba49-253">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ba49-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ba49-254">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9ba49-255">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ba49-256">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ba49-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ba49-257">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ba49-258">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ba49-259">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ba49-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ba49-260">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ba49-261">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ba49-262">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ba49-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ba49-263">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ba49-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ba49-264">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9ba49-265">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ba49-266">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ba49-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ba49-267">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ba49-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9ba49-268">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="9ba49-268">**mvc, razor**</span></span>

<span data-ttu-id="9ba49-269">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ba49-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ba49-270">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ba49-270">The possible values are:</span></span>

- <span data-ttu-id="9ba49-271">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ba49-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ba49-272">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ba49-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9ba49-273">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ba49-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ba49-274">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ba49-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ba49-275">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ba49-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9ba49-276">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ba49-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ba49-277">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ba49-278">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ba49-279">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="9ba49-280">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ba49-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ba49-281">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ba49-282">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9ba49-283">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ba49-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ba49-284">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9ba49-285">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ba49-286">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ba49-287">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ba49-288">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ba49-289">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ba49-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ba49-290">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ba49-291">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ba49-292">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ba49-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ba49-293">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="9ba49-294">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ba49-295">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ba49-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ba49-296">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="9ba49-297">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ba49-298">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ba49-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9ba49-299">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ba49-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="9ba49-300">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9ba49-301">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ba49-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ba49-302">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ba49-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ba49-303">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ba49-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9ba49-304">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="9ba49-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="9ba49-305">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ba49-306">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ba49-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ba49-307">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ba49-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9ba49-308">**page**</span><span class="sxs-lookup"><span data-stu-id="9ba49-308">**page**</span></span>

<span data-ttu-id="9ba49-309">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ba49-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9ba49-310">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9ba49-311">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="9ba49-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9ba49-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9ba49-312">**viewimports**</span></span>

<span data-ttu-id="9ba49-313">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ba49-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9ba49-314">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ba49-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ba49-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9ba49-316">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="9ba49-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="9ba49-317">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ba49-318">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="9ba49-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9ba49-319">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9ba49-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9ba49-320">**classlib**</span></span>

<span data-ttu-id="9ba49-321">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ba49-322">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="9ba49-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="9ba49-323">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="9ba49-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="9ba49-324">**mvc**</span></span>

<span data-ttu-id="9ba49-325">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ba49-326">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="9ba49-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9ba49-327">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9ba49-328">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ba49-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="9ba49-329">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="9ba49-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="9ba49-330">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-330">The default value is `None`.</span></span>

<span data-ttu-id="9ba49-331">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba49-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="9ba49-332">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="9ba49-332">Values: `true` or `false`.</span></span> <span data-ttu-id="9ba49-333">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="9ba49-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="9ba49-334">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9ba49-334">Examples</span></span>

<span data-ttu-id="9ba49-335">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="9ba49-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="9ba49-336">Erstellen Sie ein neues .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core 2.0 SDK oder höher verfügbar)</span><span class="sxs-lookup"><span data-stu-id="9ba49-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="9ba49-337">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 2.0 verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="9ba49-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="9ba49-338">Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 2.0 vorgesehen ist:</span><span class="sxs-lookup"><span data-stu-id="9ba49-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="9ba49-339">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="9ba49-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="9ba49-340">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ba49-340">See also</span></span>

[<span data-ttu-id="9ba49-341">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="9ba49-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="9ba49-342">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="9ba49-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="9ba49-343">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="9ba49-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="9ba49-344">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="9ba49-344">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
