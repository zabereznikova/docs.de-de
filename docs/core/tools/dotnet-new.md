---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 10/24/2018
ms.openlocfilehash: 5177c920fee6fa946d2bf5d96644f26309ed0a99
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516147"
---
# <a name="dotnet-new"></a><span data-ttu-id="667d8-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="667d8-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="667d8-104">name</span><span class="sxs-lookup"><span data-stu-id="667d8-104">Name</span></span>

<span data-ttu-id="667d8-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="667d8-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="667d8-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="667d8-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="667d8-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="667d8-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="667d8-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="667d8-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="667d8-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="667d8-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="667d8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="667d8-110">Description</span></span>

<span data-ttu-id="667d8-111">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="667d8-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="667d8-112">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="667d8-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="667d8-113">Argumente</span><span class="sxs-lookup"><span data-stu-id="667d8-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="667d8-114">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="667d8-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="667d8-115">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="667d8-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="667d8-116">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="667d8-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="667d8-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="667d8-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="667d8-118">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="667d8-118">The command contains a default list of templates.</span></span> <span data-ttu-id="667d8-119">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="667d8-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="667d8-120">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="667d8-121">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="667d8-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="667d8-122">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="667d8-122">Template description</span></span>                          | <span data-ttu-id="667d8-123">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="667d8-123">Template name</span></span>    | <span data-ttu-id="667d8-124">Sprachen</span><span class="sxs-lookup"><span data-stu-id="667d8-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="667d8-125">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="667d8-125">Console application</span></span>                          | `console`        | <span data-ttu-id="667d8-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-127">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="667d8-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="667d8-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-129">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="667d8-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-131">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="667d8-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-133">NUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="667d8-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-135">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="667d8-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="667d8-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-136">[C#]</span></span>          |
| <span data-ttu-id="667d8-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="667d8-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="667d8-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-138">[C#]</span></span>          |
| <span data-ttu-id="667d8-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="667d8-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="667d8-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-140">[C#]</span></span>          |
| <span data-ttu-id="667d8-141">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="667d8-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="667d8-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-142">[C#], F#</span></span>      |
| <span data-ttu-id="667d8-143">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="667d8-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="667d8-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-144">[C#], F#</span></span>      |
| <span data-ttu-id="667d8-145">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="667d8-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="667d8-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="667d8-146">`razor`, `webapp`</span></span>| <span data-ttu-id="667d8-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-147">[C#]</span></span>          |
| <span data-ttu-id="667d8-148">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="667d8-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="667d8-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-149">[C#]</span></span>          |
| <span data-ttu-id="667d8-150">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="667d8-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="667d8-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-151">[C#]</span></span>          |
| <span data-ttu-id="667d8-152">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="667d8-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="667d8-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-153">[C#]</span></span>          |
| <span data-ttu-id="667d8-154">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="667d8-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="667d8-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-155">[C#], F#</span></span>      |
| <span data-ttu-id="667d8-156">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="667d8-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="667d8-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-157">[C#]</span></span>          |
| <span data-ttu-id="667d8-158">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="667d8-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="667d8-159">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="667d8-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="667d8-160">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="667d8-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="667d8-161">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="667d8-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="667d8-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="667d8-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="667d8-163">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="667d8-163">The command contains a default list of templates.</span></span> <span data-ttu-id="667d8-164">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="667d8-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="667d8-165">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="667d8-166">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="667d8-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="667d8-167">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="667d8-167">Template description</span></span>                          | <span data-ttu-id="667d8-168">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="667d8-168">Template name</span></span> | <span data-ttu-id="667d8-169">Sprachen</span><span class="sxs-lookup"><span data-stu-id="667d8-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="667d8-170">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="667d8-170">Console application</span></span>                          | `console`     | <span data-ttu-id="667d8-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-172">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="667d8-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="667d8-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-174">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="667d8-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-176">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="667d8-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="667d8-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="667d8-178">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="667d8-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="667d8-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-179">[C#], F#</span></span>      |
| <span data-ttu-id="667d8-180">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="667d8-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="667d8-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-181">[C#], F#</span></span>      |
| <span data-ttu-id="667d8-182">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="667d8-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="667d8-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-183">[C#]</span></span>          |
| <span data-ttu-id="667d8-184">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="667d8-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="667d8-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-185">[C#]</span></span>          |
| <span data-ttu-id="667d8-186">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="667d8-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="667d8-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-187">[C#]</span></span>          |
| <span data-ttu-id="667d8-188">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="667d8-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="667d8-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-189">[C#]</span></span>          |
| <span data-ttu-id="667d8-190">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="667d8-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="667d8-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-191">[C#], F#</span></span>      |
| <span data-ttu-id="667d8-192">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="667d8-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="667d8-193">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="667d8-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="667d8-194">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="667d8-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="667d8-195">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="667d8-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="667d8-196">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="667d8-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="667d8-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="667d8-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="667d8-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="667d8-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="667d8-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="667d8-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="667d8-200">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="667d8-200">The command contains a default list of templates.</span></span> <span data-ttu-id="667d8-201">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="667d8-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="667d8-202">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 1.x vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="667d8-203">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="667d8-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="667d8-204">Vorlagenbeschreibung</span><span class="sxs-lookup"><span data-stu-id="667d8-204">Template description</span></span>  | <span data-ttu-id="667d8-205">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="667d8-205">Template name</span></span> | <span data-ttu-id="667d8-206">Sprachen</span><span class="sxs-lookup"><span data-stu-id="667d8-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="667d8-207">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="667d8-207">Console application</span></span>  | `console`     | <span data-ttu-id="667d8-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-208">[C#], F#</span></span>  |
| <span data-ttu-id="667d8-209">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="667d8-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="667d8-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-210">[C#], F#</span></span>  |
| <span data-ttu-id="667d8-211">Unittestprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="667d8-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-212">[C#], F#</span></span>  |
| <span data-ttu-id="667d8-213">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="667d8-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="667d8-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-214">[C#], F#</span></span>  |
| <span data-ttu-id="667d8-215">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="667d8-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="667d8-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-216">[C#]</span></span>      |
| <span data-ttu-id="667d8-217">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="667d8-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="667d8-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="667d8-218">[C#], F#</span></span>  |
| <span data-ttu-id="667d8-219">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="667d8-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="667d8-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="667d8-220">[C#]</span></span>      |
| <span data-ttu-id="667d8-221">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="667d8-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="667d8-222">Web-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="667d8-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="667d8-223">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="667d8-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="667d8-224">Optionen</span><span class="sxs-lookup"><span data-stu-id="667d8-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="667d8-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="667d8-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="667d8-226">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="667d8-227">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="667d8-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="667d8-228">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="667d8-228">Prints out help for the command.</span></span> <span data-ttu-id="667d8-229">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="667d8-230">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="667d8-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="667d8-231">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="667d8-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="667d8-232">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="667d8-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="667d8-233">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="667d8-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="667d8-234">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="667d8-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="667d8-235">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="667d8-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="667d8-236">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="667d8-237">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="667d8-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="667d8-238">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="667d8-238">The language of the template to create.</span></span> <span data-ttu-id="667d8-239">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="667d8-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="667d8-240">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="667d8-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="667d8-241">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="667d8-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="667d8-242">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="667d8-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="667d8-243">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-243">The name for the created output.</span></span> <span data-ttu-id="667d8-244">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="667d8-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="667d8-245">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="667d8-246">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-246">Location to place the generated output.</span></span> <span data-ttu-id="667d8-247">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="667d8-248">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="667d8-248">Filters templates based on available types.</span></span> <span data-ttu-id="667d8-249">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="667d8-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="667d8-250">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="667d8-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="667d8-251">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="667d8-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="667d8-252">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="667d8-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="667d8-253">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="667d8-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="667d8-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="667d8-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="667d8-255">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="667d8-256">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="667d8-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="667d8-257">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="667d8-257">Prints out help for the command.</span></span> <span data-ttu-id="667d8-258">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="667d8-259">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="667d8-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="667d8-260">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="667d8-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="667d8-261">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="667d8-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="667d8-262">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="667d8-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="667d8-263">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="667d8-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="667d8-264">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="667d8-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="667d8-265">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="667d8-266">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="667d8-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="667d8-267">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="667d8-267">The language of the template to create.</span></span> <span data-ttu-id="667d8-268">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="667d8-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="667d8-269">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="667d8-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="667d8-270">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="667d8-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="667d8-271">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="667d8-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="667d8-272">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-272">The name for the created output.</span></span> <span data-ttu-id="667d8-273">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="667d8-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="667d8-274">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-274">Location to place the generated output.</span></span> <span data-ttu-id="667d8-275">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="667d8-276">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="667d8-276">Filters templates based on available types.</span></span> <span data-ttu-id="667d8-277">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="667d8-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="667d8-278">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="667d8-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="667d8-279">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="667d8-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="667d8-280">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="667d8-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="667d8-281">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="667d8-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="667d8-282">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="667d8-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="667d8-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="667d8-284">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="667d8-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="667d8-285">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="667d8-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="667d8-286">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="667d8-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="667d8-287">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="667d8-287">Prints out help for the command.</span></span> <span data-ttu-id="667d8-288">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="667d8-289">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="667d8-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="667d8-290">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="667d8-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="667d8-291">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="667d8-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="667d8-292">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="667d8-292">The language of the template to create.</span></span> <span data-ttu-id="667d8-293">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="667d8-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="667d8-294">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="667d8-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="667d8-295">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="667d8-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="667d8-296">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="667d8-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="667d8-297">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-297">The name for the created output.</span></span> <span data-ttu-id="667d8-298">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="667d8-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="667d8-299">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-299">Location to place the generated output.</span></span> <span data-ttu-id="667d8-300">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="667d8-301">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="667d8-301">Template options</span></span>

<span data-ttu-id="667d8-302">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="667d8-302">Each project template may have additional options available.</span></span> <span data-ttu-id="667d8-303">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="667d8-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="667d8-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="667d8-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="667d8-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="667d8-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="667d8-306">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="667d8-307">**classlib**</span></span>

<span data-ttu-id="667d8-308">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="667d8-309">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="667d8-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="667d8-310">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="667d8-311">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="667d8-312">**mstest, xunit**</span></span>

<span data-ttu-id="667d8-313">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="667d8-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="667d8-314">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="667d8-315">**globaljson**</span></span>

<span data-ttu-id="667d8-316">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="667d8-317">**web**</span><span class="sxs-lookup"><span data-stu-id="667d8-317">**web**</span></span>

<span data-ttu-id="667d8-318">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="667d8-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="667d8-319">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-320">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="667d8-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="667d8-321">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="667d8-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="667d8-322">**webapi**</span></span>

<span data-ttu-id="667d8-323">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="667d8-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="667d8-324">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="667d8-324">The possible values are:</span></span>

- <span data-ttu-id="667d8-325">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="667d8-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="667d8-326">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="667d8-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="667d8-327">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="667d8-328">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="667d8-329">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="667d8-330">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-331">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="667d8-332">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="667d8-333">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-334">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="667d8-335">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-336">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="667d8-337">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="667d8-338">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-339">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="667d8-340">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="667d8-341">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-342">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="667d8-343">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="667d8-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="667d8-344">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-345">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="667d8-346">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="667d8-347">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="667d8-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="667d8-348">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="667d8-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="667d8-349">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="667d8-350">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="667d8-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-351">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-352">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="667d8-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="667d8-353">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="667d8-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="667d8-354">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="667d8-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="667d8-355">**mvc, razor**</span></span>

<span data-ttu-id="667d8-356">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="667d8-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="667d8-357">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="667d8-357">The possible values are:</span></span>

- <span data-ttu-id="667d8-358">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="667d8-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="667d8-359">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="667d8-360">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="667d8-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="667d8-361">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="667d8-362">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="667d8-363">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="667d8-364">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="667d8-365">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-366">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="667d8-367">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="667d8-368">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-369">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="667d8-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="667d8-370">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="667d8-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-371">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="667d8-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="667d8-372">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-373">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="667d8-374">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="667d8-375">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="667d8-376">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="667d8-377">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="667d8-378">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="667d8-379">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="667d8-380">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-381">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="667d8-382">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="667d8-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="667d8-383">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-384">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="667d8-385">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="667d8-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="667d8-386">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-387">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="667d8-388">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="667d8-389">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="667d8-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="667d8-390">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="667d8-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="667d8-391">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="667d8-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="667d8-392">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="667d8-393">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="667d8-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-394">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-395">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="667d8-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="667d8-396">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="667d8-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="667d8-397">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="667d8-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="667d8-398">**page**</span><span class="sxs-lookup"><span data-stu-id="667d8-398">**page**</span></span>

<span data-ttu-id="667d8-399">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="667d8-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="667d8-400">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="667d8-401">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="667d8-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="667d8-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="667d8-402">**viewimports**</span></span>

<span data-ttu-id="667d8-403">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="667d8-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="667d8-404">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="667d8-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="667d8-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="667d8-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="667d8-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="667d8-407">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="667d8-408">**classlib**</span></span>

<span data-ttu-id="667d8-409">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="667d8-410">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="667d8-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="667d8-411">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="667d8-412">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="667d8-413">**mstest, xunit**</span></span>

<span data-ttu-id="667d8-414">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="667d8-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="667d8-415">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="667d8-416">**globaljson**</span></span>

<span data-ttu-id="667d8-417">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="667d8-418">**web**</span><span class="sxs-lookup"><span data-stu-id="667d8-418">**web**</span></span>

<span data-ttu-id="667d8-419">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="667d8-420">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="667d8-421">**webapi**</span></span>

<span data-ttu-id="667d8-422">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="667d8-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="667d8-423">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="667d8-423">The possible values are:</span></span>

- <span data-ttu-id="667d8-424">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="667d8-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="667d8-425">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="667d8-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="667d8-426">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="667d8-427">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="667d8-428">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="667d8-429">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-430">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="667d8-431">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="667d8-432">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-433">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="667d8-434">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-435">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="667d8-436">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="667d8-437">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-438">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="667d8-439">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="667d8-440">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-441">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="667d8-442">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="667d8-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="667d8-443">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-444">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="667d8-445">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="667d8-446">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="667d8-447">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="667d8-448">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="667d8-449">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="667d8-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-450">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="667d8-451">**mvc, razor**</span></span>

<span data-ttu-id="667d8-452">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="667d8-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="667d8-453">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="667d8-453">The possible values are:</span></span>

- <span data-ttu-id="667d8-454">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="667d8-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="667d8-455">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="667d8-456">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="667d8-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="667d8-457">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="667d8-458">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="667d8-459">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="667d8-460">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="667d8-461">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-462">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="667d8-463">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="667d8-464">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-465">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="667d8-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="667d8-466">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="667d8-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-467">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="667d8-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="667d8-468">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-469">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="667d8-470">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="667d8-471">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="667d8-472">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="667d8-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="667d8-473">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="667d8-474">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="667d8-475">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="667d8-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="667d8-476">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-477">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="667d8-478">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="667d8-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="667d8-479">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="667d8-480">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="667d8-481">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="667d8-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="667d8-482">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="667d8-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="667d8-483">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="667d8-484">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="667d8-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="667d8-485">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="667d8-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="667d8-486">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="667d8-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="667d8-487">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="667d8-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="667d8-488">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="667d8-489">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="667d8-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="667d8-490">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="667d8-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="667d8-491">**page**</span><span class="sxs-lookup"><span data-stu-id="667d8-491">**page**</span></span>

<span data-ttu-id="667d8-492">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="667d8-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="667d8-493">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="667d8-494">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="667d8-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="667d8-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="667d8-495">**viewimports**</span></span>

<span data-ttu-id="667d8-496">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="667d8-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="667d8-497">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="667d8-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="667d8-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="667d8-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="667d8-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="667d8-500">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="667d8-501">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="667d8-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="667d8-502">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="667d8-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="667d8-503">**classlib**</span></span>

<span data-ttu-id="667d8-504">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="667d8-505">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="667d8-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="667d8-506">Der Standardwert ist `netstandard1.4`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="667d8-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="667d8-507">**mvc**</span></span>

<span data-ttu-id="667d8-508">`-f|--framework`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="667d8-509">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="667d8-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="667d8-510">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="667d8-511">`-au|--auth`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="667d8-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="667d8-512">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="667d8-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="667d8-513">Der Standardwert ist `None`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-513">The default value is `None`.</span></span>

<span data-ttu-id="667d8-514">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="667d8-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="667d8-515">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="667d8-515">Values: `true` or `false`.</span></span> <span data-ttu-id="667d8-516">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="667d8-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="667d8-517">Beispiele</span><span class="sxs-lookup"><span data-stu-id="667d8-517">Examples</span></span>

<span data-ttu-id="667d8-518">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="667d8-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="667d8-519">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="667d8-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="667d8-520">Erstellen Sie ein neues ASP.NET Core C# MVC-Anwendungsprojekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="667d8-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="667d8-521">Erstellen Sie eine neue xUnit-Anwendung:</span><span class="sxs-lookup"><span data-stu-id="667d8-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="667d8-522">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="667d8-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="667d8-523">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="667d8-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="667d8-524">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="667d8-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="667d8-525">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="667d8-525">See also</span></span>

- [<span data-ttu-id="667d8-526">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="667d8-526">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="667d8-527">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="667d8-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="667d8-528">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="667d8-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="667d8-529">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="667d8-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
