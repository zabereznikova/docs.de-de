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
ms.openlocfilehash: f5815e1ad2a36a8ef3279f6ff83465dba9ec5d50
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="7de0d-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="7de0d-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7de0d-105">name</span><span class="sxs-lookup"><span data-stu-id="7de0d-105">Name</span></span>

<span data-ttu-id="7de0d-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="7de0d-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7de0d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="7de0d-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7de0d-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7de0d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="7de0d-110">description</span><span class="sxs-lookup"><span data-stu-id="7de0d-110">Description</span></span>

<span data-ttu-id="7de0d-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="7de0d-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="7de0d-112">Der Befehl ruft das [Vorlagenmodul](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="7de0d-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="7de0d-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="7de0d-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="7de0d-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="7de0d-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="7de0d-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="7de0d-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="7de0d-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="7de0d-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7de0d-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7de0d-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="7de0d-118">The command contains a default list of templates.</span></span> <span data-ttu-id="7de0d-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7de0d-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="7de0d-120">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem .NET Core 2.0 SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="7de0d-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="7de0d-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7de0d-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="7de0d-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="7de0d-122">Template description</span></span>                          | <span data-ttu-id="7de0d-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="7de0d-123">Template name</span></span>  | <span data-ttu-id="7de0d-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="7de0d-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="7de0d-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="7de0d-125">Console application</span></span>                          | <span data-ttu-id="7de0d-126">Konsole</span><span class="sxs-lookup"><span data-stu-id="7de0d-126">console</span></span>        | <span data-ttu-id="7de0d-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7de0d-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7de0d-128">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="7de0d-128">Class library</span></span>                                | <span data-ttu-id="7de0d-129">classlib</span><span class="sxs-lookup"><span data-stu-id="7de0d-129">classlib</span></span>       | <span data-ttu-id="7de0d-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7de0d-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7de0d-131">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-131">Unit test project</span></span>                            | <span data-ttu-id="7de0d-132">mstest</span><span class="sxs-lookup"><span data-stu-id="7de0d-132">mstest</span></span>         | <span data-ttu-id="7de0d-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7de0d-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7de0d-134">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-134">xUnit test project</span></span>                           | <span data-ttu-id="7de0d-135">xunit</span><span class="sxs-lookup"><span data-stu-id="7de0d-135">xunit</span></span>          | <span data-ttu-id="7de0d-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7de0d-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7de0d-137">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="7de0d-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="7de0d-138">Web</span><span class="sxs-lookup"><span data-stu-id="7de0d-138">web</span></span>            | <span data-ttu-id="7de0d-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-139">[C#], F#</span></span>      |
| <span data-ttu-id="7de0d-140">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="7de0d-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="7de0d-141">MVC</span><span class="sxs-lookup"><span data-stu-id="7de0d-141">mvc</span></span>            | <span data-ttu-id="7de0d-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-142">[C#], F#</span></span>      |
| <span data-ttu-id="7de0d-143">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="7de0d-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="7de0d-144">razor</span><span class="sxs-lookup"><span data-stu-id="7de0d-144">razor</span></span>          | <span data-ttu-id="7de0d-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="7de0d-145">[C#]</span></span>          |
| <span data-ttu-id="7de0d-146">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="7de0d-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="7de0d-147">angular</span><span class="sxs-lookup"><span data-stu-id="7de0d-147">angular</span></span>        | <span data-ttu-id="7de0d-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="7de0d-148">[C#]</span></span>          |
| <span data-ttu-id="7de0d-149">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="7de0d-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="7de0d-150">react</span><span class="sxs-lookup"><span data-stu-id="7de0d-150">react</span></span>          | <span data-ttu-id="7de0d-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="7de0d-151">[C#]</span></span>          |
| <span data-ttu-id="7de0d-152">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="7de0d-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="7de0d-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="7de0d-153">reactredux</span></span>     | <span data-ttu-id="7de0d-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="7de0d-154">[C#]</span></span>          |
| <span data-ttu-id="7de0d-155">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="7de0d-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="7de0d-156">Web-API</span><span class="sxs-lookup"><span data-stu-id="7de0d-156">webapi</span></span>         | <span data-ttu-id="7de0d-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-157">[C#], F#</span></span>      |
| <span data-ttu-id="7de0d-158">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="7de0d-158">global.json file</span></span>                             | <span data-ttu-id="7de0d-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="7de0d-159">globaljson</span></span>     |               |
| <span data-ttu-id="7de0d-160">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7de0d-160">Nuget config</span></span>                                 | <span data-ttu-id="7de0d-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="7de0d-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="7de0d-162">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7de0d-162">Web config</span></span>                                   | <span data-ttu-id="7de0d-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="7de0d-163">webconfig</span></span>      |               |
| <span data-ttu-id="7de0d-164">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="7de0d-164">Solution file</span></span>                                | <span data-ttu-id="7de0d-165">sln</span><span class="sxs-lookup"><span data-stu-id="7de0d-165">sln</span></span>            |               |
| <span data-ttu-id="7de0d-166">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="7de0d-166">Razor page</span></span>                                   | <span data-ttu-id="7de0d-167">Seite</span><span class="sxs-lookup"><span data-stu-id="7de0d-167">page</span></span>           |               |
| <span data-ttu-id="7de0d-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="7de0d-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="7de0d-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="7de0d-169">viewimports</span></span>    |               |
| <span data-ttu-id="7de0d-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="7de0d-170">MVC ViewStart</span></span>                                | <span data-ttu-id="7de0d-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="7de0d-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7de0d-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7de0d-173">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="7de0d-173">The command contains a default list of templates.</span></span> <span data-ttu-id="7de0d-174">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7de0d-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="7de0d-175">Die folgende Tabelle zeigt die Vorlagen, die bereits mit dem .NET Core 1.x SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="7de0d-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="7de0d-176">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7de0d-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="7de0d-177">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="7de0d-177">Template description</span></span>  | <span data-ttu-id="7de0d-178">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="7de0d-178">Template name</span></span>  | <span data-ttu-id="7de0d-179">Sprachen</span><span class="sxs-lookup"><span data-stu-id="7de0d-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="7de0d-180">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="7de0d-180">Console application</span></span>  | <span data-ttu-id="7de0d-181">Konsole</span><span class="sxs-lookup"><span data-stu-id="7de0d-181">console</span></span>        | <span data-ttu-id="7de0d-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-182">[C#], F#</span></span>  |
| <span data-ttu-id="7de0d-183">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="7de0d-183">Class library</span></span>        | <span data-ttu-id="7de0d-184">classlib</span><span class="sxs-lookup"><span data-stu-id="7de0d-184">classlib</span></span>       | <span data-ttu-id="7de0d-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-185">[C#], F#</span></span>  |
| <span data-ttu-id="7de0d-186">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-186">Unit test project</span></span>    | <span data-ttu-id="7de0d-187">mstest</span><span class="sxs-lookup"><span data-stu-id="7de0d-187">mstest</span></span>         | <span data-ttu-id="7de0d-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-188">[C#], F#</span></span>  |
| <span data-ttu-id="7de0d-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-189">xUnit test project</span></span>   | <span data-ttu-id="7de0d-190">xunit</span><span class="sxs-lookup"><span data-stu-id="7de0d-190">xunit</span></span>          | <span data-ttu-id="7de0d-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-191">[C#], F#</span></span>  |
| <span data-ttu-id="7de0d-192">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="7de0d-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="7de0d-193">Web</span><span class="sxs-lookup"><span data-stu-id="7de0d-193">web</span></span>            | <span data-ttu-id="7de0d-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="7de0d-194">[C#]</span></span>      |
| <span data-ttu-id="7de0d-195">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="7de0d-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="7de0d-196">MVC</span><span class="sxs-lookup"><span data-stu-id="7de0d-196">mvc</span></span>            | <span data-ttu-id="7de0d-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7de0d-197">[C#], F#</span></span>  |
| <span data-ttu-id="7de0d-198">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="7de0d-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="7de0d-199">Web-API</span><span class="sxs-lookup"><span data-stu-id="7de0d-199">webapi</span></span>         | <span data-ttu-id="7de0d-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="7de0d-200">[C#]</span></span>      |
| <span data-ttu-id="7de0d-201">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7de0d-201">Nuget config</span></span>         | <span data-ttu-id="7de0d-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="7de0d-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="7de0d-203">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7de0d-203">Web config</span></span>           | <span data-ttu-id="7de0d-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="7de0d-204">webconfig</span></span>      |           |
| <span data-ttu-id="7de0d-205">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="7de0d-205">Solution file</span></span>        | <span data-ttu-id="7de0d-206">sln</span><span class="sxs-lookup"><span data-stu-id="7de0d-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="7de0d-207">Optionen</span><span class="sxs-lookup"><span data-stu-id="7de0d-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7de0d-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="7de0d-209">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7de0d-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="7de0d-210">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="7de0d-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7de0d-211">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="7de0d-211">Prints out help for the command.</span></span> <span data-ttu-id="7de0d-212">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7de0d-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="7de0d-213">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7de0d-214">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="7de0d-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="7de0d-215">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7de0d-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="7de0d-216">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7de0d-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7de0d-217">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="7de0d-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="7de0d-218">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="7de0d-218">The language of the template to create.</span></span> <span data-ttu-id="7de0d-219">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7de0d-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7de0d-220">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="7de0d-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7de0d-221">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-221">The name for the created output.</span></span> <span data-ttu-id="7de0d-222">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="7de0d-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7de0d-223">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-223">Location to place the generated output.</span></span> <span data-ttu-id="7de0d-224">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7de0d-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="7de0d-225">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="7de0d-225">Filters templates based on available types.</span></span> <span data-ttu-id="7de0d-226">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="7de0d-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="7de0d-227">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="7de0d-228">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="7de0d-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="7de0d-229">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="7de0d-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="7de0d-230">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="7de0d-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7de0d-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="7de0d-232">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="7de0d-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="7de0d-233">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="7de0d-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="7de0d-234">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="7de0d-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7de0d-235">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="7de0d-235">Prints out help for the command.</span></span> <span data-ttu-id="7de0d-236">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7de0d-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="7de0d-237">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7de0d-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="7de0d-238">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7de0d-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7de0d-239">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="7de0d-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="7de0d-240">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="7de0d-240">The language of the template to create.</span></span> <span data-ttu-id="7de0d-241">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7de0d-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7de0d-242">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="7de0d-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7de0d-243">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-243">The name for the created output.</span></span> <span data-ttu-id="7de0d-244">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="7de0d-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7de0d-245">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-245">Location to place the generated output.</span></span> <span data-ttu-id="7de0d-246">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7de0d-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="7de0d-247">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="7de0d-247">Template options</span></span>

<span data-ttu-id="7de0d-248">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="7de0d-248">Each project template may have additional options available.</span></span> <span data-ttu-id="7de0d-249">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="7de0d-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7de0d-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7de0d-251">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="7de0d-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="7de0d-252">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="7de0d-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="7de0d-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7de0d-253">**classlib**</span></span>

<span data-ttu-id="7de0d-254">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7de0d-255">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7de0d-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="7de0d-256">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="7de0d-257">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="7de0d-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="7de0d-258">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="7de0d-258">**mstest, xunit**</span></span>

<span data-ttu-id="7de0d-259">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7de0d-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7de0d-260">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="7de0d-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="7de0d-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="7de0d-261">**globaljson**</span></span>

<span data-ttu-id="7de0d-262">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="7de0d-263">**web**</span><span class="sxs-lookup"><span data-stu-id="7de0d-263">**web**</span></span>

<span data-ttu-id="7de0d-264">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7de0d-265">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="7de0d-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="7de0d-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="7de0d-266">**webapi**</span></span>

<span data-ttu-id="7de0d-267">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="7de0d-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7de0d-268">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7de0d-268">The possible values are:</span></span>

- <span data-ttu-id="7de0d-269">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="7de0d-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7de0d-270">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="7de0d-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7de0d-271">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="7de0d-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7de0d-272">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7de0d-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7de0d-273">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7de0d-274">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7de0d-275">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7de0d-276">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="7de0d-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7de0d-277">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7de0d-278">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7de0d-279">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7de0d-280">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7de0d-281">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="7de0d-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7de0d-282">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="7de0d-283">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7de0d-284">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="7de0d-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7de0d-285">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7de0d-286">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7de0d-287">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="7de0d-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7de0d-288">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7de0d-289">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7de0d-290">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7de0d-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7de0d-291">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7de0d-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7de0d-292">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7de0d-293">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7de0d-294">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7de0d-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7de0d-295">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="7de0d-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="7de0d-296">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="7de0d-296">**mvc, razor**</span></span>

<span data-ttu-id="7de0d-297">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="7de0d-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7de0d-298">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="7de0d-298">The possible values are:</span></span>

- <span data-ttu-id="7de0d-299">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="7de0d-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7de0d-300">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7de0d-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="7de0d-301">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="7de0d-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7de0d-302">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="7de0d-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7de0d-303">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="7de0d-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="7de0d-304">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7de0d-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7de0d-305">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7de0d-306">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7de0d-307">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="7de0d-308">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="7de0d-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7de0d-309">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7de0d-310">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="7de0d-311">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="7de0d-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7de0d-312">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="7de0d-313">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7de0d-314">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7de0d-315">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="7de0d-316">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7de0d-317">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="7de0d-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7de0d-318">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="7de0d-319">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7de0d-320">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="7de0d-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7de0d-321">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="7de0d-322">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7de0d-323">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="7de0d-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7de0d-324">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="7de0d-325">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7de0d-326">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7de0d-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="7de0d-327">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="7de0d-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="7de0d-328">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="7de0d-329">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7de0d-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7de0d-330">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7de0d-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7de0d-331">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="7de0d-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7de0d-332">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="7de0d-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="7de0d-333">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7de0d-334">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="7de0d-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7de0d-335">`--no-restore`: führt eine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="7de0d-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="7de0d-336">**page**</span><span class="sxs-lookup"><span data-stu-id="7de0d-336">**page**</span></span>

<span data-ttu-id="7de0d-337">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="7de0d-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7de0d-338">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7de0d-339">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="7de0d-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="7de0d-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="7de0d-340">**viewimports**</span></span>

<span data-ttu-id="7de0d-341">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="7de0d-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7de0d-342">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7de0d-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7de0d-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7de0d-344">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="7de0d-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="7de0d-345">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7de0d-346">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="7de0d-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="7de0d-347">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="7de0d-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7de0d-348">**classlib**</span></span>

<span data-ttu-id="7de0d-349">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7de0d-350">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="7de0d-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="7de0d-351">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="7de0d-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="7de0d-352">**mvc**</span></span>

<span data-ttu-id="7de0d-353">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7de0d-354">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="7de0d-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="7de0d-355">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="7de0d-356">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="7de0d-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="7de0d-357">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="7de0d-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="7de0d-358">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-358">The default value is `None`.</span></span>

<span data-ttu-id="7de0d-359">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7de0d-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="7de0d-360">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="7de0d-360">Values: `true` or `false`.</span></span> <span data-ttu-id="7de0d-361">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="7de0d-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7de0d-362">Beispiele</span><span class="sxs-lookup"><span data-stu-id="7de0d-362">Examples</span></span>

<span data-ttu-id="7de0d-363">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="7de0d-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="7de0d-364">Erstellen Sie ein neues .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core 2.0 SDK oder höher verfügbar)</span><span class="sxs-lookup"><span data-stu-id="7de0d-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="7de0d-365">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 2.0 verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="7de0d-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="7de0d-366">Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 2.0 vorgesehen ist:</span><span class="sxs-lookup"><span data-stu-id="7de0d-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="7de0d-367">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="7de0d-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="7de0d-368">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7de0d-368">See also</span></span>

[<span data-ttu-id="7de0d-369">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="7de0d-369">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="7de0d-370">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="7de0d-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="7de0d-371">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="7de0d-371">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="7de0d-372">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="7de0d-372">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
