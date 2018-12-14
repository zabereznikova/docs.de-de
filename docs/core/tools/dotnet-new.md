---
title: dotnet new Befehl – .NET Core-CLI
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: a8d486f569f31d68d5659ac6a80d615474ef2506
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131481"
---
# <a name="dotnet-new"></a><span data-ttu-id="4bd90-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4bd90-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4bd90-104">name</span><span class="sxs-lookup"><span data-stu-id="4bd90-104">Name</span></span>

<span data-ttu-id="4bd90-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="4bd90-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4bd90-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="4bd90-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4bd90-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4bd90-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4bd90-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4bd90-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4bd90-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4bd90-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="4bd90-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4bd90-110">Description</span></span>

<span data-ttu-id="4bd90-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="4bd90-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="4bd90-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="4bd90-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="4bd90-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="4bd90-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="4bd90-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4bd90-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="4bd90-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="4bd90-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="4bd90-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="4bd90-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4bd90-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4bd90-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4bd90-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-118">The command contains a default list of templates.</span></span> <span data-ttu-id="4bd90-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4bd90-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="4bd90-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4bd90-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4bd90-122">Template description</span></span>                          | <span data-ttu-id="4bd90-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="4bd90-123">Template name</span></span>    | <span data-ttu-id="4bd90-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="4bd90-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="4bd90-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4bd90-125">Console application</span></span>                          | `console`        | <span data-ttu-id="4bd90-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="4bd90-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="4bd90-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="4bd90-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="4bd90-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-133">NUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="4bd90-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-135">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="4bd90-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="4bd90-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-136">[C#]</span></span>          |
| <span data-ttu-id="4bd90-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4bd90-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="4bd90-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-138">[C#]</span></span>          |
| <span data-ttu-id="4bd90-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4bd90-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="4bd90-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-140">[C#]</span></span>          |
| <span data-ttu-id="4bd90-141">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="4bd90-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="4bd90-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-142">[C#], F#</span></span>      |
| <span data-ttu-id="4bd90-143">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4bd90-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="4bd90-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-144">[C#], F#</span></span>      |
| <span data-ttu-id="4bd90-145">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="4bd90-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="4bd90-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="4bd90-146">`razor`, `webapp`</span></span>| <span data-ttu-id="4bd90-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-147">[C#]</span></span>          |
| <span data-ttu-id="4bd90-148">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="4bd90-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="4bd90-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-149">[C#]</span></span>          |
| <span data-ttu-id="4bd90-150">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="4bd90-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="4bd90-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-151">[C#]</span></span>          |
| <span data-ttu-id="4bd90-152">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="4bd90-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="4bd90-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-153">[C#]</span></span>          |
| <span data-ttu-id="4bd90-154">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="4bd90-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="4bd90-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-155">[C#], F#</span></span>      |
| <span data-ttu-id="4bd90-156">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="4bd90-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="4bd90-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-157">[C#]</span></span>          |
| <span data-ttu-id="4bd90-158">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="4bd90-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="4bd90-159">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bd90-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="4bd90-160">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bd90-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="4bd90-161">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="4bd90-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4bd90-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4bd90-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4bd90-163">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-163">The command contains a default list of templates.</span></span> <span data-ttu-id="4bd90-164">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4bd90-165">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="4bd90-166">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4bd90-167">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4bd90-167">Template description</span></span>                          | <span data-ttu-id="4bd90-168">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="4bd90-168">Template name</span></span> | <span data-ttu-id="4bd90-169">Sprachen</span><span class="sxs-lookup"><span data-stu-id="4bd90-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="4bd90-170">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4bd90-170">Console application</span></span>                          | `console`     | <span data-ttu-id="4bd90-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-172">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="4bd90-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="4bd90-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-174">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="4bd90-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-176">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="4bd90-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4bd90-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4bd90-178">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="4bd90-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="4bd90-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-179">[C#], F#</span></span>      |
| <span data-ttu-id="4bd90-180">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4bd90-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="4bd90-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-181">[C#], F#</span></span>      |
| <span data-ttu-id="4bd90-182">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="4bd90-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="4bd90-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-183">[C#]</span></span>          |
| <span data-ttu-id="4bd90-184">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="4bd90-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="4bd90-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-185">[C#]</span></span>          |
| <span data-ttu-id="4bd90-186">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="4bd90-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="4bd90-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-187">[C#]</span></span>          |
| <span data-ttu-id="4bd90-188">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="4bd90-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="4bd90-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-189">[C#]</span></span>          |
| <span data-ttu-id="4bd90-190">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="4bd90-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="4bd90-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-191">[C#], F#</span></span>      |
| <span data-ttu-id="4bd90-192">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="4bd90-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="4bd90-193">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bd90-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="4bd90-194">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bd90-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="4bd90-195">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="4bd90-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="4bd90-196">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="4bd90-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="4bd90-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4bd90-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="4bd90-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4bd90-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4bd90-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4bd90-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4bd90-200">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-200">The command contains a default list of templates.</span></span> <span data-ttu-id="4bd90-201">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="4bd90-202">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="4bd90-203">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4bd90-204">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4bd90-204">Template description</span></span>  | <span data-ttu-id="4bd90-205">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="4bd90-205">Template name</span></span> | <span data-ttu-id="4bd90-206">Sprachen</span><span class="sxs-lookup"><span data-stu-id="4bd90-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="4bd90-207">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="4bd90-207">Console application</span></span>  | `console`     | <span data-ttu-id="4bd90-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-208">[C#], F#</span></span>  |
| <span data-ttu-id="4bd90-209">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="4bd90-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="4bd90-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-210">[C#], F#</span></span>  |
| <span data-ttu-id="4bd90-211">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="4bd90-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-212">[C#], F#</span></span>  |
| <span data-ttu-id="4bd90-213">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="4bd90-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-214">[C#], F#</span></span>  |
| <span data-ttu-id="4bd90-215">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="4bd90-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="4bd90-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-216">[C#]</span></span>      |
| <span data-ttu-id="4bd90-217">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="4bd90-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="4bd90-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4bd90-218">[C#], F#</span></span>  |
| <span data-ttu-id="4bd90-219">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="4bd90-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="4bd90-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="4bd90-220">[C#]</span></span>      |
| <span data-ttu-id="4bd90-221">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bd90-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="4bd90-222">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4bd90-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="4bd90-223">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="4bd90-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="4bd90-224">Optionen</span><span class="sxs-lookup"><span data-stu-id="4bd90-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4bd90-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4bd90-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="4bd90-226">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4bd90-227">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="4bd90-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4bd90-228">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4bd90-228">Prints out help for the command.</span></span> <span data-ttu-id="4bd90-229">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4bd90-230">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4bd90-231">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="4bd90-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4bd90-232">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4bd90-233">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="4bd90-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4bd90-234">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4bd90-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4bd90-235">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4bd90-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="4bd90-236">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4bd90-237">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="4bd90-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4bd90-238">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-238">The language of the template to create.</span></span> <span data-ttu-id="4bd90-239">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4bd90-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4bd90-240">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="4bd90-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4bd90-241">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4bd90-242">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4bd90-243">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-243">The name for the created output.</span></span> <span data-ttu-id="4bd90-244">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="4bd90-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="4bd90-245">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4bd90-246">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-246">Location to place the generated output.</span></span> <span data-ttu-id="4bd90-247">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4bd90-248">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-248">Filters templates based on available types.</span></span> <span data-ttu-id="4bd90-249">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="4bd90-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4bd90-250">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4bd90-251">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="4bd90-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4bd90-252">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="4bd90-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="4bd90-253">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4bd90-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4bd90-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="4bd90-255">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4bd90-256">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="4bd90-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4bd90-257">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4bd90-257">Prints out help for the command.</span></span> <span data-ttu-id="4bd90-258">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4bd90-259">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4bd90-260">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="4bd90-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4bd90-261">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4bd90-262">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="4bd90-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4bd90-263">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4bd90-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4bd90-264">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4bd90-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="4bd90-265">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4bd90-266">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="4bd90-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4bd90-267">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-267">The language of the template to create.</span></span> <span data-ttu-id="4bd90-268">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4bd90-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4bd90-269">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="4bd90-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4bd90-270">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4bd90-271">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4bd90-272">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-272">The name for the created output.</span></span> <span data-ttu-id="4bd90-273">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="4bd90-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4bd90-274">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-274">Location to place the generated output.</span></span> <span data-ttu-id="4bd90-275">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4bd90-276">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-276">Filters templates based on available types.</span></span> <span data-ttu-id="4bd90-277">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="4bd90-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4bd90-278">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4bd90-279">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="4bd90-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4bd90-280">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="4bd90-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="4bd90-281">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="4bd90-282">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4bd90-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4bd90-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="4bd90-284">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="4bd90-285">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="4bd90-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="4bd90-286">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="4bd90-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4bd90-287">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="4bd90-287">Prints out help for the command.</span></span> <span data-ttu-id="4bd90-288">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="4bd90-289">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4bd90-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="4bd90-290">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4bd90-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4bd90-291">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="4bd90-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="4bd90-292">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-292">The language of the template to create.</span></span> <span data-ttu-id="4bd90-293">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4bd90-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4bd90-294">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="4bd90-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4bd90-295">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4bd90-296">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4bd90-297">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-297">The name for the created output.</span></span> <span data-ttu-id="4bd90-298">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="4bd90-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4bd90-299">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-299">Location to place the generated output.</span></span> <span data-ttu-id="4bd90-300">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="4bd90-301">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="4bd90-301">Template options</span></span>

<span data-ttu-id="4bd90-302">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="4bd90-302">Each project template may have additional options available.</span></span> <span data-ttu-id="4bd90-303">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="4bd90-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4bd90-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4bd90-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4bd90-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="4bd90-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="4bd90-306">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4bd90-307">**classlib**</span></span>

<span data-ttu-id="4bd90-308">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4bd90-309">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4bd90-310">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4bd90-311">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4bd90-312">**mstest, xunit**</span></span>

<span data-ttu-id="4bd90-313">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4bd90-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4bd90-314">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4bd90-315">**globaljson**</span></span>

<span data-ttu-id="4bd90-316">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4bd90-317">**web**</span><span class="sxs-lookup"><span data-stu-id="4bd90-317">**web**</span></span>

<span data-ttu-id="4bd90-318">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="4bd90-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4bd90-319">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-320">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4bd90-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4bd90-321">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="4bd90-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4bd90-322">**webapi**</span></span>

<span data-ttu-id="4bd90-323">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="4bd90-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4bd90-324">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4bd90-324">The possible values are:</span></span>

- <span data-ttu-id="4bd90-325">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="4bd90-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4bd90-326">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="4bd90-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4bd90-327">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4bd90-328">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4bd90-329">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4bd90-330">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-331">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4bd90-332">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4bd90-333">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-334">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4bd90-335">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-336">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4bd90-337">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4bd90-338">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-339">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4bd90-340">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4bd90-341">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-342">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4bd90-343">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="4bd90-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4bd90-344">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-345">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4bd90-346">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4bd90-347">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4bd90-348">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="4bd90-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4bd90-349">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4bd90-350">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-351">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-352">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4bd90-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4bd90-353">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4bd90-354">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4bd90-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4bd90-355">**mvc, razor**</span></span>

<span data-ttu-id="4bd90-356">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="4bd90-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4bd90-357">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4bd90-357">The possible values are:</span></span>

- <span data-ttu-id="4bd90-358">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="4bd90-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4bd90-359">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4bd90-360">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="4bd90-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4bd90-361">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4bd90-362">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4bd90-363">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4bd90-364">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4bd90-365">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-366">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4bd90-367">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4bd90-368">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-369">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4bd90-370">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-371">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4bd90-372">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-373">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4bd90-374">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4bd90-375">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4bd90-376">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4bd90-377">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4bd90-378">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4bd90-379">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4bd90-380">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-381">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4bd90-382">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="4bd90-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4bd90-383">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-384">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4bd90-385">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4bd90-386">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-387">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4bd90-388">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4bd90-389">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4bd90-390">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="4bd90-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4bd90-391">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4bd90-392">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4bd90-393">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-394">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-395">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4bd90-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4bd90-396">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4bd90-397">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4bd90-398">**page**</span><span class="sxs-lookup"><span data-stu-id="4bd90-398">**page**</span></span>

<span data-ttu-id="4bd90-399">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4bd90-400">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4bd90-401">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="4bd90-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4bd90-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4bd90-402">**viewimports**</span></span>

<span data-ttu-id="4bd90-403">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4bd90-404">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4bd90-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4bd90-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4bd90-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="4bd90-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="4bd90-407">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4bd90-408">**classlib**</span></span>

<span data-ttu-id="4bd90-409">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4bd90-410">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4bd90-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4bd90-411">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4bd90-412">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4bd90-413">**mstest, xunit**</span></span>

<span data-ttu-id="4bd90-414">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4bd90-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4bd90-415">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4bd90-416">**globaljson**</span></span>

<span data-ttu-id="4bd90-417">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4bd90-418">**web**</span><span class="sxs-lookup"><span data-stu-id="4bd90-418">**web**</span></span>

<span data-ttu-id="4bd90-419">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4bd90-420">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4bd90-421">**webapi**</span></span>

<span data-ttu-id="4bd90-422">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="4bd90-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4bd90-423">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4bd90-423">The possible values are:</span></span>

- <span data-ttu-id="4bd90-424">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="4bd90-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4bd90-425">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="4bd90-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4bd90-426">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4bd90-427">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4bd90-428">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4bd90-429">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-430">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4bd90-431">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4bd90-432">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-433">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4bd90-434">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-435">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4bd90-436">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4bd90-437">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-438">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4bd90-439">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4bd90-440">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-441">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4bd90-442">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="4bd90-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4bd90-443">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-444">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4bd90-445">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4bd90-446">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4bd90-447">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4bd90-448">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4bd90-449">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-450">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4bd90-451">**mvc, razor**</span></span>

<span data-ttu-id="4bd90-452">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="4bd90-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4bd90-453">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="4bd90-453">The possible values are:</span></span>

- <span data-ttu-id="4bd90-454">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="4bd90-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4bd90-455">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4bd90-456">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="4bd90-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4bd90-457">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4bd90-458">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4bd90-459">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4bd90-460">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4bd90-461">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-462">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4bd90-463">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4bd90-464">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-465">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4bd90-466">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4bd90-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-467">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4bd90-468">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-469">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4bd90-470">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4bd90-471">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4bd90-472">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd90-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4bd90-473">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4bd90-474">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4bd90-475">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="4bd90-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4bd90-476">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-477">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4bd90-478">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="4bd90-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4bd90-479">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4bd90-480">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4bd90-481">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4bd90-482">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="4bd90-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4bd90-483">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4bd90-484">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="4bd90-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4bd90-485">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="4bd90-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4bd90-486">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="4bd90-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4bd90-487">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="4bd90-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4bd90-488">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4bd90-489">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4bd90-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4bd90-490">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="4bd90-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4bd90-491">**page**</span><span class="sxs-lookup"><span data-stu-id="4bd90-491">**page**</span></span>

<span data-ttu-id="4bd90-492">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4bd90-493">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4bd90-494">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="4bd90-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4bd90-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4bd90-495">**viewimports**</span></span>

<span data-ttu-id="4bd90-496">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="4bd90-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4bd90-497">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4bd90-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4bd90-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4bd90-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="4bd90-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="4bd90-500">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4bd90-501">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="4bd90-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4bd90-502">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4bd90-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4bd90-503">**classlib**</span></span>

<span data-ttu-id="4bd90-504">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4bd90-505">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="4bd90-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="4bd90-506">Der Standardwert ist `netstandard1.4`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="4bd90-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="4bd90-507">**mvc**</span></span>

<span data-ttu-id="4bd90-508">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4bd90-509">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="4bd90-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4bd90-510">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4bd90-511">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="4bd90-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="4bd90-512">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="4bd90-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="4bd90-513">Der Standardwert ist `None`.</span><span class="sxs-lookup"><span data-stu-id="4bd90-513">The default value is `None`.</span></span>

<span data-ttu-id="4bd90-514">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd90-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="4bd90-515">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="4bd90-515">Values: `true` or `false`.</span></span> <span data-ttu-id="4bd90-516">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="4bd90-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4bd90-517">Beispiele</span><span class="sxs-lookup"><span data-stu-id="4bd90-517">Examples</span></span>

<span data-ttu-id="4bd90-518">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="4bd90-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="4bd90-519">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="4bd90-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="4bd90-520">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="4bd90-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="4bd90-521">Erstellen Sie eine neue xUnit-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="4bd90-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="4bd90-522">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="4bd90-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="4bd90-523">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="4bd90-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="4bd90-524">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="4bd90-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="4bd90-525">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bd90-525">See also</span></span>

* [<span data-ttu-id="4bd90-526">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="4bd90-526">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="4bd90-527">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="4bd90-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="4bd90-528">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="4bd90-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="4bd90-529">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="4bd90-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
