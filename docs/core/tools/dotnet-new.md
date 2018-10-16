---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 396c4ddf09854fa4582226bdb1422f8c929e459b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208632"
---
# <a name="dotnet-new"></a><span data-ttu-id="665f5-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="665f5-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="665f5-104">name</span><span class="sxs-lookup"><span data-stu-id="665f5-104">Name</span></span>

<span data-ttu-id="665f5-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="665f5-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="665f5-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="665f5-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="665f5-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="665f5-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="665f5-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="665f5-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="665f5-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="665f5-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="665f5-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="665f5-110">Description</span></span>

<span data-ttu-id="665f5-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="665f5-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="665f5-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="665f5-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="665f5-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="665f5-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="665f5-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="665f5-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="665f5-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="665f5-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="665f5-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="665f5-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="665f5-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="665f5-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="665f5-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="665f5-118">The command contains a default list of templates.</span></span> <span data-ttu-id="665f5-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="665f5-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="665f5-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="665f5-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="665f5-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="665f5-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="665f5-122">Template description</span></span>                          | <span data-ttu-id="665f5-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="665f5-123">Template name</span></span>   | <span data-ttu-id="665f5-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="665f5-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="665f5-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="665f5-125">Console application</span></span>                          | `console`       | <span data-ttu-id="665f5-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="665f5-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="665f5-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="665f5-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="665f5-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="665f5-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="665f5-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-133">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="665f5-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="665f5-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-134">[C#]</span></span>          |
| <span data-ttu-id="665f5-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="665f5-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="665f5-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-136">[C#]</span></span>          |
| <span data-ttu-id="665f5-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="665f5-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="665f5-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-138">[C#]</span></span>          |
| <span data-ttu-id="665f5-139">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="665f5-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="665f5-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-140">[C#], F#</span></span>      |
| <span data-ttu-id="665f5-141">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="665f5-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="665f5-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-142">[C#], F#</span></span>      |
| <span data-ttu-id="665f5-143">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="665f5-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="665f5-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-144">[C#]</span></span>          |
| <span data-ttu-id="665f5-145">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="665f5-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="665f5-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-146">[C#]</span></span>          |
| <span data-ttu-id="665f5-147">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="665f5-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="665f5-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-148">[C#]</span></span>          |
| <span data-ttu-id="665f5-149">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="665f5-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="665f5-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-150">[C#]</span></span>          |
| <span data-ttu-id="665f5-151">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="665f5-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="665f5-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-152">[C#], F#</span></span>      |
| <span data-ttu-id="665f5-153">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="665f5-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="665f5-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-154">[C#]</span></span>          |
| <span data-ttu-id="665f5-155">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="665f5-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="665f5-156">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="665f5-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="665f5-157">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="665f5-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="665f5-158">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="665f5-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="665f5-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="665f5-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="665f5-160">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="665f5-160">The command contains a default list of templates.</span></span> <span data-ttu-id="665f5-161">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="665f5-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="665f5-162">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="665f5-163">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="665f5-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="665f5-164">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="665f5-164">Template description</span></span>                          | <span data-ttu-id="665f5-165">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="665f5-165">Template name</span></span> | <span data-ttu-id="665f5-166">Sprachen</span><span class="sxs-lookup"><span data-stu-id="665f5-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="665f5-167">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="665f5-167">Console application</span></span>                          | `console`     | <span data-ttu-id="665f5-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-169">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="665f5-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="665f5-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-171">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="665f5-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="665f5-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-173">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="665f5-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="665f5-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="665f5-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="665f5-175">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="665f5-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="665f5-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-176">[C#], F#</span></span>      |
| <span data-ttu-id="665f5-177">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="665f5-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="665f5-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-178">[C#], F#</span></span>      |
| <span data-ttu-id="665f5-179">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="665f5-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="665f5-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-180">[C#]</span></span>          |
| <span data-ttu-id="665f5-181">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="665f5-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="665f5-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-182">[C#]</span></span>          |
| <span data-ttu-id="665f5-183">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="665f5-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="665f5-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-184">[C#]</span></span>          |
| <span data-ttu-id="665f5-185">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="665f5-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="665f5-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-186">[C#]</span></span>          |
| <span data-ttu-id="665f5-187">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="665f5-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="665f5-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-188">[C#], F#</span></span>      |
| <span data-ttu-id="665f5-189">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="665f5-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="665f5-190">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="665f5-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="665f5-191">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="665f5-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="665f5-192">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="665f5-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="665f5-193">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="665f5-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="665f5-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="665f5-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="665f5-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="665f5-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="665f5-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="665f5-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="665f5-197">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="665f5-197">The command contains a default list of templates.</span></span> <span data-ttu-id="665f5-198">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="665f5-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="665f5-199">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="665f5-200">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="665f5-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="665f5-201">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="665f5-201">Template description</span></span>  | <span data-ttu-id="665f5-202">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="665f5-202">Template name</span></span> | <span data-ttu-id="665f5-203">Sprachen</span><span class="sxs-lookup"><span data-stu-id="665f5-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="665f5-204">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="665f5-204">Console application</span></span>  | `console`     | <span data-ttu-id="665f5-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-205">[C#], F#</span></span>  |
| <span data-ttu-id="665f5-206">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="665f5-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="665f5-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-207">[C#], F#</span></span>  |
| <span data-ttu-id="665f5-208">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="665f5-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="665f5-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-209">[C#], F#</span></span>  |
| <span data-ttu-id="665f5-210">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="665f5-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="665f5-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-211">[C#], F#</span></span>  |
| <span data-ttu-id="665f5-212">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="665f5-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="665f5-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-213">[C#]</span></span>      |
| <span data-ttu-id="665f5-214">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="665f5-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="665f5-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="665f5-215">[C#], F#</span></span>  |
| <span data-ttu-id="665f5-216">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="665f5-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="665f5-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="665f5-217">[C#]</span></span>      |
| <span data-ttu-id="665f5-218">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="665f5-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="665f5-219">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="665f5-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="665f5-220">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="665f5-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="665f5-221">Optionen</span><span class="sxs-lookup"><span data-stu-id="665f5-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="665f5-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="665f5-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="665f5-223">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="665f5-224">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="665f5-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="665f5-225">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="665f5-225">Prints out help for the command.</span></span> <span data-ttu-id="665f5-226">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="665f5-227">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="665f5-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="665f5-228">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="665f5-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="665f5-229">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="665f5-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="665f5-230">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="665f5-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="665f5-231">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="665f5-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="665f5-232">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="665f5-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="665f5-233">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="665f5-234">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="665f5-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="665f5-235">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="665f5-235">The language of the template to create.</span></span> <span data-ttu-id="665f5-236">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="665f5-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="665f5-237">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="665f5-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="665f5-238">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="665f5-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="665f5-239">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="665f5-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="665f5-240">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-240">The name for the created output.</span></span> <span data-ttu-id="665f5-241">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="665f5-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="665f5-242">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="665f5-243">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-243">Location to place the generated output.</span></span> <span data-ttu-id="665f5-244">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="665f5-245">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="665f5-245">Filters templates based on available types.</span></span> <span data-ttu-id="665f5-246">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="665f5-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="665f5-247">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="665f5-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="665f5-248">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="665f5-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="665f5-249">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="665f5-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="665f5-250">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="665f5-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="665f5-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="665f5-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="665f5-252">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="665f5-253">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="665f5-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="665f5-254">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="665f5-254">Prints out help for the command.</span></span> <span data-ttu-id="665f5-255">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="665f5-256">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="665f5-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="665f5-257">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="665f5-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="665f5-258">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="665f5-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="665f5-259">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="665f5-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="665f5-260">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="665f5-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="665f5-261">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="665f5-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="665f5-262">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="665f5-263">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="665f5-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="665f5-264">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="665f5-264">The language of the template to create.</span></span> <span data-ttu-id="665f5-265">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="665f5-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="665f5-266">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="665f5-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="665f5-267">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="665f5-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="665f5-268">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="665f5-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="665f5-269">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-269">The name for the created output.</span></span> <span data-ttu-id="665f5-270">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="665f5-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="665f5-271">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-271">Location to place the generated output.</span></span> <span data-ttu-id="665f5-272">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="665f5-273">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="665f5-273">Filters templates based on available types.</span></span> <span data-ttu-id="665f5-274">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="665f5-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="665f5-275">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="665f5-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="665f5-276">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="665f5-276">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="665f5-277">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="665f5-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="665f5-278">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="665f5-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="665f5-279">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-279">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="665f5-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="665f5-280">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="665f5-281">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="665f5-281">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="665f5-282">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="665f5-282">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="665f5-283">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="665f5-283">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="665f5-284">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="665f5-284">Prints out help for the command.</span></span> <span data-ttu-id="665f5-285">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-285">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="665f5-286">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="665f5-286">Lists templates containing the specified name.</span></span> <span data-ttu-id="665f5-287">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="665f5-287">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="665f5-288">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="665f5-288">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="665f5-289">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="665f5-289">The language of the template to create.</span></span> <span data-ttu-id="665f5-290">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="665f5-290">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="665f5-291">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="665f5-291">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="665f5-292">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="665f5-292">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="665f5-293">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="665f5-293">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="665f5-294">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-294">The name for the created output.</span></span> <span data-ttu-id="665f5-295">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="665f5-295">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="665f5-296">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-296">Location to place the generated output.</span></span> <span data-ttu-id="665f5-297">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-297">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="665f5-298">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="665f5-298">Template options</span></span>

<span data-ttu-id="665f5-299">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="665f5-299">Each project template may have additional options available.</span></span> <span data-ttu-id="665f5-300">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="665f5-300">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="665f5-301">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="665f5-301">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="665f5-302">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="665f5-302">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="665f5-303">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-303">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-304">**classlib**</span><span class="sxs-lookup"><span data-stu-id="665f5-304">**classlib**</span></span>

<span data-ttu-id="665f5-305">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-305">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="665f5-306">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="665f5-306">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="665f5-307">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="665f5-307">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="665f5-308">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-308">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-309">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="665f5-309">**mstest, xunit**</span></span>

<span data-ttu-id="665f5-310">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="665f5-310">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="665f5-311">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-312">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="665f5-312">**globaljson**</span></span>

<span data-ttu-id="665f5-313">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-313">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="665f5-314">**web**</span><span class="sxs-lookup"><span data-stu-id="665f5-314">**web**</span></span>

<span data-ttu-id="665f5-315">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="665f5-315">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="665f5-316">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-316">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-317">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="665f5-317">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="665f5-318">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-318">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="665f5-319">**webapi**</span><span class="sxs-lookup"><span data-stu-id="665f5-319">**webapi**</span></span>

<span data-ttu-id="665f5-320">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="665f5-320">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="665f5-321">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="665f5-321">The possible values are:</span></span>

- <span data-ttu-id="665f5-322">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="665f5-322">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="665f5-323">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="665f5-323">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="665f5-324">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-324">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="665f5-325">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-325">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="665f5-326">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-326">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="665f5-327">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-327">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-328">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-328">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="665f5-329">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-329">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="665f5-330">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-330">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-331">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-331">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="665f5-332">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-333">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-333">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="665f5-334">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-334">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="665f5-335">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-335">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-336">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="665f5-336">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="665f5-337">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-337">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="665f5-338">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-338">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-339">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="665f5-339">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="665f5-340">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="665f5-340">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="665f5-341">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-341">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-342">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="665f5-342">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="665f5-343">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-343">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="665f5-344">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="665f5-344">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="665f5-345">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="665f5-345">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="665f5-346">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-346">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="665f5-347">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="665f5-347">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-348">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-348">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-349">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="665f5-349">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="665f5-350">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="665f5-350">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="665f5-351">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-351">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="665f5-352">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="665f5-352">**mvc, razor**</span></span>

<span data-ttu-id="665f5-353">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="665f5-353">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="665f5-354">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="665f5-354">The possible values are:</span></span>

- <span data-ttu-id="665f5-355">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="665f5-355">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="665f5-356">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-356">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="665f5-357">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="665f5-357">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="665f5-358">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-358">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="665f5-359">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-359">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="665f5-360">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-360">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="665f5-361">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-361">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="665f5-362">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-362">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-363">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-363">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="665f5-364">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-364">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="665f5-365">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-365">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-366">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="665f5-366">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="665f5-367">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="665f5-367">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-368">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="665f5-368">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="665f5-369">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-369">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-370">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-370">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="665f5-371">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-371">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="665f5-372">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-372">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="665f5-373">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-373">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="665f5-374">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-374">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="665f5-375">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="665f5-375">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="665f5-376">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-376">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="665f5-377">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-378">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="665f5-378">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="665f5-379">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="665f5-379">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="665f5-380">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-380">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-381">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="665f5-381">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="665f5-382">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="665f5-382">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="665f5-383">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-383">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-384">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="665f5-384">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="665f5-385">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-385">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="665f5-386">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="665f5-386">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="665f5-387">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="665f5-387">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="665f5-388">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="665f5-388">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="665f5-389">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-389">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="665f5-390">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="665f5-390">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-391">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-391">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-392">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="665f5-392">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="665f5-393">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="665f5-393">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="665f5-394">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="665f5-394">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="665f5-395">**page**</span><span class="sxs-lookup"><span data-stu-id="665f5-395">**page**</span></span>

<span data-ttu-id="665f5-396">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="665f5-396">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="665f5-397">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="665f5-397">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="665f5-398">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="665f5-398">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="665f5-399">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="665f5-399">**viewimports**</span></span>

<span data-ttu-id="665f5-400">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="665f5-400">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="665f5-401">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="665f5-401">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="665f5-402">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="665f5-402">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="665f5-403">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="665f5-403">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="665f5-404">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-404">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-405">**classlib**</span><span class="sxs-lookup"><span data-stu-id="665f5-405">**classlib**</span></span>

<span data-ttu-id="665f5-406">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-406">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="665f5-407">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="665f5-407">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="665f5-408">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="665f5-408">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="665f5-409">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-409">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-410">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="665f5-410">**mstest, xunit**</span></span>

<span data-ttu-id="665f5-411">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="665f5-411">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="665f5-412">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-413">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="665f5-413">**globaljson**</span></span>

<span data-ttu-id="665f5-414">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-414">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="665f5-415">**web**</span><span class="sxs-lookup"><span data-stu-id="665f5-415">**web**</span></span>

<span data-ttu-id="665f5-416">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-416">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="665f5-417">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-417">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-418">**webapi**</span><span class="sxs-lookup"><span data-stu-id="665f5-418">**webapi**</span></span>

<span data-ttu-id="665f5-419">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="665f5-419">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="665f5-420">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="665f5-420">The possible values are:</span></span>

- <span data-ttu-id="665f5-421">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="665f5-421">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="665f5-422">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="665f5-422">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="665f5-423">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-423">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="665f5-424">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-424">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="665f5-425">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-425">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="665f5-426">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-426">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-427">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-427">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="665f5-428">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-428">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="665f5-429">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-429">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-430">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-430">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="665f5-431">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-432">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-432">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="665f5-433">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-433">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="665f5-434">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-434">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-435">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="665f5-435">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="665f5-436">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-436">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="665f5-437">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-437">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-438">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="665f5-438">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="665f5-439">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="665f5-439">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="665f5-440">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-441">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="665f5-441">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="665f5-442">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-442">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="665f5-443">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-443">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="665f5-444">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-444">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="665f5-445">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-445">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="665f5-446">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="665f5-446">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-447">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-447">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-448">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="665f5-448">**mvc, razor**</span></span>

<span data-ttu-id="665f5-449">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="665f5-449">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="665f5-450">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="665f5-450">The possible values are:</span></span>

- <span data-ttu-id="665f5-451">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="665f5-451">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="665f5-452">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-452">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="665f5-453">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="665f5-453">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="665f5-454">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-454">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="665f5-455">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-455">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="665f5-456">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-456">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="665f5-457">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-457">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="665f5-458">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-458">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-459">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-459">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="665f5-460">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-460">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="665f5-461">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-461">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-462">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="665f5-462">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="665f5-463">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="665f5-463">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-464">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="665f5-464">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="665f5-465">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-465">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-466">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-466">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="665f5-467">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-467">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="665f5-468">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="665f5-468">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="665f5-469">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="665f5-469">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="665f5-470">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-470">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="665f5-471">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="665f5-471">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="665f5-472">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="665f5-472">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="665f5-473">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-473">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-474">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="665f5-474">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="665f5-475">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="665f5-475">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="665f5-476">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-476">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="665f5-477">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="665f5-477">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="665f5-478">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="665f5-478">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="665f5-479">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="665f5-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="665f5-480">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="665f5-480">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="665f5-481">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="665f5-481">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="665f5-482">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="665f5-482">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="665f5-483">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="665f5-483">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="665f5-484">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="665f5-484">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="665f5-485">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-485">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="665f5-486">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="665f5-486">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="665f5-487">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="665f5-487">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="665f5-488">**page**</span><span class="sxs-lookup"><span data-stu-id="665f5-488">**page**</span></span>

<span data-ttu-id="665f5-489">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="665f5-489">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="665f5-490">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="665f5-490">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="665f5-491">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="665f5-491">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="665f5-492">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="665f5-492">**viewimports**</span></span>

<span data-ttu-id="665f5-493">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="665f5-493">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="665f5-494">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="665f5-494">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="665f5-495">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="665f5-495">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="665f5-496">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="665f5-496">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="665f5-497">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-497">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="665f5-498">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="665f5-498">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="665f5-499">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="665f5-499">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="665f5-500">**classlib**</span><span class="sxs-lookup"><span data-stu-id="665f5-500">**classlib**</span></span>

<span data-ttu-id="665f5-501">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-501">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="665f5-502">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="665f5-502">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="665f5-503">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="665f5-503">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="665f5-504">**mvc**</span><span class="sxs-lookup"><span data-stu-id="665f5-504">**mvc**</span></span>

<span data-ttu-id="665f5-505">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-505">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="665f5-506">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="665f5-506">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="665f5-507">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="665f5-507">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="665f5-508">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="665f5-508">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="665f5-509">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="665f5-509">Values: `None` or `Individual`.</span></span> <span data-ttu-id="665f5-510">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="665f5-510">The default value is `None`.</span></span>

<span data-ttu-id="665f5-511">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="665f5-511">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="665f5-512">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="665f5-512">Values: `true` or `false`.</span></span> <span data-ttu-id="665f5-513">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="665f5-513">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="665f5-514">Beispiele</span><span class="sxs-lookup"><span data-stu-id="665f5-514">Examples</span></span>

<span data-ttu-id="665f5-515">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="665f5-515">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="665f5-516">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="665f5-516">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="665f5-517">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="665f5-517">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="665f5-518">Erstellen Sie eine neue xUnit-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="665f5-518">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="665f5-519">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="665f5-519">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="665f5-520">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="665f5-520">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="665f5-521">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="665f5-521">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="665f5-522">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="665f5-522">See also</span></span>

* [<span data-ttu-id="665f5-523">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="665f5-523">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="665f5-524">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="665f5-524">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="665f5-525">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="665f5-525">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="665f5-526">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="665f5-526">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
