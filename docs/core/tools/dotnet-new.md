---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ae24c4145cc67ca863c07e4d22af8a1c2c2dd732
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570462"
---
# <a name="dotnet-new"></a><span data-ttu-id="0c694-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="0c694-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0c694-104">name</span><span class="sxs-lookup"><span data-stu-id="0c694-104">Name</span></span>

<span data-ttu-id="0c694-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="0c694-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0c694-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0c694-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0c694-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0c694-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0c694-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0c694-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0c694-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0c694-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="0c694-110">description</span><span class="sxs-lookup"><span data-stu-id="0c694-110">Description</span></span>

<span data-ttu-id="0c694-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="0c694-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="0c694-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="0c694-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="0c694-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="0c694-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="0c694-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0c694-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="0c694-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="0c694-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="0c694-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="0c694-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0c694-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0c694-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="0c694-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="0c694-118">The command contains a default list of templates.</span></span> <span data-ttu-id="0c694-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0c694-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="0c694-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="0c694-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="0c694-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c694-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0c694-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0c694-122">Template description</span></span>                          | <span data-ttu-id="0c694-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="0c694-123">Template name</span></span>   | <span data-ttu-id="0c694-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="0c694-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="0c694-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="0c694-125">Console application</span></span>                          | `console`       | <span data-ttu-id="0c694-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="0c694-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="0c694-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="0c694-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="0c694-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="0c694-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="0c694-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-133">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="0c694-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="0c694-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-134">[C#]</span></span>          |
| <span data-ttu-id="0c694-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="0c694-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="0c694-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-136">[C#]</span></span>          |
| <span data-ttu-id="0c694-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0c694-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="0c694-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-138">[C#]</span></span>          |
| <span data-ttu-id="0c694-139">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="0c694-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="0c694-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-140">[C#], F#</span></span>      |
| <span data-ttu-id="0c694-141">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="0c694-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="0c694-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-142">[C#], F#</span></span>      |
| <span data-ttu-id="0c694-143">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="0c694-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="0c694-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-144">[C#]</span></span>          |
| <span data-ttu-id="0c694-145">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="0c694-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="0c694-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-146">[C#]</span></span>          |
| <span data-ttu-id="0c694-147">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="0c694-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="0c694-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-148">[C#]</span></span>          |
| <span data-ttu-id="0c694-149">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="0c694-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="0c694-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-150">[C#]</span></span>          |
| <span data-ttu-id="0c694-151">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="0c694-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="0c694-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-152">[C#], F#</span></span>      |
| <span data-ttu-id="0c694-153">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="0c694-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="0c694-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-154">[C#]</span></span>          |
| <span data-ttu-id="0c694-155">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="0c694-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="0c694-156">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c694-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="0c694-157">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c694-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="0c694-158">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="0c694-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0c694-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0c694-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="0c694-160">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="0c694-160">The command contains a default list of templates.</span></span> <span data-ttu-id="0c694-161">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0c694-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="0c694-162">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="0c694-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="0c694-163">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c694-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0c694-164">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0c694-164">Template description</span></span>                          | <span data-ttu-id="0c694-165">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="0c694-165">Template name</span></span> | <span data-ttu-id="0c694-166">Sprachen</span><span class="sxs-lookup"><span data-stu-id="0c694-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="0c694-167">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="0c694-167">Console application</span></span>                          | `console`     | <span data-ttu-id="0c694-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-169">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="0c694-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="0c694-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-171">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="0c694-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="0c694-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-173">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="0c694-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="0c694-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0c694-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0c694-175">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="0c694-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="0c694-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-176">[C#], F#</span></span>      |
| <span data-ttu-id="0c694-177">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="0c694-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="0c694-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-178">[C#], F#</span></span>      |
| <span data-ttu-id="0c694-179">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="0c694-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="0c694-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-180">[C#]</span></span>          |
| <span data-ttu-id="0c694-181">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="0c694-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="0c694-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-182">[C#]</span></span>          |
| <span data-ttu-id="0c694-183">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="0c694-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="0c694-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-184">[C#]</span></span>          |
| <span data-ttu-id="0c694-185">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="0c694-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="0c694-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-186">[C#]</span></span>          |
| <span data-ttu-id="0c694-187">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="0c694-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="0c694-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-188">[C#], F#</span></span>      |
| <span data-ttu-id="0c694-189">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="0c694-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="0c694-190">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c694-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="0c694-191">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c694-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="0c694-192">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="0c694-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="0c694-193">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="0c694-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="0c694-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="0c694-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="0c694-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0c694-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0c694-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0c694-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0c694-197">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="0c694-197">The command contains a default list of templates.</span></span> <span data-ttu-id="0c694-198">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0c694-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="0c694-199">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="0c694-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="0c694-200">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c694-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0c694-201">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0c694-201">Template description</span></span>  | <span data-ttu-id="0c694-202">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="0c694-202">Template name</span></span> | <span data-ttu-id="0c694-203">Sprachen</span><span class="sxs-lookup"><span data-stu-id="0c694-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="0c694-204">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="0c694-204">Console application</span></span>  | `console`     | <span data-ttu-id="0c694-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-205">[C#], F#</span></span>  |
| <span data-ttu-id="0c694-206">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="0c694-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="0c694-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-207">[C#], F#</span></span>  |
| <span data-ttu-id="0c694-208">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="0c694-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="0c694-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-209">[C#], F#</span></span>  |
| <span data-ttu-id="0c694-210">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="0c694-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="0c694-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-211">[C#], F#</span></span>  |
| <span data-ttu-id="0c694-212">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="0c694-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="0c694-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-213">[C#]</span></span>      |
| <span data-ttu-id="0c694-214">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="0c694-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="0c694-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0c694-215">[C#], F#</span></span>  |
| <span data-ttu-id="0c694-216">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="0c694-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="0c694-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="0c694-217">[C#]</span></span>      |
| <span data-ttu-id="0c694-218">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c694-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="0c694-219">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="0c694-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="0c694-220">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="0c694-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="0c694-221">Optionen</span><span class="sxs-lookup"><span data-stu-id="0c694-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0c694-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0c694-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="0c694-223">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0c694-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0c694-224">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="0c694-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0c694-225">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0c694-225">Prints out help for the command.</span></span> <span data-ttu-id="0c694-226">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c694-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="0c694-227">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="0c694-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0c694-228">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="0c694-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="0c694-229">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="0c694-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="0c694-230">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="0c694-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="0c694-231">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="0c694-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="0c694-232">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c694-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="0c694-233">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0c694-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0c694-234">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="0c694-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="0c694-235">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="0c694-235">The language of the template to create.</span></span> <span data-ttu-id="0c694-236">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0c694-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0c694-237">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="0c694-237">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0c694-238">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-238">The name for the created output.</span></span> <span data-ttu-id="0c694-239">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c694-239">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="0c694-240">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-240">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0c694-241">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-241">Location to place the generated output.</span></span> <span data-ttu-id="0c694-242">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-242">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="0c694-243">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="0c694-243">Filters templates based on available types.</span></span> <span data-ttu-id="0c694-244">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="0c694-244">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="0c694-245">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="0c694-245">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="0c694-246">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c694-246">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="0c694-247">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="0c694-247">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="0c694-248">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="0c694-248">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0c694-249">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0c694-249">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="0c694-250">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0c694-250">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0c694-251">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="0c694-251">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0c694-252">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0c694-252">Prints out help for the command.</span></span> <span data-ttu-id="0c694-253">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c694-253">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="0c694-254">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="0c694-254">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0c694-255">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="0c694-255">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="0c694-256">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="0c694-256">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="0c694-257">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="0c694-257">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="0c694-258">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="0c694-258">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="0c694-259">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c694-259">Lists templates containing the specified name.</span></span> <span data-ttu-id="0c694-260">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0c694-260">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0c694-261">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="0c694-261">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="0c694-262">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="0c694-262">The language of the template to create.</span></span> <span data-ttu-id="0c694-263">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0c694-263">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0c694-264">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="0c694-264">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0c694-265">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-265">The name for the created output.</span></span> <span data-ttu-id="0c694-266">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c694-266">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0c694-267">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-267">Location to place the generated output.</span></span> <span data-ttu-id="0c694-268">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-268">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="0c694-269">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="0c694-269">Filters templates based on available types.</span></span> <span data-ttu-id="0c694-270">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="0c694-270">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="0c694-271">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="0c694-271">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="0c694-272">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="0c694-272">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="0c694-273">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="0c694-273">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="0c694-274">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="0c694-274">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0c694-275">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0c694-275">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="0c694-276">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="0c694-276">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="0c694-277">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="0c694-277">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="0c694-278">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="0c694-278">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0c694-279">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="0c694-279">Prints out help for the command.</span></span> <span data-ttu-id="0c694-280">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c694-280">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="0c694-281">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c694-281">Lists templates containing the specified name.</span></span> <span data-ttu-id="0c694-282">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0c694-282">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0c694-283">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="0c694-283">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="0c694-284">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="0c694-284">The language of the template to create.</span></span> <span data-ttu-id="0c694-285">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0c694-285">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0c694-286">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="0c694-286">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0c694-287">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-287">The name for the created output.</span></span> <span data-ttu-id="0c694-288">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="0c694-288">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0c694-289">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-289">Location to place the generated output.</span></span> <span data-ttu-id="0c694-290">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-290">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="0c694-291">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="0c694-291">Template options</span></span>

<span data-ttu-id="0c694-292">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="0c694-292">Each project template may have additional options available.</span></span> <span data-ttu-id="0c694-293">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="0c694-293">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="0c694-294">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="0c694-294">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="0c694-295">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="0c694-295">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="0c694-296">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-296">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-297">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0c694-297">**classlib**</span></span>

<span data-ttu-id="0c694-298">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-298">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0c694-299">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c694-299">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0c694-300">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="0c694-300">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="0c694-301">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-301">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-302">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="0c694-302">**mstest, xunit**</span></span>

<span data-ttu-id="0c694-303">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="0c694-303">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="0c694-304">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-305">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="0c694-305">**globaljson**</span></span>

<span data-ttu-id="0c694-306">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-306">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="0c694-307">**web**</span><span class="sxs-lookup"><span data-stu-id="0c694-307">**web**</span></span>

<span data-ttu-id="0c694-308">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-308">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0c694-309">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-310">**webapi**</span><span class="sxs-lookup"><span data-stu-id="0c694-310">**webapi**</span></span>

<span data-ttu-id="0c694-311">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="0c694-311">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0c694-312">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c694-312">The possible values are:</span></span>

- <span data-ttu-id="0c694-313">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="0c694-313">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0c694-314">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="0c694-314">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0c694-315">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-315">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0c694-316">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-316">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0c694-317">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-317">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0c694-318">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-318">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-319">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-319">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0c694-320">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-320">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0c694-321">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-321">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-322">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-322">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0c694-323">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-323">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-324">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-324">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0c694-325">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-325">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0c694-326">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-326">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-327">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0c694-327">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0c694-328">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-328">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0c694-329">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-329">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-330">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0c694-330">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0c694-331">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="0c694-331">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0c694-332">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-333">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0c694-333">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0c694-334">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-334">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0c694-335">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-335">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0c694-336">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-336">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0c694-337">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-337">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0c694-338">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0c694-338">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-339">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-339">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-340">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="0c694-340">**mvc, razor**</span></span>

<span data-ttu-id="0c694-341">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="0c694-341">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0c694-342">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c694-342">The possible values are:</span></span>

- <span data-ttu-id="0c694-343">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="0c694-343">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0c694-344">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-344">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="0c694-345">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="0c694-345">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0c694-346">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-346">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0c694-347">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-347">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="0c694-348">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-348">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0c694-349">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-349">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0c694-350">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-350">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-351">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-351">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0c694-352">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-352">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0c694-353">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-353">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-354">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="0c694-354">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="0c694-355">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c694-355">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-356">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="0c694-356">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="0c694-357">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-357">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-358">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-358">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0c694-359">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-359">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0c694-360">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-360">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0c694-361">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-361">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0c694-362">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-362">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0c694-363">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0c694-363">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0c694-364">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-364">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0c694-365">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-365">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-366">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0c694-366">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0c694-367">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="0c694-367">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0c694-368">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-368">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-369">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0c694-369">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0c694-370">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0c694-370">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0c694-371">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-372">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="0c694-372">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="0c694-373">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-373">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0c694-374">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-374">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0c694-375">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-375">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0c694-376">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="0c694-376">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="0c694-377">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-377">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0c694-378">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0c694-378">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-379">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-379">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-380">**page**</span><span class="sxs-lookup"><span data-stu-id="0c694-380">**page**</span></span>

<span data-ttu-id="0c694-381">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="0c694-381">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0c694-382">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0c694-382">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="0c694-383">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="0c694-383">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="0c694-384">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="0c694-384">**viewimports**</span></span>

<span data-ttu-id="0c694-385">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="0c694-385">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0c694-386">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0c694-386">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="0c694-387">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0c694-387">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="0c694-388">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="0c694-388">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="0c694-389">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-389">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-390">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0c694-390">**classlib**</span></span>

<span data-ttu-id="0c694-391">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-391">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0c694-392">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c694-392">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0c694-393">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="0c694-393">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="0c694-394">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-395">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="0c694-395">**mstest, xunit**</span></span>

<span data-ttu-id="0c694-396">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="0c694-396">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="0c694-397">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-397">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-398">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="0c694-398">**globaljson**</span></span>

<span data-ttu-id="0c694-399">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-399">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="0c694-400">**web**</span><span class="sxs-lookup"><span data-stu-id="0c694-400">**web**</span></span>

<span data-ttu-id="0c694-401">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-401">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0c694-402">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-402">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-403">**webapi**</span><span class="sxs-lookup"><span data-stu-id="0c694-403">**webapi**</span></span>

<span data-ttu-id="0c694-404">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="0c694-404">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0c694-405">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c694-405">The possible values are:</span></span>

- <span data-ttu-id="0c694-406">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="0c694-406">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0c694-407">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="0c694-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0c694-408">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0c694-409">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-409">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0c694-410">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-410">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0c694-411">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-412">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0c694-413">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-413">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0c694-414">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-414">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-415">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-415">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0c694-416">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-416">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-417">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-417">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0c694-418">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-418">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0c694-419">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-419">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-420">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0c694-420">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0c694-421">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-421">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0c694-422">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-422">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-423">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0c694-423">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0c694-424">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="0c694-424">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0c694-425">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-425">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-426">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0c694-426">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0c694-427">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-427">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0c694-428">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-428">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0c694-429">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-429">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0c694-430">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-430">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0c694-431">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0c694-431">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-432">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-432">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-433">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="0c694-433">**mvc, razor**</span></span>

<span data-ttu-id="0c694-434">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="0c694-434">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0c694-435">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="0c694-435">The possible values are:</span></span>

- <span data-ttu-id="0c694-436">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="0c694-436">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0c694-437">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-437">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="0c694-438">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="0c694-438">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0c694-439">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-439">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0c694-440">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-440">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="0c694-441">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-441">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0c694-442">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-442">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0c694-443">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-443">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-444">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-444">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0c694-445">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-445">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0c694-446">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-446">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-447">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="0c694-447">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="0c694-448">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0c694-448">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-449">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="0c694-449">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="0c694-450">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-450">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-451">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-451">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0c694-452">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-452">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0c694-453">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0c694-453">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0c694-454">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="0c694-454">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0c694-455">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-455">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0c694-456">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0c694-456">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0c694-457">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="0c694-457">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0c694-458">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-458">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-459">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0c694-459">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0c694-460">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="0c694-460">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0c694-461">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-461">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0c694-462">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0c694-462">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0c694-463">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0c694-463">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0c694-464">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="0c694-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0c694-465">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="0c694-465">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="0c694-466">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0c694-466">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0c694-467">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="0c694-467">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0c694-468">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="0c694-468">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0c694-469">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="0c694-469">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="0c694-470">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-470">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0c694-471">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="0c694-471">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0c694-472">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="0c694-472">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="0c694-473">**page**</span><span class="sxs-lookup"><span data-stu-id="0c694-473">**page**</span></span>

<span data-ttu-id="0c694-474">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="0c694-474">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0c694-475">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0c694-475">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="0c694-476">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="0c694-476">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="0c694-477">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="0c694-477">**viewimports**</span></span>

<span data-ttu-id="0c694-478">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="0c694-478">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0c694-479">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0c694-479">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0c694-480">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0c694-480">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0c694-481">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="0c694-481">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="0c694-482">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-482">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0c694-483">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="0c694-483">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0c694-484">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="0c694-484">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0c694-485">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0c694-485">**classlib**</span></span>

<span data-ttu-id="0c694-486">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-486">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0c694-487">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="0c694-487">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="0c694-488">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="0c694-488">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="0c694-489">**mvc**</span><span class="sxs-lookup"><span data-stu-id="0c694-489">**mvc**</span></span>

<span data-ttu-id="0c694-490">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-490">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0c694-491">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="0c694-491">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0c694-492">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="0c694-492">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0c694-493">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="0c694-493">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="0c694-494">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="0c694-494">Values: `None` or `Individual`.</span></span> <span data-ttu-id="0c694-495">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="0c694-495">The default value is `None`.</span></span>

<span data-ttu-id="0c694-496">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c694-496">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="0c694-497">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="0c694-497">Values: `true` or `false`.</span></span> <span data-ttu-id="0c694-498">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0c694-498">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="0c694-499">Beispiele</span><span class="sxs-lookup"><span data-stu-id="0c694-499">Examples</span></span>

<span data-ttu-id="0c694-500">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="0c694-500">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="0c694-501">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="0c694-501">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="0c694-502">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung, wobei .NET Core 2.0 verwendet werden soll:</span><span class="sxs-lookup"><span data-stu-id="0c694-502">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="0c694-503">Erstellen Sie eine neue xUnit-Anwendung, die für .NET Core 2.0 vorgesehen ist:</span><span class="sxs-lookup"><span data-stu-id="0c694-503">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="0c694-504">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="0c694-504">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="0c694-505">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="0c694-505">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="0c694-506">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="0c694-506">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="0c694-507">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c694-507">See also</span></span>

[<span data-ttu-id="0c694-508">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="0c694-508">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="0c694-509">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="0c694-509">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="0c694-510">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="0c694-510">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="0c694-511">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="0c694-511">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)