---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 06/12/2018
ms.openlocfilehash: f0ef91361dfbc2c2ba5532fbd607786289e98c69
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207781"
---
# <a name="dotnet-new"></a><span data-ttu-id="d5563-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d5563-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d5563-104">name</span><span class="sxs-lookup"><span data-stu-id="d5563-104">Name</span></span>

<span data-ttu-id="d5563-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="d5563-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d5563-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d5563-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d5563-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d5563-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d5563-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d5563-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d5563-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d5563-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d5563-110">description</span><span class="sxs-lookup"><span data-stu-id="d5563-110">Description</span></span>

<span data-ttu-id="d5563-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d5563-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="d5563-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="d5563-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="d5563-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="d5563-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="d5563-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d5563-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d5563-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="d5563-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d5563-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="d5563-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d5563-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d5563-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="d5563-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="d5563-118">The command contains a default list of templates.</span></span> <span data-ttu-id="d5563-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d5563-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="d5563-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="d5563-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="d5563-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5563-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d5563-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d5563-122">Template description</span></span>                          | <span data-ttu-id="d5563-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="d5563-123">Template name</span></span>   | <span data-ttu-id="d5563-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="d5563-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="d5563-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="d5563-125">Console application</span></span>                          | `console`       | <span data-ttu-id="d5563-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="d5563-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="d5563-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="d5563-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="d5563-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="d5563-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="d5563-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-133">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="d5563-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="d5563-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-134">[C#]</span></span>          |
| <span data-ttu-id="d5563-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="d5563-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="d5563-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-136">[C#]</span></span>          |
| <span data-ttu-id="d5563-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d5563-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="d5563-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-138">[C#]</span></span>          |
| <span data-ttu-id="d5563-139">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="d5563-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="d5563-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-140">[C#], F#</span></span>      |
| <span data-ttu-id="d5563-141">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d5563-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="d5563-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-142">[C#], F#</span></span>      |
| <span data-ttu-id="d5563-143">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="d5563-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="d5563-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-144">[C#]</span></span>          |
| <span data-ttu-id="d5563-145">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="d5563-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="d5563-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-146">[C#]</span></span>          |
| <span data-ttu-id="d5563-147">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="d5563-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="d5563-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-148">[C#]</span></span>          |
| <span data-ttu-id="d5563-149">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="d5563-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="d5563-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-150">[C#]</span></span>          |
| <span data-ttu-id="d5563-151">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="d5563-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="d5563-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-152">[C#], F#</span></span>      |
| <span data-ttu-id="d5563-153">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="d5563-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="d5563-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-154">[C#]</span></span>          |
| <span data-ttu-id="d5563-155">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="d5563-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="d5563-156">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5563-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="d5563-157">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5563-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="d5563-158">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="d5563-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d5563-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d5563-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="d5563-160">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="d5563-160">The command contains a default list of templates.</span></span> <span data-ttu-id="d5563-161">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d5563-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="d5563-162">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="d5563-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="d5563-163">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5563-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d5563-164">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d5563-164">Template description</span></span>                          | <span data-ttu-id="d5563-165">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="d5563-165">Template name</span></span> | <span data-ttu-id="d5563-166">Sprachen</span><span class="sxs-lookup"><span data-stu-id="d5563-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="d5563-167">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="d5563-167">Console application</span></span>                          | `console`     | <span data-ttu-id="d5563-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-169">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="d5563-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="d5563-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-171">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="d5563-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="d5563-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-173">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="d5563-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="d5563-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d5563-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d5563-175">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="d5563-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="d5563-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-176">[C#], F#</span></span>      |
| <span data-ttu-id="d5563-177">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d5563-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="d5563-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-178">[C#], F#</span></span>      |
| <span data-ttu-id="d5563-179">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="d5563-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="d5563-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-180">[C#]</span></span>          |
| <span data-ttu-id="d5563-181">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="d5563-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="d5563-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-182">[C#]</span></span>          |
| <span data-ttu-id="d5563-183">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="d5563-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="d5563-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-184">[C#]</span></span>          |
| <span data-ttu-id="d5563-185">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="d5563-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="d5563-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-186">[C#]</span></span>          |
| <span data-ttu-id="d5563-187">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="d5563-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="d5563-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-188">[C#], F#</span></span>      |
| <span data-ttu-id="d5563-189">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="d5563-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="d5563-190">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5563-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="d5563-191">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5563-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="d5563-192">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="d5563-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="d5563-193">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="d5563-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="d5563-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="d5563-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="d5563-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d5563-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d5563-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d5563-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d5563-197">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="d5563-197">The command contains a default list of templates.</span></span> <span data-ttu-id="d5563-198">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d5563-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="d5563-199">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="d5563-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="d5563-200">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d5563-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d5563-201">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d5563-201">Template description</span></span>  | <span data-ttu-id="d5563-202">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="d5563-202">Template name</span></span> | <span data-ttu-id="d5563-203">Sprachen</span><span class="sxs-lookup"><span data-stu-id="d5563-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="d5563-204">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="d5563-204">Console application</span></span>  | `console`     | <span data-ttu-id="d5563-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-205">[C#], F#</span></span>  |
| <span data-ttu-id="d5563-206">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="d5563-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="d5563-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-207">[C#], F#</span></span>  |
| <span data-ttu-id="d5563-208">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="d5563-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="d5563-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-209">[C#], F#</span></span>  |
| <span data-ttu-id="d5563-210">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="d5563-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="d5563-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-211">[C#], F#</span></span>  |
| <span data-ttu-id="d5563-212">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="d5563-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="d5563-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-213">[C#]</span></span>      |
| <span data-ttu-id="d5563-214">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="d5563-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="d5563-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d5563-215">[C#], F#</span></span>  |
| <span data-ttu-id="d5563-216">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="d5563-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="d5563-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="d5563-217">[C#]</span></span>      |
| <span data-ttu-id="d5563-218">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5563-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="d5563-219">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5563-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="d5563-220">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="d5563-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="d5563-221">Optionen</span><span class="sxs-lookup"><span data-stu-id="d5563-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d5563-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d5563-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="d5563-223">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d5563-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d5563-224">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d5563-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d5563-225">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d5563-225">Prints out help for the command.</span></span> <span data-ttu-id="d5563-226">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d5563-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="d5563-227">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d5563-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d5563-228">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="d5563-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="d5563-229">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5563-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="d5563-230">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="d5563-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="d5563-231">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d5563-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="d5563-232">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d5563-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="d5563-233">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d5563-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d5563-234">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="d5563-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="d5563-235">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="d5563-235">The language of the template to create.</span></span> <span data-ttu-id="d5563-236">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="d5563-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d5563-237">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="d5563-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="d5563-238">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="d5563-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="d5563-239">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="d5563-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d5563-240">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-240">The name for the created output.</span></span> <span data-ttu-id="d5563-241">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5563-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="d5563-242">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d5563-243">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-243">Location to place the generated output.</span></span> <span data-ttu-id="d5563-244">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="d5563-245">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="d5563-245">Filters templates based on available types.</span></span> <span data-ttu-id="d5563-246">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="d5563-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="d5563-247">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d5563-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="d5563-248">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="d5563-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d5563-249">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="d5563-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="d5563-250">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="d5563-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d5563-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d5563-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="d5563-252">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d5563-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d5563-253">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d5563-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d5563-254">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d5563-254">Prints out help for the command.</span></span> <span data-ttu-id="d5563-255">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d5563-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="d5563-256">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d5563-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d5563-257">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="d5563-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="d5563-258">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5563-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="d5563-259">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="d5563-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="d5563-260">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d5563-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="d5563-261">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d5563-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="d5563-262">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d5563-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d5563-263">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="d5563-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="d5563-264">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="d5563-264">The language of the template to create.</span></span> <span data-ttu-id="d5563-265">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="d5563-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d5563-266">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="d5563-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="d5563-267">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="d5563-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="d5563-268">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="d5563-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d5563-269">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-269">The name for the created output.</span></span> <span data-ttu-id="d5563-270">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5563-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d5563-271">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-271">Location to place the generated output.</span></span> <span data-ttu-id="d5563-272">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="d5563-273">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="d5563-273">Filters templates based on available types.</span></span> <span data-ttu-id="d5563-274">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="d5563-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="d5563-275">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="d5563-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="d5563-276">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="d5563-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d5563-277">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="d5563-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="d5563-278">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="d5563-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d5563-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d5563-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="d5563-280">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="d5563-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="d5563-281">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d5563-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="d5563-282">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="d5563-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d5563-283">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d5563-283">Prints out help for the command.</span></span> <span data-ttu-id="d5563-284">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d5563-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="d5563-285">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d5563-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="d5563-286">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d5563-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d5563-287">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="d5563-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="d5563-288">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="d5563-288">The language of the template to create.</span></span> <span data-ttu-id="d5563-289">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="d5563-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d5563-290">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="d5563-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="d5563-291">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="d5563-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="d5563-292">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="d5563-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d5563-293">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-293">The name for the created output.</span></span> <span data-ttu-id="d5563-294">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="d5563-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d5563-295">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-295">Location to place the generated output.</span></span> <span data-ttu-id="d5563-296">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="d5563-297">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="d5563-297">Template options</span></span>

<span data-ttu-id="d5563-298">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="d5563-298">Each project template may have additional options available.</span></span> <span data-ttu-id="d5563-299">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="d5563-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="d5563-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d5563-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="d5563-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="d5563-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="d5563-302">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d5563-303">**classlib**</span></span>

<span data-ttu-id="d5563-304">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d5563-305">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5563-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d5563-306">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="d5563-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="d5563-307">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="d5563-308">**mstest, xunit**</span></span>

<span data-ttu-id="d5563-309">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d5563-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="d5563-310">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="d5563-311">**globaljson**</span></span>

<span data-ttu-id="d5563-312">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="d5563-313">**web**</span><span class="sxs-lookup"><span data-stu-id="d5563-313">**web**</span></span>

<span data-ttu-id="d5563-314">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-314">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d5563-315">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-316">**webapi**</span><span class="sxs-lookup"><span data-stu-id="d5563-316">**webapi**</span></span>

<span data-ttu-id="d5563-317">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="d5563-317">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d5563-318">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="d5563-318">The possible values are:</span></span>

- <span data-ttu-id="d5563-319">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5563-319">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d5563-320">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="d5563-320">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d5563-321">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-321">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d5563-322">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-322">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d5563-323">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-323">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d5563-324">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-324">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-325">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-325">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d5563-326">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-326">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d5563-327">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-327">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-328">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-328">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d5563-329">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-329">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-330">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-330">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d5563-331">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-331">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d5563-332">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-332">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-333">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d5563-333">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d5563-334">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-334">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d5563-335">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-335">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-336">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d5563-336">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d5563-337">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="d5563-337">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d5563-338">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-338">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-339">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d5563-339">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d5563-340">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-340">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d5563-341">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-341">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d5563-342">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-342">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d5563-343">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-343">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d5563-344">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d5563-344">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-345">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-345">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-346">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="d5563-346">**mvc, razor**</span></span>

<span data-ttu-id="d5563-347">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="d5563-347">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d5563-348">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="d5563-348">The possible values are:</span></span>

- <span data-ttu-id="d5563-349">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5563-349">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d5563-350">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-350">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="d5563-351">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="d5563-351">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d5563-352">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-352">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d5563-353">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-353">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="d5563-354">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-354">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d5563-355">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-355">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d5563-356">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-356">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-357">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-357">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d5563-358">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-358">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d5563-359">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-359">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-360">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="d5563-360">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="d5563-361">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5563-361">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-362">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="d5563-362">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="d5563-363">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-363">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-364">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-364">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d5563-365">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-365">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d5563-366">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-366">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d5563-367">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-367">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d5563-368">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-368">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d5563-369">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d5563-369">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d5563-370">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-370">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d5563-371">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-372">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d5563-372">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d5563-373">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="d5563-373">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d5563-374">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-374">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-375">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d5563-375">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d5563-376">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d5563-376">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d5563-377">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-378">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="d5563-378">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="d5563-379">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-379">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d5563-380">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-380">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d5563-381">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-381">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d5563-382">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="d5563-382">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="d5563-383">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-383">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d5563-384">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d5563-384">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-385">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-385">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-386">**page**</span><span class="sxs-lookup"><span data-stu-id="d5563-386">**page**</span></span>

<span data-ttu-id="d5563-387">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="d5563-387">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d5563-388">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d5563-388">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="d5563-389">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="d5563-389">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="d5563-390">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="d5563-390">**viewimports**</span></span>

<span data-ttu-id="d5563-391">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="d5563-391">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d5563-392">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d5563-392">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="d5563-393">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d5563-393">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="d5563-394">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="d5563-394">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="d5563-395">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-395">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-396">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d5563-396">**classlib**</span></span>

<span data-ttu-id="d5563-397">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-397">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d5563-398">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5563-398">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d5563-399">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="d5563-399">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="d5563-400">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-400">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-401">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="d5563-401">**mstest, xunit**</span></span>

<span data-ttu-id="d5563-402">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d5563-402">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="d5563-403">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-404">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="d5563-404">**globaljson**</span></span>

<span data-ttu-id="d5563-405">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-405">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="d5563-406">**web**</span><span class="sxs-lookup"><span data-stu-id="d5563-406">**web**</span></span>

<span data-ttu-id="d5563-407">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-407">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d5563-408">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-409">**webapi**</span><span class="sxs-lookup"><span data-stu-id="d5563-409">**webapi**</span></span>

<span data-ttu-id="d5563-410">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="d5563-410">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d5563-411">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="d5563-411">The possible values are:</span></span>

- <span data-ttu-id="d5563-412">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5563-412">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d5563-413">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="d5563-413">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d5563-414">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-414">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d5563-415">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-415">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d5563-416">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-416">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d5563-417">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-417">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-418">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-418">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d5563-419">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-419">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d5563-420">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-420">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-421">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-421">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d5563-422">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-422">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-423">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-423">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d5563-424">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-424">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d5563-425">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-425">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-426">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d5563-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d5563-427">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-427">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d5563-428">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-429">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d5563-429">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d5563-430">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="d5563-430">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d5563-431">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-432">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d5563-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d5563-433">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-433">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d5563-434">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-434">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d5563-435">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-435">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d5563-436">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-436">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d5563-437">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d5563-437">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-438">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-438">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-439">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="d5563-439">**mvc, razor**</span></span>

<span data-ttu-id="d5563-440">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="d5563-440">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d5563-441">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="d5563-441">The possible values are:</span></span>

- <span data-ttu-id="d5563-442">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="d5563-442">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d5563-443">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-443">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="d5563-444">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="d5563-444">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d5563-445">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-445">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d5563-446">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-446">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="d5563-447">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-447">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d5563-448">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-448">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d5563-449">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-449">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-450">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-450">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d5563-451">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-451">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d5563-452">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-452">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-453">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="d5563-453">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="d5563-454">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5563-454">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-455">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="d5563-455">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="d5563-456">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-456">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-457">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-457">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d5563-458">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-458">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d5563-459">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d5563-459">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d5563-460">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="d5563-460">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d5563-461">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-461">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d5563-462">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d5563-462">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d5563-463">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="d5563-463">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d5563-464">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-465">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d5563-465">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d5563-466">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="d5563-466">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d5563-467">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-467">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d5563-468">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d5563-468">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d5563-469">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d5563-469">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d5563-470">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="d5563-470">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d5563-471">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="d5563-471">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="d5563-472">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d5563-472">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d5563-473">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d5563-473">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d5563-474">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="d5563-474">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d5563-475">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="d5563-475">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="d5563-476">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-476">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d5563-477">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="d5563-477">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d5563-478">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="d5563-478">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="d5563-479">**page**</span><span class="sxs-lookup"><span data-stu-id="d5563-479">**page**</span></span>

<span data-ttu-id="d5563-480">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="d5563-480">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d5563-481">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d5563-481">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="d5563-482">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="d5563-482">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="d5563-483">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="d5563-483">**viewimports**</span></span>

<span data-ttu-id="d5563-484">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="d5563-484">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d5563-485">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d5563-485">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d5563-486">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d5563-486">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d5563-487">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="d5563-487">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="d5563-488">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-488">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d5563-489">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="d5563-489">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d5563-490">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="d5563-490">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d5563-491">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d5563-491">**classlib**</span></span>

<span data-ttu-id="d5563-492">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-492">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d5563-493">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="d5563-493">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="d5563-494">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="d5563-494">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="d5563-495">**mvc**</span><span class="sxs-lookup"><span data-stu-id="d5563-495">**mvc**</span></span>

<span data-ttu-id="d5563-496">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d5563-497">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="d5563-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d5563-498">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="d5563-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d5563-499">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="d5563-499">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="d5563-500">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="d5563-500">Values: `None` or `Individual`.</span></span> <span data-ttu-id="d5563-501">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="d5563-501">The default value is `None`.</span></span>

<span data-ttu-id="d5563-502">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d5563-502">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="d5563-503">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="d5563-503">Values: `true` or `false`.</span></span> <span data-ttu-id="d5563-504">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="d5563-504">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d5563-505">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d5563-505">Examples</span></span>

<span data-ttu-id="d5563-506">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="d5563-506">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="d5563-507">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="d5563-507">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="d5563-508">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="d5563-508">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="d5563-509">Erstellen Sie eine neue xUnit-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="d5563-509">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="d5563-510">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="d5563-510">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="d5563-511">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="d5563-511">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="d5563-512">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="d5563-512">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="d5563-513">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5563-513">See also</span></span>

[<span data-ttu-id="d5563-514">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="d5563-514">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="d5563-515">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="d5563-515">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="d5563-516">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="d5563-516">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="d5563-517">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="d5563-517">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
