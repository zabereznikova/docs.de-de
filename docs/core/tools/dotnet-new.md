---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512554"
---
# <a name="dotnet-new"></a><span data-ttu-id="e3b97-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e3b97-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e3b97-104">name</span><span class="sxs-lookup"><span data-stu-id="e3b97-104">Name</span></span>

<span data-ttu-id="e3b97-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="e3b97-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e3b97-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e3b97-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e3b97-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e3b97-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e3b97-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e3b97-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e3b97-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e3b97-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e3b97-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="e3b97-110">Description</span></span>

<span data-ttu-id="e3b97-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e3b97-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="e3b97-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="e3b97-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="e3b97-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="e3b97-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="e3b97-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e3b97-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e3b97-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="e3b97-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e3b97-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e3b97-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e3b97-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e3b97-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e3b97-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-118">The command contains a default list of templates.</span></span> <span data-ttu-id="e3b97-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e3b97-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="e3b97-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="e3b97-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e3b97-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e3b97-122">Template description</span></span>                          | <span data-ttu-id="e3b97-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="e3b97-123">Template name</span></span>   | <span data-ttu-id="e3b97-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="e3b97-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="e3b97-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="e3b97-125">Console application</span></span>                          | `console`       | <span data-ttu-id="e3b97-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="e3b97-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="e3b97-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="e3b97-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="e3b97-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-133">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="e3b97-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="e3b97-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-134">[C#]</span></span>          |
| <span data-ttu-id="e3b97-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e3b97-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="e3b97-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-136">[C#]</span></span>          |
| <span data-ttu-id="e3b97-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e3b97-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="e3b97-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-138">[C#]</span></span>          |
| <span data-ttu-id="e3b97-139">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="e3b97-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="e3b97-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-140">[C#], F#</span></span>      |
| <span data-ttu-id="e3b97-141">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e3b97-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="e3b97-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-142">[C#], F#</span></span>      |
| <span data-ttu-id="e3b97-143">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="e3b97-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="e3b97-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-144">[C#]</span></span>          |
| <span data-ttu-id="e3b97-145">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="e3b97-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="e3b97-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-146">[C#]</span></span>          |
| <span data-ttu-id="e3b97-147">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="e3b97-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="e3b97-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-148">[C#]</span></span>          |
| <span data-ttu-id="e3b97-149">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="e3b97-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="e3b97-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-150">[C#]</span></span>          |
| <span data-ttu-id="e3b97-151">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="e3b97-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="e3b97-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-152">[C#], F#</span></span>      |
| <span data-ttu-id="e3b97-153">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="e3b97-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="e3b97-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-154">[C#]</span></span>          |
| <span data-ttu-id="e3b97-155">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="e3b97-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="e3b97-156">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b97-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="e3b97-157">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b97-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="e3b97-158">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="e3b97-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e3b97-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e3b97-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e3b97-160">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-160">The command contains a default list of templates.</span></span> <span data-ttu-id="e3b97-161">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e3b97-162">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="e3b97-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="e3b97-163">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e3b97-164">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e3b97-164">Template description</span></span>                          | <span data-ttu-id="e3b97-165">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="e3b97-165">Template name</span></span> | <span data-ttu-id="e3b97-166">Sprachen</span><span class="sxs-lookup"><span data-stu-id="e3b97-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="e3b97-167">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="e3b97-167">Console application</span></span>                          | `console`     | <span data-ttu-id="e3b97-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-169">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="e3b97-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="e3b97-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-171">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="e3b97-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-173">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="e3b97-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e3b97-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e3b97-175">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="e3b97-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="e3b97-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-176">[C#], F#</span></span>      |
| <span data-ttu-id="e3b97-177">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e3b97-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="e3b97-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-178">[C#], F#</span></span>      |
| <span data-ttu-id="e3b97-179">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="e3b97-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="e3b97-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-180">[C#]</span></span>          |
| <span data-ttu-id="e3b97-181">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="e3b97-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="e3b97-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-182">[C#]</span></span>          |
| <span data-ttu-id="e3b97-183">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="e3b97-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="e3b97-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-184">[C#]</span></span>          |
| <span data-ttu-id="e3b97-185">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="e3b97-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="e3b97-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-186">[C#]</span></span>          |
| <span data-ttu-id="e3b97-187">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="e3b97-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="e3b97-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-188">[C#], F#</span></span>      |
| <span data-ttu-id="e3b97-189">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="e3b97-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="e3b97-190">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b97-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="e3b97-191">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b97-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="e3b97-192">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="e3b97-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="e3b97-193">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="e3b97-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="e3b97-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e3b97-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="e3b97-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e3b97-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e3b97-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e3b97-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e3b97-197">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-197">The command contains a default list of templates.</span></span> <span data-ttu-id="e3b97-198">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="e3b97-199">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="e3b97-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="e3b97-200">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e3b97-201">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="e3b97-201">Template description</span></span>  | <span data-ttu-id="e3b97-202">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="e3b97-202">Template name</span></span> | <span data-ttu-id="e3b97-203">Sprachen</span><span class="sxs-lookup"><span data-stu-id="e3b97-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="e3b97-204">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="e3b97-204">Console application</span></span>  | `console`     | <span data-ttu-id="e3b97-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-205">[C#], F#</span></span>  |
| <span data-ttu-id="e3b97-206">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="e3b97-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="e3b97-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-207">[C#], F#</span></span>  |
| <span data-ttu-id="e3b97-208">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="e3b97-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-209">[C#], F#</span></span>  |
| <span data-ttu-id="e3b97-210">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="e3b97-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-211">[C#], F#</span></span>  |
| <span data-ttu-id="e3b97-212">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="e3b97-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="e3b97-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-213">[C#]</span></span>      |
| <span data-ttu-id="e3b97-214">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="e3b97-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="e3b97-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e3b97-215">[C#], F#</span></span>  |
| <span data-ttu-id="e3b97-216">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="e3b97-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="e3b97-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="e3b97-217">[C#]</span></span>      |
| <span data-ttu-id="e3b97-218">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b97-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="e3b97-219">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e3b97-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="e3b97-220">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="e3b97-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="e3b97-221">Optionen</span><span class="sxs-lookup"><span data-stu-id="e3b97-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e3b97-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e3b97-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="e3b97-223">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e3b97-224">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="e3b97-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e3b97-225">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e3b97-225">Prints out help for the command.</span></span> <span data-ttu-id="e3b97-226">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e3b97-227">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e3b97-228">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="e3b97-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e3b97-229">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e3b97-230">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="e3b97-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e3b97-231">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e3b97-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e3b97-232">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e3b97-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="e3b97-233">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e3b97-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e3b97-234">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="e3b97-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e3b97-235">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-235">The language of the template to create.</span></span> <span data-ttu-id="e3b97-236">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e3b97-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e3b97-237">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="e3b97-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e3b97-238">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e3b97-239">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e3b97-240">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-240">The name for the created output.</span></span> <span data-ttu-id="e3b97-241">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3b97-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="e3b97-242">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e3b97-243">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-243">Location to place the generated output.</span></span> <span data-ttu-id="e3b97-244">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e3b97-245">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-245">Filters templates based on available types.</span></span> <span data-ttu-id="e3b97-246">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="e3b97-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e3b97-247">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e3b97-248">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e3b97-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e3b97-249">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="e3b97-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e3b97-250">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="e3b97-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e3b97-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e3b97-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="e3b97-252">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e3b97-253">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="e3b97-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e3b97-254">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e3b97-254">Prints out help for the command.</span></span> <span data-ttu-id="e3b97-255">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e3b97-256">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e3b97-257">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="e3b97-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e3b97-258">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e3b97-259">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="e3b97-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e3b97-260">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e3b97-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e3b97-261">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e3b97-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="e3b97-262">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e3b97-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e3b97-263">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="e3b97-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e3b97-264">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-264">The language of the template to create.</span></span> <span data-ttu-id="e3b97-265">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e3b97-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e3b97-266">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="e3b97-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e3b97-267">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e3b97-268">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e3b97-269">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-269">The name for the created output.</span></span> <span data-ttu-id="e3b97-270">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3b97-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e3b97-271">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-271">Location to place the generated output.</span></span> <span data-ttu-id="e3b97-272">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e3b97-273">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-273">Filters templates based on available types.</span></span> <span data-ttu-id="e3b97-274">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="e3b97-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e3b97-275">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e3b97-276">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="e3b97-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e3b97-277">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="e3b97-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e3b97-278">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="e3b97-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e3b97-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e3b97-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="e3b97-280">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="e3b97-281">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="e3b97-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="e3b97-282">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="e3b97-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e3b97-283">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="e3b97-283">Prints out help for the command.</span></span> <span data-ttu-id="e3b97-284">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="e3b97-285">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e3b97-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="e3b97-286">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e3b97-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e3b97-287">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="e3b97-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="e3b97-288">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-288">The language of the template to create.</span></span> <span data-ttu-id="e3b97-289">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e3b97-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e3b97-290">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="e3b97-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e3b97-291">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e3b97-292">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e3b97-293">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-293">The name for the created output.</span></span> <span data-ttu-id="e3b97-294">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3b97-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e3b97-295">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-295">Location to place the generated output.</span></span> <span data-ttu-id="e3b97-296">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="e3b97-297">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="e3b97-297">Template options</span></span>

<span data-ttu-id="e3b97-298">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="e3b97-298">Each project template may have additional options available.</span></span> <span data-ttu-id="e3b97-299">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="e3b97-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e3b97-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e3b97-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e3b97-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="e3b97-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="e3b97-302">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e3b97-303">**classlib**</span></span>

<span data-ttu-id="e3b97-304">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3b97-305">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e3b97-306">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e3b97-307">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e3b97-308">**mstest, xunit**</span></span>

<span data-ttu-id="e3b97-309">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e3b97-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e3b97-310">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e3b97-311">**globaljson**</span></span>

<span data-ttu-id="e3b97-312">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e3b97-313">**web**</span><span class="sxs-lookup"><span data-stu-id="e3b97-313">**web**</span></span>

<span data-ttu-id="e3b97-314">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="e3b97-314">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e3b97-315">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-316">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3b97-316">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e3b97-317">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-317">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="e3b97-318">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e3b97-318">**webapi**</span></span>

<span data-ttu-id="e3b97-319">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="e3b97-319">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e3b97-320">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e3b97-320">The possible values are:</span></span>

- <span data-ttu-id="e3b97-321">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="e3b97-321">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e3b97-322">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="e3b97-322">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e3b97-323">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-323">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e3b97-324">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-324">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e3b97-325">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-325">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3b97-326">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-326">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-327">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-327">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e3b97-328">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-328">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3b97-329">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-329">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-330">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-330">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3b97-331">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-331">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-332">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-332">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e3b97-333">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-333">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e3b97-334">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-334">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-335">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-335">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e3b97-336">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-336">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e3b97-337">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-337">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-338">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-338">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e3b97-339">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="e3b97-339">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3b97-340">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-340">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-341">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-341">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e3b97-342">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-342">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3b97-343">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-343">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e3b97-344">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="e3b97-344">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e3b97-345">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-345">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3b97-346">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-346">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-347">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-347">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-348">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3b97-348">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e3b97-349">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-349">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e3b97-350">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-350">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="e3b97-351">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e3b97-351">**mvc, razor**</span></span>

<span data-ttu-id="e3b97-352">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="e3b97-352">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e3b97-353">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e3b97-353">The possible values are:</span></span>

- <span data-ttu-id="e3b97-354">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="e3b97-354">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e3b97-355">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-355">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e3b97-356">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="e3b97-356">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e3b97-357">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-357">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e3b97-358">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-358">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e3b97-359">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-359">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e3b97-360">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-360">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3b97-361">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-361">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-362">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-362">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e3b97-363">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-363">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3b97-364">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-364">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-365">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-365">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e3b97-366">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-367">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-367">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e3b97-368">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-369">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-369">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3b97-370">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-370">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3b97-371">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-371">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e3b97-372">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-372">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e3b97-373">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-373">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3b97-374">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-374">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e3b97-375">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-375">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e3b97-376">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-376">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-377">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-377">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e3b97-378">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="e3b97-378">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3b97-379">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-379">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-380">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-380">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e3b97-381">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-381">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e3b97-382">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-382">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-383">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-383">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e3b97-384">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-384">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3b97-385">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-385">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e3b97-386">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="e3b97-386">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e3b97-387">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-387">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e3b97-388">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-388">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3b97-389">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-389">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-390">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-390">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-391">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e3b97-391">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e3b97-392">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-392">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e3b97-393">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-393">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="e3b97-394">**page**</span><span class="sxs-lookup"><span data-stu-id="e3b97-394">**page**</span></span>

<span data-ttu-id="e3b97-395">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-395">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e3b97-396">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-396">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e3b97-397">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="e3b97-397">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e3b97-398">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e3b97-398">**viewimports**</span></span>

<span data-ttu-id="e3b97-399">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e3b97-400">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-400">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e3b97-401">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e3b97-401">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e3b97-402">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="e3b97-402">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="e3b97-403">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-404">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e3b97-404">**classlib**</span></span>

<span data-ttu-id="e3b97-405">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-405">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3b97-406">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3b97-406">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e3b97-407">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-407">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e3b97-408">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-409">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e3b97-409">**mstest, xunit**</span></span>

<span data-ttu-id="e3b97-410">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e3b97-410">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e3b97-411">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-411">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-412">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e3b97-412">**globaljson**</span></span>

<span data-ttu-id="e3b97-413">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-413">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e3b97-414">**web**</span><span class="sxs-lookup"><span data-stu-id="e3b97-414">**web**</span></span>

<span data-ttu-id="e3b97-415">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-415">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e3b97-416">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-416">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-417">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e3b97-417">**webapi**</span></span>

<span data-ttu-id="e3b97-418">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="e3b97-418">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e3b97-419">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e3b97-419">The possible values are:</span></span>

- <span data-ttu-id="e3b97-420">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="e3b97-420">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e3b97-421">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="e3b97-421">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e3b97-422">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-422">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e3b97-423">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-423">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e3b97-424">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-424">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3b97-425">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-425">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-426">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-426">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e3b97-427">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-427">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3b97-428">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-428">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-429">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-429">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3b97-430">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-431">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-431">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e3b97-432">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-432">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e3b97-433">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-433">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-434">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-434">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e3b97-435">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-435">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e3b97-436">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-437">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-437">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e3b97-438">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="e3b97-438">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3b97-439">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-439">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-440">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-440">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e3b97-441">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-441">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3b97-442">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-442">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e3b97-443">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-443">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e3b97-444">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-444">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3b97-445">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-445">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-446">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-446">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-447">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e3b97-447">**mvc, razor**</span></span>

<span data-ttu-id="e3b97-448">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="e3b97-448">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e3b97-449">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="e3b97-449">The possible values are:</span></span>

- <span data-ttu-id="e3b97-450">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="e3b97-450">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e3b97-451">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-451">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e3b97-452">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="e3b97-452">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e3b97-453">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-453">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e3b97-454">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-454">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e3b97-455">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-455">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e3b97-456">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-456">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e3b97-457">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-457">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-458">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-458">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e3b97-459">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-459">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e3b97-460">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-460">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-461">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-461">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e3b97-462">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e3b97-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-463">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-463">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e3b97-464">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-465">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-465">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e3b97-466">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-466">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3b97-467">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-467">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e3b97-468">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3b97-468">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e3b97-469">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-469">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e3b97-470">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-470">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e3b97-471">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="e3b97-471">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e3b97-472">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-472">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-473">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-473">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e3b97-474">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="e3b97-474">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e3b97-475">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-475">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e3b97-476">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-476">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e3b97-477">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-477">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e3b97-478">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="e3b97-478">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e3b97-479">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-479">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e3b97-480">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e3b97-480">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e3b97-481">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e3b97-481">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e3b97-482">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="e3b97-482">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e3b97-483">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="e3b97-483">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e3b97-484">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-484">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e3b97-485">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e3b97-485">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e3b97-486">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="e3b97-486">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e3b97-487">**page**</span><span class="sxs-lookup"><span data-stu-id="e3b97-487">**page**</span></span>

<span data-ttu-id="e3b97-488">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-488">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e3b97-489">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-489">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e3b97-490">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="e3b97-490">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e3b97-491">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e3b97-491">**viewimports**</span></span>

<span data-ttu-id="e3b97-492">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="e3b97-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e3b97-493">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-493">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e3b97-494">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e3b97-494">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e3b97-495">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="e3b97-495">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="e3b97-496">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3b97-497">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="e3b97-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e3b97-498">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e3b97-499">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e3b97-499">**classlib**</span></span>

<span data-ttu-id="e3b97-500">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3b97-501">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="e3b97-501">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="e3b97-502">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-502">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="e3b97-503">**mvc**</span><span class="sxs-lookup"><span data-stu-id="e3b97-503">**mvc**</span></span>

<span data-ttu-id="e3b97-504">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e3b97-505">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="e3b97-505">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e3b97-506">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-506">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e3b97-507">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="e3b97-507">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="e3b97-508">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="e3b97-508">Values: `None` or `Individual`.</span></span> <span data-ttu-id="e3b97-509">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-509">The default value is `None`.</span></span>

<span data-ttu-id="e3b97-510">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e3b97-510">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="e3b97-511">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="e3b97-511">Values: `true` or `false`.</span></span> <span data-ttu-id="e3b97-512">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="e3b97-512">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e3b97-513">Beispiele</span><span class="sxs-lookup"><span data-stu-id="e3b97-513">Examples</span></span>

<span data-ttu-id="e3b97-514">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="e3b97-514">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="e3b97-515">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="e3b97-515">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="e3b97-516">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="e3b97-516">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="e3b97-517">Erstellen Sie eine neue xUnit-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="e3b97-517">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="e3b97-518">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="e3b97-518">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="e3b97-519">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="e3b97-519">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="e3b97-520">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="e3b97-520">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="e3b97-521">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3b97-521">See also</span></span>

* [<span data-ttu-id="e3b97-522">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="e3b97-522">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="e3b97-523">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="e3b97-523">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="e3b97-524">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="e3b97-524">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="e3b97-525">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="e3b97-525">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
