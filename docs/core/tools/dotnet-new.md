---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: ab8d6f779a428aab7bd2739105dcf08b51d14ab9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="63e9b-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="63e9b-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="63e9b-104">name</span><span class="sxs-lookup"><span data-stu-id="63e9b-104">Name</span></span>

<span data-ttu-id="63e9b-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="63e9b-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="63e9b-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="63e9b-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="63e9b-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="63e9b-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="63e9b-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="63e9b-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="63e9b-109">description</span><span class="sxs-lookup"><span data-stu-id="63e9b-109">Description</span></span>

<span data-ttu-id="63e9b-110">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="63e9b-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="63e9b-111">Der Befehl ruft das [Vorlagenmodul](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="63e9b-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="63e9b-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="63e9b-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="63e9b-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="63e9b-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="63e9b-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="63e9b-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="63e9b-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="63e9b-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="63e9b-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="63e9b-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="63e9b-117">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="63e9b-117">The command contains a default list of templates.</span></span> <span data-ttu-id="63e9b-118">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63e9b-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="63e9b-119">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem .NET Core 2.0 SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="63e9b-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="63e9b-120">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="63e9b-121">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="63e9b-121">Template description</span></span>                          | <span data-ttu-id="63e9b-122">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="63e9b-122">Template name</span></span> | <span data-ttu-id="63e9b-123">Sprachen</span><span class="sxs-lookup"><span data-stu-id="63e9b-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="63e9b-124">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="63e9b-124">Console application</span></span>                          | `console`     | <span data-ttu-id="63e9b-125">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="63e9b-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="63e9b-126">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="63e9b-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="63e9b-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="63e9b-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="63e9b-128">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="63e9b-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="63e9b-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="63e9b-130">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="63e9b-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="63e9b-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="63e9b-132">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="63e9b-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="63e9b-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-133">[C#], F#</span></span>      |
| <span data-ttu-id="63e9b-134">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="63e9b-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="63e9b-135">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-135">[C#], F#</span></span>      |
| <span data-ttu-id="63e9b-136">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="63e9b-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="63e9b-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="63e9b-137">[C#]</span></span>          |
| <span data-ttu-id="63e9b-138">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="63e9b-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="63e9b-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="63e9b-139">[C#]</span></span>          |
| <span data-ttu-id="63e9b-140">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="63e9b-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="63e9b-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="63e9b-141">[C#]</span></span>          |
| <span data-ttu-id="63e9b-142">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="63e9b-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="63e9b-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="63e9b-143">[C#]</span></span>          |
| <span data-ttu-id="63e9b-144">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="63e9b-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="63e9b-145">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-145">[C#], F#</span></span>      |
| <span data-ttu-id="63e9b-146">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="63e9b-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="63e9b-147">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="63e9b-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="63e9b-148">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="63e9b-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="63e9b-149">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="63e9b-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="63e9b-150">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="63e9b-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="63e9b-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="63e9b-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="63e9b-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="63e9b-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="63e9b-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="63e9b-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="63e9b-154">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="63e9b-154">The command contains a default list of templates.</span></span> <span data-ttu-id="63e9b-155">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63e9b-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="63e9b-156">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem .NET Core 1.x SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="63e9b-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="63e9b-157">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="63e9b-158">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="63e9b-158">Template description</span></span>  | <span data-ttu-id="63e9b-159">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="63e9b-159">Template name</span></span> | <span data-ttu-id="63e9b-160">Sprachen</span><span class="sxs-lookup"><span data-stu-id="63e9b-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="63e9b-161">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="63e9b-161">Console application</span></span>  | `console`     | <span data-ttu-id="63e9b-162">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-162">[C#], F#</span></span>  |
| <span data-ttu-id="63e9b-163">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="63e9b-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="63e9b-164">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-164">[C#], F#</span></span>  |
| <span data-ttu-id="63e9b-165">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="63e9b-166">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-166">[C#], F#</span></span>  |
| <span data-ttu-id="63e9b-167">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="63e9b-168">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-168">[C#], F#</span></span>  |
| <span data-ttu-id="63e9b-169">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="63e9b-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="63e9b-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="63e9b-170">[C#]</span></span>      |
| <span data-ttu-id="63e9b-171">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="63e9b-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="63e9b-172">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="63e9b-172">[C#], F#</span></span>  |
| <span data-ttu-id="63e9b-173">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="63e9b-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="63e9b-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="63e9b-174">[C#]</span></span>      |
| <span data-ttu-id="63e9b-175">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="63e9b-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="63e9b-176">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="63e9b-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="63e9b-177">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="63e9b-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="63e9b-178">Optionen</span><span class="sxs-lookup"><span data-stu-id="63e9b-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="63e9b-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="63e9b-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="63e9b-180">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63e9b-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="63e9b-181">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="63e9b-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="63e9b-182">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="63e9b-182">Prints out help for the command.</span></span> <span data-ttu-id="63e9b-183">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="63e9b-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="63e9b-184">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="63e9b-185">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="63e9b-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="63e9b-186">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="63e9b-187">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="63e9b-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="63e9b-188">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="63e9b-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="63e9b-189">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="63e9b-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="63e9b-190">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="63e9b-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="63e9b-191">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="63e9b-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="63e9b-192">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="63e9b-192">The language of the template to create.</span></span> <span data-ttu-id="63e9b-193">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="63e9b-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="63e9b-194">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="63e9b-194">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="63e9b-195">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-195">The name for the created output.</span></span> <span data-ttu-id="63e9b-196">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="63e9b-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="63e9b-197">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-197">Location to place the generated output.</span></span> <span data-ttu-id="63e9b-198">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="63e9b-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="63e9b-199">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="63e9b-199">Filters templates based on available types.</span></span> <span data-ttu-id="63e9b-200">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="63e9b-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="63e9b-201">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="63e9b-202">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="63e9b-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="63e9b-203">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="63e9b-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="63e9b-204">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="63e9b-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="63e9b-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="63e9b-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="63e9b-206">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="63e9b-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="63e9b-207">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="63e9b-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="63e9b-208">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="63e9b-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="63e9b-209">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="63e9b-209">Prints out help for the command.</span></span> <span data-ttu-id="63e9b-210">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="63e9b-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="63e9b-211">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="63e9b-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="63e9b-212">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="63e9b-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="63e9b-213">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="63e9b-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="63e9b-214">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="63e9b-214">The language of the template to create.</span></span> <span data-ttu-id="63e9b-215">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="63e9b-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="63e9b-216">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="63e9b-216">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="63e9b-217">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-217">The name for the created output.</span></span> <span data-ttu-id="63e9b-218">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="63e9b-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="63e9b-219">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-219">Location to place the generated output.</span></span> <span data-ttu-id="63e9b-220">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="63e9b-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="63e9b-221">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="63e9b-221">Template options</span></span>

<span data-ttu-id="63e9b-222">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="63e9b-222">Each project template may have additional options available.</span></span> <span data-ttu-id="63e9b-223">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="63e9b-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="63e9b-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="63e9b-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="63e9b-225">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="63e9b-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="63e9b-226">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="63e9b-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="63e9b-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="63e9b-227">**classlib**</span></span>

<span data-ttu-id="63e9b-228">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="63e9b-229">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="63e9b-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="63e9b-230">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="63e9b-231">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="63e9b-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="63e9b-232">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="63e9b-232">**mstest, xunit**</span></span>

<span data-ttu-id="63e9b-233">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="63e9b-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="63e9b-234">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="63e9b-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="63e9b-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="63e9b-235">**globaljson**</span></span>

<span data-ttu-id="63e9b-236">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="63e9b-237">**web**</span><span class="sxs-lookup"><span data-stu-id="63e9b-237">**web**</span></span>

<span data-ttu-id="63e9b-238">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="63e9b-239">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="63e9b-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="63e9b-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="63e9b-240">**webapi**</span></span>

<span data-ttu-id="63e9b-241">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="63e9b-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="63e9b-242">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="63e9b-242">The possible values are:</span></span>

- <span data-ttu-id="63e9b-243">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="63e9b-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="63e9b-244">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="63e9b-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="63e9b-245">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="63e9b-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="63e9b-246">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="63e9b-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="63e9b-247">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="63e9b-248">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="63e9b-249">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="63e9b-250">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="63e9b-251">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="63e9b-252">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="63e9b-253">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="63e9b-254">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="63e9b-255">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="63e9b-256">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="63e9b-257">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="63e9b-258">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="63e9b-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="63e9b-259">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="63e9b-260">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="63e9b-261">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="63e9b-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="63e9b-262">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="63e9b-263">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="63e9b-264">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="63e9b-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="63e9b-265">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="63e9b-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="63e9b-266">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="63e9b-267">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="63e9b-268">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="63e9b-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="63e9b-269">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="63e9b-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="63e9b-270">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="63e9b-270">**mvc, razor**</span></span>

<span data-ttu-id="63e9b-271">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="63e9b-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="63e9b-272">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="63e9b-272">The possible values are:</span></span>

- <span data-ttu-id="63e9b-273">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="63e9b-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="63e9b-274">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="63e9b-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="63e9b-275">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="63e9b-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="63e9b-276">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="63e9b-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="63e9b-277">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="63e9b-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="63e9b-278">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="63e9b-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="63e9b-279">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="63e9b-280">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="63e9b-281">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="63e9b-282">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="63e9b-283">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="63e9b-284">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="63e9b-285">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="63e9b-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="63e9b-286">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="63e9b-287">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="63e9b-288">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="63e9b-289">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="63e9b-290">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="63e9b-291">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="63e9b-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="63e9b-292">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="63e9b-293">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="63e9b-294">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="63e9b-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="63e9b-295">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="63e9b-296">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="63e9b-297">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="63e9b-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="63e9b-298">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="63e9b-299">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="63e9b-300">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="63e9b-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="63e9b-301">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="63e9b-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="63e9b-302">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="63e9b-303">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="63e9b-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="63e9b-304">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="63e9b-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="63e9b-305">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="63e9b-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="63e9b-306">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="63e9b-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="63e9b-307">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="63e9b-308">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="63e9b-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="63e9b-309">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="63e9b-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="63e9b-310">**page**</span><span class="sxs-lookup"><span data-stu-id="63e9b-310">**page**</span></span>

<span data-ttu-id="63e9b-311">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="63e9b-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="63e9b-312">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="63e9b-313">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="63e9b-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="63e9b-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="63e9b-314">**viewimports**</span></span>

<span data-ttu-id="63e9b-315">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="63e9b-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="63e9b-316">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="63e9b-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="63e9b-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="63e9b-318">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="63e9b-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="63e9b-319">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="63e9b-320">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="63e9b-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="63e9b-321">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="63e9b-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="63e9b-322">**classlib**</span></span>

<span data-ttu-id="63e9b-323">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="63e9b-324">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="63e9b-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="63e9b-325">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="63e9b-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="63e9b-326">**mvc**</span></span>

<span data-ttu-id="63e9b-327">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="63e9b-328">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="63e9b-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="63e9b-329">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="63e9b-330">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="63e9b-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="63e9b-331">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="63e9b-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="63e9b-332">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-332">The default value is `None`.</span></span>

<span data-ttu-id="63e9b-333">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63e9b-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="63e9b-334">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="63e9b-334">Values: `true` or `false`.</span></span> <span data-ttu-id="63e9b-335">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="63e9b-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="63e9b-336">Beispiele</span><span class="sxs-lookup"><span data-stu-id="63e9b-336">Examples</span></span>

<span data-ttu-id="63e9b-337">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="63e9b-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="63e9b-338">Erstellen Sie ein neues .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core 2.0 SDK oder höher verfügbar)</span><span class="sxs-lookup"><span data-stu-id="63e9b-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="63e9b-339">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 2.0 verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="63e9b-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="63e9b-340">Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 2.0 vorgesehen ist:</span><span class="sxs-lookup"><span data-stu-id="63e9b-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="63e9b-341">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="63e9b-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="63e9b-342">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="63e9b-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="63e9b-343">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63e9b-343">See also</span></span>

[<span data-ttu-id="63e9b-344">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="63e9b-344">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="63e9b-345">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="63e9b-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="63e9b-346">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="63e9b-346">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="63e9b-347">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="63e9b-347">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
