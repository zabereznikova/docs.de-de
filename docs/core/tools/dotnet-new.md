---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: 56d76f1dd54097f9cf20129d74057235290c273c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188200"
---
# <a name="dotnet-new"></a><span data-ttu-id="adca4-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="adca4-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="adca4-104">name</span><span class="sxs-lookup"><span data-stu-id="adca4-104">Name</span></span>

<span data-ttu-id="adca4-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="adca4-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="adca4-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="adca4-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="adca4-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="adca4-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="adca4-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="adca4-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="adca4-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="adca4-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="adca4-110">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="adca4-110">Description</span></span>

<span data-ttu-id="adca4-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="adca4-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="adca4-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="adca4-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="adca4-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="adca4-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="adca4-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="adca4-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="adca4-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="adca4-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="adca4-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="adca4-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="adca4-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="adca4-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="adca4-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="adca4-118">The command contains a default list of templates.</span></span> <span data-ttu-id="adca4-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="adca4-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="adca4-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="adca4-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="adca4-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="adca4-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="adca4-122">Template description</span></span>                          | <span data-ttu-id="adca4-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="adca4-123">Template name</span></span>    | <span data-ttu-id="adca4-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="adca4-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="adca4-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="adca4-125">Console application</span></span>                          | `console`        | <span data-ttu-id="adca4-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="adca4-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="adca4-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="adca4-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="adca4-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="adca4-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="adca4-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-133">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="adca4-133">Razor page</span></span>                                   | `page`           | <span data-ttu-id="adca4-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-134">[C#]</span></span>          |
| <span data-ttu-id="adca4-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="adca4-135">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="adca4-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-136">[C#]</span></span>          |
| <span data-ttu-id="adca4-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="adca4-137">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="adca4-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-138">[C#]</span></span>          |
| <span data-ttu-id="adca4-139">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="adca4-139">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="adca4-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-140">[C#], F#</span></span>      |
| <span data-ttu-id="adca4-141">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="adca4-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="adca4-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-142">[C#], F#</span></span>      |
| <span data-ttu-id="adca4-143">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="adca4-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="adca4-144">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="adca4-144">`razor`, `webapp`</span></span>| <span data-ttu-id="adca4-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-145">[C#]</span></span>          |
| <span data-ttu-id="adca4-146">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="adca4-146">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="adca4-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-147">[C#]</span></span>          |
| <span data-ttu-id="adca4-148">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="adca4-148">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="adca4-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-149">[C#]</span></span>          |
| <span data-ttu-id="adca4-150">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="adca4-150">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="adca4-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-151">[C#]</span></span>          |
| <span data-ttu-id="adca4-152">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="adca4-152">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="adca4-153">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-153">[C#], F#</span></span>      |
| <span data-ttu-id="adca4-154">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="adca4-154">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="adca4-155">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-155">[C#]</span></span>          |
| <span data-ttu-id="adca4-156">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="adca4-156">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="adca4-157">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="adca4-157">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="adca4-158">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="adca4-158">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="adca4-159">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="adca4-159">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="adca4-160">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="adca4-160">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="adca4-161">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="adca4-161">The command contains a default list of templates.</span></span> <span data-ttu-id="adca4-162">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="adca4-162">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="adca4-163">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-163">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="adca4-164">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="adca4-164">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="adca4-165">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="adca4-165">Template description</span></span>                          | <span data-ttu-id="adca4-166">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="adca4-166">Template name</span></span> | <span data-ttu-id="adca4-167">Sprachen</span><span class="sxs-lookup"><span data-stu-id="adca4-167">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="adca4-168">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="adca4-168">Console application</span></span>                          | `console`     | <span data-ttu-id="adca4-169">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-169">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-170">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="adca4-170">Class library</span></span>                                | `classlib`    | <span data-ttu-id="adca4-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-172">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="adca4-172">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="adca4-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-174">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="adca4-174">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="adca4-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="adca4-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="adca4-176">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="adca4-176">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="adca4-177">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-177">[C#], F#</span></span>      |
| <span data-ttu-id="adca4-178">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="adca4-178">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="adca4-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-179">[C#], F#</span></span>      |
| <span data-ttu-id="adca4-180">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="adca4-180">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="adca4-181">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-181">[C#]</span></span>          |
| <span data-ttu-id="adca4-182">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="adca4-182">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="adca4-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-183">[C#]</span></span>          |
| <span data-ttu-id="adca4-184">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="adca4-184">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="adca4-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-185">[C#]</span></span>          |
| <span data-ttu-id="adca4-186">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="adca4-186">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="adca4-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-187">[C#]</span></span>          |
| <span data-ttu-id="adca4-188">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="adca4-188">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="adca4-189">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-189">[C#], F#</span></span>      |
| <span data-ttu-id="adca4-190">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="adca4-190">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="adca4-191">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="adca4-191">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="adca4-192">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="adca4-192">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="adca4-193">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="adca4-193">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="adca4-194">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="adca4-194">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="adca4-195">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="adca4-195">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="adca4-196">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="adca4-196">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="adca4-197">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="adca4-197">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="adca4-198">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="adca4-198">The command contains a default list of templates.</span></span> <span data-ttu-id="adca4-199">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="adca4-199">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="adca4-200">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-200">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="adca4-201">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="adca4-201">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="adca4-202">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="adca4-202">Template description</span></span>  | <span data-ttu-id="adca4-203">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="adca4-203">Template name</span></span> | <span data-ttu-id="adca4-204">Sprachen</span><span class="sxs-lookup"><span data-stu-id="adca4-204">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="adca4-205">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="adca4-205">Console application</span></span>  | `console`     | <span data-ttu-id="adca4-206">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-206">[C#], F#</span></span>  |
| <span data-ttu-id="adca4-207">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="adca4-207">Class library</span></span>        | `classlib`    | <span data-ttu-id="adca4-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-208">[C#], F#</span></span>  |
| <span data-ttu-id="adca4-209">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="adca4-209">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="adca4-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-210">[C#], F#</span></span>  |
| <span data-ttu-id="adca4-211">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="adca4-211">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="adca4-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-212">[C#], F#</span></span>  |
| <span data-ttu-id="adca4-213">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="adca4-213">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="adca4-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-214">[C#]</span></span>      |
| <span data-ttu-id="adca4-215">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="adca4-215">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="adca4-216">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="adca4-216">[C#], F#</span></span>  |
| <span data-ttu-id="adca4-217">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="adca4-217">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="adca4-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="adca4-218">[C#]</span></span>      |
| <span data-ttu-id="adca4-219">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="adca4-219">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="adca4-220">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="adca4-220">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="adca4-221">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="adca4-221">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="adca4-222">Optionen</span><span class="sxs-lookup"><span data-stu-id="adca4-222">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="adca4-223">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="adca4-223">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="adca4-224">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-224">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="adca4-225">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="adca4-225">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="adca4-226">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="adca4-226">Prints out help for the command.</span></span> <span data-ttu-id="adca4-227">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-227">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="adca4-228">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="adca4-228">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="adca4-229">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="adca4-229">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="adca4-230">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="adca4-230">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="adca4-231">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="adca4-231">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="adca4-232">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="adca4-232">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="adca4-233">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="adca4-233">Lists templates containing the specified name.</span></span> <span data-ttu-id="adca4-234">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-234">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="adca4-235">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="adca4-235">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="adca4-236">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="adca4-236">The language of the template to create.</span></span> <span data-ttu-id="adca4-237">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="adca4-237">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="adca4-238">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="adca4-238">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="adca4-239">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="adca4-239">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="adca4-240">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="adca4-240">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="adca4-241">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-241">The name for the created output.</span></span> <span data-ttu-id="adca4-242">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="adca4-242">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="adca4-243">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-243">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="adca4-244">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-244">Location to place the generated output.</span></span> <span data-ttu-id="adca4-245">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-245">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="adca4-246">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="adca4-246">Filters templates based on available types.</span></span> <span data-ttu-id="adca4-247">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="adca4-247">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="adca4-248">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="adca4-248">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="adca4-249">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="adca4-249">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="adca4-250">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="adca4-250">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="adca4-251">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="adca4-251">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="adca4-252">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="adca4-252">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="adca4-253">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-253">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="adca4-254">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="adca4-254">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="adca4-255">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="adca4-255">Prints out help for the command.</span></span> <span data-ttu-id="adca4-256">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-256">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="adca4-257">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="adca4-257">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="adca4-258">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="adca4-258">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="adca4-259">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="adca4-259">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="adca4-260">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="adca4-260">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="adca4-261">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="adca4-261">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="adca4-262">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="adca4-262">Lists templates containing the specified name.</span></span> <span data-ttu-id="adca4-263">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-263">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="adca4-264">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="adca4-264">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="adca4-265">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="adca4-265">The language of the template to create.</span></span> <span data-ttu-id="adca4-266">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="adca4-266">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="adca4-267">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="adca4-267">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="adca4-268">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="adca4-268">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="adca4-269">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="adca4-269">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="adca4-270">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-270">The name for the created output.</span></span> <span data-ttu-id="adca4-271">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="adca4-271">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="adca4-272">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-272">Location to place the generated output.</span></span> <span data-ttu-id="adca4-273">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-273">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="adca4-274">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="adca4-274">Filters templates based on available types.</span></span> <span data-ttu-id="adca4-275">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="adca4-275">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="adca4-276">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="adca4-276">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="adca4-277">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="adca4-277">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="adca4-278">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="adca4-278">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="adca4-279">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="adca4-279">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="adca4-280">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-280">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="adca4-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="adca4-281">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="adca4-282">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="adca4-282">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="adca4-283">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="adca4-283">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="adca4-284">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="adca4-284">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="adca4-285">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="adca4-285">Prints out help for the command.</span></span> <span data-ttu-id="adca4-286">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-286">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="adca4-287">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="adca4-287">Lists templates containing the specified name.</span></span> <span data-ttu-id="adca4-288">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="adca4-288">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="adca4-289">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="adca4-289">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="adca4-290">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="adca4-290">The language of the template to create.</span></span> <span data-ttu-id="adca4-291">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="adca4-291">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="adca4-292">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="adca4-292">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="adca4-293">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="adca4-293">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="adca4-294">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="adca4-294">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="adca4-295">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-295">The name for the created output.</span></span> <span data-ttu-id="adca4-296">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="adca4-296">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="adca4-297">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-297">Location to place the generated output.</span></span> <span data-ttu-id="adca4-298">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-298">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="adca4-299">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="adca4-299">Template options</span></span>

<span data-ttu-id="adca4-300">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="adca4-300">Each project template may have additional options available.</span></span> <span data-ttu-id="adca4-301">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="adca4-301">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="adca4-302">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="adca4-302">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="adca4-303">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="adca4-303">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="adca4-304">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-305">**classlib**</span><span class="sxs-lookup"><span data-stu-id="adca4-305">**classlib**</span></span>

<span data-ttu-id="adca4-306">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-306">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="adca4-307">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="adca4-307">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="adca4-308">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="adca4-308">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="adca4-309">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-310">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="adca4-310">**mstest, xunit**</span></span>

<span data-ttu-id="adca4-311">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="adca4-311">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="adca4-312">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-312">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-313">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="adca4-313">**globaljson**</span></span>

<span data-ttu-id="adca4-314">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-314">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="adca4-315">**web**</span><span class="sxs-lookup"><span data-stu-id="adca4-315">**web**</span></span>

<span data-ttu-id="adca4-316">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="adca4-316">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="adca4-317">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-317">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-318">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="adca4-318">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="adca4-319">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-319">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="adca4-320">**webapi**</span><span class="sxs-lookup"><span data-stu-id="adca4-320">**webapi**</span></span>

<span data-ttu-id="adca4-321">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="adca4-321">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="adca4-322">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="adca4-322">The possible values are:</span></span>

- <span data-ttu-id="adca4-323">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="adca4-323">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="adca4-324">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="adca4-324">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="adca4-325">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-325">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="adca4-326">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-326">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="adca4-327">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-327">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="adca4-328">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-328">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-329">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-329">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="adca4-330">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-330">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="adca4-331">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-331">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-332">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-332">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="adca4-333">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-333">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-334">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-334">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="adca4-335">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-335">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="adca4-336">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-336">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-337">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="adca4-337">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="adca4-338">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-338">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="adca4-339">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-339">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-340">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="adca4-340">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="adca4-341">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="adca4-341">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="adca4-342">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-342">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-343">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="adca4-343">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="adca4-344">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-344">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="adca4-345">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="adca4-345">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="adca4-346">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="adca4-346">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="adca4-347">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-347">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="adca4-348">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="adca4-348">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-349">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-349">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-350">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="adca4-350">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="adca4-351">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="adca4-351">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="adca4-352">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-352">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="adca4-353">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="adca4-353">**mvc, razor**</span></span>

<span data-ttu-id="adca4-354">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="adca4-354">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="adca4-355">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="adca4-355">The possible values are:</span></span>

- <span data-ttu-id="adca4-356">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="adca4-356">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="adca4-357">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-357">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="adca4-358">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="adca4-358">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="adca4-359">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-359">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="adca4-360">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-360">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="adca4-361">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-361">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="adca4-362">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-362">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="adca4-363">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-363">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-364">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-364">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="adca4-365">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-365">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="adca4-366">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-367">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="adca4-367">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="adca4-368">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="adca4-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-369">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="adca4-369">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="adca4-370">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-371">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-371">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="adca4-372">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-372">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="adca4-373">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-373">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="adca4-374">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-374">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="adca4-375">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-375">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="adca4-376">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="adca4-376">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="adca4-377">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-377">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="adca4-378">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-378">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-379">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="adca4-379">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="adca4-380">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="adca4-380">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="adca4-381">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-381">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-382">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="adca4-382">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="adca4-383">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="adca4-383">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="adca4-384">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-384">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-385">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="adca4-385">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="adca4-386">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-386">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="adca4-387">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="adca4-387">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="adca4-388">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="adca4-388">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="adca4-389">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="adca4-389">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="adca4-390">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-390">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="adca4-391">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="adca4-391">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-392">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-392">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-393">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="adca4-393">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="adca4-394">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="adca4-394">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="adca4-395">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adca4-395">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="adca4-396">**page**</span><span class="sxs-lookup"><span data-stu-id="adca4-396">**page**</span></span>

<span data-ttu-id="adca4-397">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="adca4-397">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="adca4-398">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="adca4-398">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="adca4-399">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="adca4-399">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="adca4-400">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="adca4-400">**viewimports**</span></span>

<span data-ttu-id="adca4-401">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="adca4-401">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="adca4-402">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="adca4-402">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="adca4-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="adca4-403">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="adca4-404">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="adca4-404">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="adca4-405">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-405">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-406">**classlib**</span><span class="sxs-lookup"><span data-stu-id="adca4-406">**classlib**</span></span>

<span data-ttu-id="adca4-407">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-407">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="adca4-408">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="adca4-408">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="adca4-409">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="adca4-409">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="adca4-410">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-410">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-411">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="adca4-411">**mstest, xunit**</span></span>

<span data-ttu-id="adca4-412">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="adca4-412">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="adca4-413">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-413">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-414">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="adca4-414">**globaljson**</span></span>

<span data-ttu-id="adca4-415">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-415">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="adca4-416">**web**</span><span class="sxs-lookup"><span data-stu-id="adca4-416">**web**</span></span>

<span data-ttu-id="adca4-417">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-417">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="adca4-418">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-418">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-419">**webapi**</span><span class="sxs-lookup"><span data-stu-id="adca4-419">**webapi**</span></span>

<span data-ttu-id="adca4-420">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="adca4-420">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="adca4-421">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="adca4-421">The possible values are:</span></span>

- <span data-ttu-id="adca4-422">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="adca4-422">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="adca4-423">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="adca4-423">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="adca4-424">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-424">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="adca4-425">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-425">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="adca4-426">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-426">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="adca4-427">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-427">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-428">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-428">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="adca4-429">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-429">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="adca4-430">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-430">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-431">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-431">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="adca4-432">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-432">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-433">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-433">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="adca4-434">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-434">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="adca4-435">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-435">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-436">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="adca4-436">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="adca4-437">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-437">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="adca4-438">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-438">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-439">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="adca4-439">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="adca4-440">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="adca4-440">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="adca4-441">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-441">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-442">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="adca4-442">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="adca4-443">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-443">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="adca4-444">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-444">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="adca4-445">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-445">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="adca4-446">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-446">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="adca4-447">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="adca4-447">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-448">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-448">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-449">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="adca4-449">**mvc, razor**</span></span>

<span data-ttu-id="adca4-450">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="adca4-450">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="adca4-451">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="adca4-451">The possible values are:</span></span>

- <span data-ttu-id="adca4-452">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="adca4-452">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="adca4-453">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-453">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="adca4-454">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="adca4-454">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="adca4-455">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-455">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="adca4-456">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-456">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="adca4-457">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-457">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="adca4-458">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-458">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="adca4-459">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-459">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-460">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-460">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="adca4-461">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-461">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="adca4-462">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-463">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="adca4-463">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="adca4-464">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="adca4-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-465">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="adca4-465">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="adca4-466">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-467">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-467">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="adca4-468">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-468">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="adca4-469">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="adca4-469">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="adca4-470">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="adca4-470">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="adca4-471">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-471">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="adca4-472">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="adca4-472">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="adca4-473">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="adca4-473">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="adca4-474">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-474">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-475">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="adca4-475">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="adca4-476">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="adca4-476">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="adca4-477">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-477">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="adca4-478">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="adca4-478">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="adca4-479">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="adca4-479">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="adca4-480">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="adca4-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="adca4-481">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="adca4-481">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="adca4-482">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="adca4-482">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="adca4-483">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="adca4-483">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="adca4-484">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="adca4-484">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="adca4-485">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="adca4-485">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="adca4-486">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-486">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="adca4-487">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="adca4-487">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="adca4-488">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="adca4-488">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="adca4-489">**page**</span><span class="sxs-lookup"><span data-stu-id="adca4-489">**page**</span></span>

<span data-ttu-id="adca4-490">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="adca4-490">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="adca4-491">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="adca4-491">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="adca4-492">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="adca4-492">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="adca4-493">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="adca4-493">**viewimports**</span></span>

<span data-ttu-id="adca4-494">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="adca4-494">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="adca4-495">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="adca4-495">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="adca4-496">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="adca4-496">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="adca4-497">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="adca4-497">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="adca4-498">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-498">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="adca4-499">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="adca4-499">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="adca4-500">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="adca4-500">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="adca4-501">**classlib**</span><span class="sxs-lookup"><span data-stu-id="adca4-501">**classlib**</span></span>

<span data-ttu-id="adca4-502">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-502">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="adca4-503">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="adca4-503">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="adca4-504">Der Standardwert ist `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="adca4-504">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="adca4-505">**mvc**</span><span class="sxs-lookup"><span data-stu-id="adca4-505">**mvc**</span></span>

<span data-ttu-id="adca4-506">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-506">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="adca4-507">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="adca4-507">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="adca4-508">Der Standardwert ist `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="adca4-508">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="adca4-509">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="adca4-509">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="adca4-510">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="adca4-510">Values: `None` or `Individual`.</span></span> <span data-ttu-id="adca4-511">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="adca4-511">The default value is `None`.</span></span>

<span data-ttu-id="adca4-512">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="adca4-512">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="adca4-513">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="adca4-513">Values: `true` or `false`.</span></span> <span data-ttu-id="adca4-514">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="adca4-514">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="adca4-515">Beispiele</span><span class="sxs-lookup"><span data-stu-id="adca4-515">Examples</span></span>

<span data-ttu-id="adca4-516">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="adca4-516">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="adca4-517">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="adca4-517">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="adca4-518">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="adca4-518">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="adca4-519">Erstellen Sie eine neue xUnit-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="adca4-519">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="adca4-520">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="adca4-520">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="adca4-521">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="adca4-521">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="adca4-522">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="adca4-522">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="adca4-523">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adca4-523">See also</span></span>

* [<span data-ttu-id="adca4-524">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="adca4-524">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="adca4-525">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="adca4-525">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="adca4-526">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="adca4-526">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="adca4-527">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="adca4-527">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
