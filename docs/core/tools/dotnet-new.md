---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 05/06/2019
ms.openlocfilehash: c9e960bab0e28e88b0cc8d431dad3b9f3f00c9c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660541"
---
# <a name="dotnet-new"></a><span data-ttu-id="5c6d8-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="5c6d8-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5c6d8-104">name</span><span class="sxs-lookup"><span data-stu-id="5c6d8-104">Name</span></span>

<span data-ttu-id="5c6d8-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5c6d8-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5c6d8-106">Synopsis</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="5c6d8-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5c6d8-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5c6d8-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5c6d8-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5c6d8-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5c6d8-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5c6d8-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5c6d8-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="5c6d8-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5c6d8-111">Description</span></span>

<span data-ttu-id="5c6d8-112">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="5c6d8-113">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="5c6d8-114">Argumente</span><span class="sxs-lookup"><span data-stu-id="5c6d8-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="5c6d8-115">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="5c6d8-116">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="5c6d8-117">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="5c6d8-118">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** übereinstimmt, wird für diese beiden Spalten ein Abgleich der Teilzeichenfolge durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="5c6d8-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5c6d8-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="5c6d8-120">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-120">The command contains a default list of templates.</span></span> <span data-ttu-id="5c6d8-121">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="5c6d8-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 2.2.100 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="5c6d8-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="5c6d8-124">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-124">Templates</span></span>                                    | <span data-ttu-id="5c6d8-125">Kurzname</span><span class="sxs-lookup"><span data-stu-id="5c6d8-125">Short Name</span></span>        | <span data-ttu-id="5c6d8-126">Sprache</span><span class="sxs-lookup"><span data-stu-id="5c6d8-126">Language</span></span>     | <span data-ttu-id="5c6d8-127">Tags</span><span class="sxs-lookup"><span data-stu-id="5c6d8-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="5c6d8-128">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="5c6d8-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-129">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-130">Common/Console</span><span class="sxs-lookup"><span data-stu-id="5c6d8-130">Common/Console</span></span>                        |
| <span data-ttu-id="5c6d8-131">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5c6d8-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="5c6d8-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-132">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-133">Common/Library</span><span class="sxs-lookup"><span data-stu-id="5c6d8-133">Common/Library</span></span>                        |
| <span data-ttu-id="5c6d8-134">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="5c6d8-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-135">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="5c6d8-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="5c6d8-137">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="5c6d8-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-138">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="5c6d8-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="5c6d8-140">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="5c6d8-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="5c6d8-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-141">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="5c6d8-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="5c6d8-143">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="5c6d8-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-144">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="5c6d8-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="5c6d8-146">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="5c6d8-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="5c6d8-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-147">[C#]</span></span>         | <span data-ttu-id="5c6d8-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="5c6d8-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5c6d8-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="5c6d8-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-150">[C#]</span></span>         | <span data-ttu-id="5c6d8-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="5c6d8-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5c6d8-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="5c6d8-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-153">[C#]</span></span>         | <span data-ttu-id="5c6d8-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="5c6d8-155">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="5c6d8-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="5c6d8-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-156">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="5c6d8-157">Web/Empty</span></span>                             |
| <span data-ttu-id="5c6d8-158">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="5c6d8-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-159">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="5c6d8-160">Web/MVC</span></span>                               |
| <span data-ttu-id="5c6d8-161">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="5c6d8-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="5c6d8-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="5c6d8-162">`webapp`, `razor`</span></span> | <span data-ttu-id="5c6d8-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-163">[C#]</span></span>         | <span data-ttu-id="5c6d8-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="5c6d8-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="5c6d8-165">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="5c6d8-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="5c6d8-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-166">[C#]</span></span>         | <span data-ttu-id="5c6d8-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="5c6d8-168">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="5c6d8-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="5c6d8-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-169">[C#]</span></span>         | <span data-ttu-id="5c6d8-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="5c6d8-171">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="5c6d8-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="5c6d8-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-172">[C#]</span></span>         | <span data-ttu-id="5c6d8-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="5c6d8-174">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5c6d8-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="5c6d8-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-175">[C#]</span></span>         | <span data-ttu-id="5c6d8-176">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="5c6d8-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="5c6d8-177">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="5c6d8-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="5c6d8-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-178">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="5c6d8-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="5c6d8-180">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="5c6d8-181">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-181">Config</span></span>                                |
| <span data-ttu-id="5c6d8-182">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="5c6d8-183">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-183">Config</span></span>                                |
| <span data-ttu-id="5c6d8-184">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="5c6d8-185">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-185">Config</span></span>                                |
| <span data-ttu-id="5c6d8-186">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="5c6d8-187">Lösung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5c6d8-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5c6d8-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="5c6d8-189">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-189">The command contains a default list of templates.</span></span> <span data-ttu-id="5c6d8-190">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="5c6d8-191">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="5c6d8-192">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="5c6d8-193">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-193">Templates</span></span>                                    | <span data-ttu-id="5c6d8-194">Kurzname</span><span class="sxs-lookup"><span data-stu-id="5c6d8-194">Short Name</span></span>      | <span data-ttu-id="5c6d8-195">Sprache</span><span class="sxs-lookup"><span data-stu-id="5c6d8-195">Language</span></span>     | <span data-ttu-id="5c6d8-196">Tags</span><span class="sxs-lookup"><span data-stu-id="5c6d8-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="5c6d8-197">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="5c6d8-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-198">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-199">Common/Console</span><span class="sxs-lookup"><span data-stu-id="5c6d8-199">Common/Console</span></span>                        |
| <span data-ttu-id="5c6d8-200">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5c6d8-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="5c6d8-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-201">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-202">Common/Library</span><span class="sxs-lookup"><span data-stu-id="5c6d8-202">Common/Library</span></span>                        |
| <span data-ttu-id="5c6d8-203">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="5c6d8-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-204">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="5c6d8-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="5c6d8-206">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="5c6d8-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-207">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="5c6d8-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="5c6d8-209">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="5c6d8-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="5c6d8-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-210">[C#]</span></span>         | <span data-ttu-id="5c6d8-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="5c6d8-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5c6d8-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="5c6d8-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-213">[C#]</span></span>         | <span data-ttu-id="5c6d8-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="5c6d8-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5c6d8-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="5c6d8-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-216">[C#]</span></span>         | <span data-ttu-id="5c6d8-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="5c6d8-218">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="5c6d8-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="5c6d8-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-219">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="5c6d8-220">Web/Empty</span></span>                             |
| <span data-ttu-id="5c6d8-221">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="5c6d8-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-222">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="5c6d8-223">Web/MVC</span></span>                               |
| <span data-ttu-id="5c6d8-224">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="5c6d8-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="5c6d8-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-225">[C#]</span></span>         | <span data-ttu-id="5c6d8-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="5c6d8-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="5c6d8-227">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="5c6d8-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="5c6d8-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-228">[C#]</span></span>         | <span data-ttu-id="5c6d8-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="5c6d8-230">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="5c6d8-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="5c6d8-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-231">[C#]</span></span>         | <span data-ttu-id="5c6d8-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="5c6d8-233">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="5c6d8-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="5c6d8-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-234">[C#]</span></span>         | <span data-ttu-id="5c6d8-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="5c6d8-236">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5c6d8-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="5c6d8-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-237">[C#]</span></span>         | <span data-ttu-id="5c6d8-238">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="5c6d8-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="5c6d8-239">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="5c6d8-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="5c6d8-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-240">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="5c6d8-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="5c6d8-242">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="5c6d8-243">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-243">Config</span></span>                                |
| <span data-ttu-id="5c6d8-244">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="5c6d8-245">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-245">Config</span></span>                                |
| <span data-ttu-id="5c6d8-246">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="5c6d8-247">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-247">Config</span></span>                                |
| <span data-ttu-id="5c6d8-248">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="5c6d8-249">Lösung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5c6d8-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5c6d8-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="5c6d8-251">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-251">The command contains a default list of templates.</span></span> <span data-ttu-id="5c6d8-252">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="5c6d8-253">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 2.0.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="5c6d8-254">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="5c6d8-255">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-255">Templates</span></span>                                    | <span data-ttu-id="5c6d8-256">Kurzname</span><span class="sxs-lookup"><span data-stu-id="5c6d8-256">Short Name</span></span>    | <span data-ttu-id="5c6d8-257">Sprache</span><span class="sxs-lookup"><span data-stu-id="5c6d8-257">Language</span></span>     | <span data-ttu-id="5c6d8-258">Tags</span><span class="sxs-lookup"><span data-stu-id="5c6d8-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="5c6d8-259">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="5c6d8-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-260">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-261">Common/Console</span><span class="sxs-lookup"><span data-stu-id="5c6d8-261">Common/Console</span></span>      |
| <span data-ttu-id="5c6d8-262">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5c6d8-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="5c6d8-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-263">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-264">Common/Library</span><span class="sxs-lookup"><span data-stu-id="5c6d8-264">Common/Library</span></span>      |
| <span data-ttu-id="5c6d8-265">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="5c6d8-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-266">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="5c6d8-267">Test/MSTest</span></span>         |
| <span data-ttu-id="5c6d8-268">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="5c6d8-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5c6d8-269">[C#], F#, VB</span></span> | <span data-ttu-id="5c6d8-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="5c6d8-270">Test/xUnit</span></span>          |
| <span data-ttu-id="5c6d8-271">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="5c6d8-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="5c6d8-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-272">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="5c6d8-273">Web/Empty</span></span>           |
| <span data-ttu-id="5c6d8-274">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="5c6d8-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-275">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="5c6d8-276">Web/MVC</span></span>             |
| <span data-ttu-id="5c6d8-277">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="5c6d8-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="5c6d8-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-278">[C#]</span></span>         | <span data-ttu-id="5c6d8-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="5c6d8-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="5c6d8-280">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="5c6d8-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="5c6d8-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-281">[C#]</span></span>         | <span data-ttu-id="5c6d8-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="5c6d8-283">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="5c6d8-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="5c6d8-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-284">[C#]</span></span>         | <span data-ttu-id="5c6d8-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="5c6d8-286">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="5c6d8-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="5c6d8-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-287">[C#]</span></span>         | <span data-ttu-id="5c6d8-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5c6d8-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="5c6d8-289">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="5c6d8-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="5c6d8-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-290">[C#], F#</span></span>     | <span data-ttu-id="5c6d8-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="5c6d8-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="5c6d8-292">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="5c6d8-293">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-293">Config</span></span>              |
| <span data-ttu-id="5c6d8-294">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="5c6d8-295">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-295">Config</span></span>              |
| <span data-ttu-id="5c6d8-296">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="5c6d8-297">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-297">Config</span></span>              |
| <span data-ttu-id="5c6d8-298">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="5c6d8-299">Lösung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-299">Solution</span></span>            |
| <span data-ttu-id="5c6d8-300">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="5c6d8-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="5c6d8-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="5c6d8-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5c6d8-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="5c6d8-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="5c6d8-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5c6d8-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="5c6d8-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5c6d8-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5c6d8-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5c6d8-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5c6d8-307">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-307">The command contains a default list of templates.</span></span> <span data-ttu-id="5c6d8-308">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="5c6d8-309">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 1.0.1 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="5c6d8-310">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="5c6d8-311">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-311">Templates</span></span>            | <span data-ttu-id="5c6d8-312">Kurzname</span><span class="sxs-lookup"><span data-stu-id="5c6d8-312">Short Name</span></span>    | <span data-ttu-id="5c6d8-313">Sprache</span><span class="sxs-lookup"><span data-stu-id="5c6d8-313">Language</span></span> | <span data-ttu-id="5c6d8-314">Tags</span><span class="sxs-lookup"><span data-stu-id="5c6d8-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="5c6d8-315">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-315">Console Application</span></span>  | `console`     | <span data-ttu-id="5c6d8-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-316">[C#], F#</span></span> | <span data-ttu-id="5c6d8-317">Common/Console</span><span class="sxs-lookup"><span data-stu-id="5c6d8-317">Common/Console</span></span> |
| <span data-ttu-id="5c6d8-318">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5c6d8-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="5c6d8-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-319">[C#], F#</span></span> | <span data-ttu-id="5c6d8-320">Common/Library</span><span class="sxs-lookup"><span data-stu-id="5c6d8-320">Common/Library</span></span> |
| <span data-ttu-id="5c6d8-321">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="5c6d8-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-322">[C#], F#</span></span> | <span data-ttu-id="5c6d8-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="5c6d8-323">Test/MSTest</span></span>    |
| <span data-ttu-id="5c6d8-324">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="5c6d8-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-325">[C#], F#</span></span> | <span data-ttu-id="5c6d8-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="5c6d8-326">Test/xUnit</span></span>     |
| <span data-ttu-id="5c6d8-327">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="5c6d8-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="5c6d8-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-328">[C#]</span></span>     | <span data-ttu-id="5c6d8-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="5c6d8-329">Web/Empty</span></span>      |
| <span data-ttu-id="5c6d8-330">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="5c6d8-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="5c6d8-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5c6d8-331">[C#], F#</span></span> | <span data-ttu-id="5c6d8-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="5c6d8-332">Web/MVC</span></span>        |
| <span data-ttu-id="5c6d8-333">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="5c6d8-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="5c6d8-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="5c6d8-334">[C#]</span></span>     | <span data-ttu-id="5c6d8-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="5c6d8-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="5c6d8-336">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="5c6d8-337">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-337">Config</span></span>         |
| <span data-ttu-id="5c6d8-338">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="5c6d8-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="5c6d8-339">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-339">Config</span></span>         |
| <span data-ttu-id="5c6d8-340">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="5c6d8-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="5c6d8-341">Lösung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="5c6d8-342">Optionen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="5c6d8-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5c6d8-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="5c6d8-344">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="5c6d8-345">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5c6d8-346">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5c6d8-347">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-347">Prints out help for the command.</span></span> <span data-ttu-id="5c6d8-348">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="5c6d8-349">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5c6d8-350">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5c6d8-351">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="5c6d8-352">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="5c6d8-353">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="5c6d8-354">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="5c6d8-355">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5c6d8-356">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="5c6d8-357">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-357">The language of the template to create.</span></span> <span data-ttu-id="5c6d8-358">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5c6d8-359">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-360">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5c6d8-361">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5c6d8-362">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-362">The name for the created output.</span></span> <span data-ttu-id="5c6d8-363">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="5c6d8-364">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5c6d8-365">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-365">Location to place the generated output.</span></span> <span data-ttu-id="5c6d8-366">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="5c6d8-367">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-367">Filters templates based on available types.</span></span> <span data-ttu-id="5c6d8-368">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="5c6d8-369">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5c6d8-370">Wenn der Wert `<PATH|NUGET_ID>` weggelassen wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-371">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5c6d8-372">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="5c6d8-373">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5c6d8-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5c6d8-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="5c6d8-375">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5c6d8-376">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5c6d8-377">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-377">Prints out help for the command.</span></span> <span data-ttu-id="5c6d8-378">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="5c6d8-379">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5c6d8-380">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5c6d8-381">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="5c6d8-382">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="5c6d8-383">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="5c6d8-384">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="5c6d8-385">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5c6d8-386">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="5c6d8-387">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-387">The language of the template to create.</span></span> <span data-ttu-id="5c6d8-388">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5c6d8-389">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-390">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5c6d8-391">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5c6d8-392">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-392">The name for the created output.</span></span> <span data-ttu-id="5c6d8-393">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="5c6d8-394">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5c6d8-395">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-395">Location to place the generated output.</span></span> <span data-ttu-id="5c6d8-396">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="5c6d8-397">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-397">Filters templates based on available types.</span></span> <span data-ttu-id="5c6d8-398">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="5c6d8-399">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-400">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5c6d8-401">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="5c6d8-402">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5c6d8-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5c6d8-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="5c6d8-404">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5c6d8-405">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5c6d8-406">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-406">Prints out help for the command.</span></span> <span data-ttu-id="5c6d8-407">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="5c6d8-408">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5c6d8-409">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5c6d8-410">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="5c6d8-411">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="5c6d8-412">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="5c6d8-413">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="5c6d8-414">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5c6d8-415">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="5c6d8-416">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-416">The language of the template to create.</span></span> <span data-ttu-id="5c6d8-417">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5c6d8-418">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-419">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5c6d8-420">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5c6d8-421">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-421">The name for the created output.</span></span> <span data-ttu-id="5c6d8-422">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5c6d8-423">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-423">Location to place the generated output.</span></span> <span data-ttu-id="5c6d8-424">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="5c6d8-425">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-425">Filters templates based on available types.</span></span> <span data-ttu-id="5c6d8-426">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="5c6d8-427">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-428">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5c6d8-429">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="5c6d8-430">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="5c6d8-431">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5c6d8-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5c6d8-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="5c6d8-433">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="5c6d8-434">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="5c6d8-435">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5c6d8-436">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-436">Prints out help for the command.</span></span> <span data-ttu-id="5c6d8-437">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="5c6d8-438">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="5c6d8-439">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5c6d8-440">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="5c6d8-441">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-441">The language of the template to create.</span></span> <span data-ttu-id="5c6d8-442">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5c6d8-443">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5c6d8-444">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5c6d8-445">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5c6d8-446">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-446">The name for the created output.</span></span> <span data-ttu-id="5c6d8-447">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5c6d8-448">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-448">Location to place the generated output.</span></span> <span data-ttu-id="5c6d8-449">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="5c6d8-450">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="5c6d8-450">Template options</span></span>

<span data-ttu-id="5c6d8-451">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-451">Each project template may have additional options available.</span></span> <span data-ttu-id="5c6d8-452">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="5c6d8-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5c6d8-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="5c6d8-454">**console**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-454">**console**</span></span>

<span data-ttu-id="5c6d8-455">`--langVersion <VERSION_NUMBER>`: Legt die `LangVersion`-Eigenschaft in der erstellten Projektdatei fest.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5c6d8-456">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="5c6d8-457">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-457">Not supported for F#.</span></span>

<span data-ttu-id="5c6d8-458">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="5c6d8-460">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-461">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-462">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-463">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="5c6d8-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-464">**razorclasslib**</span></span>

<span data-ttu-id="5c6d8-465">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-466">**classlib**</span></span>

<span data-ttu-id="5c6d8-467">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-468">Werte: `netcoreapp2.2`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5c6d8-469">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="5c6d8-470">`--langVersion <VERSION_NUMBER>`: Legt die `LangVersion`-Eigenschaft in der erstellten Projektdatei fest.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5c6d8-471">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="5c6d8-472">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-472">Not supported for F#.</span></span>

<span data-ttu-id="5c6d8-473">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-474">**mstest, xunit**</span></span>

<span data-ttu-id="5c6d8-475">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="5c6d8-476">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-477">**nunit**</span></span>

<span data-ttu-id="5c6d8-478">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-479">Der Standardwert ist `netcoreapp2.1`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="5c6d8-480">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="5c6d8-481">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-482">**page**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-482">**page**</span></span>

<span data-ttu-id="5c6d8-483">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="5c6d8-484">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="5c6d8-485">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="5c6d8-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="5c6d8-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-486">**viewimports**</span></span>

<span data-ttu-id="5c6d8-487">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="5c6d8-488">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="5c6d8-489">**web**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-489">**web**</span></span>

<span data-ttu-id="5c6d8-490">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-491">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-492">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-493">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="5c6d8-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-494">**mvc, webapp**</span></span>

<span data-ttu-id="5c6d8-495">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-496">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-496">The possible values are:</span></span>

- <span data-ttu-id="5c6d8-497">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5c6d8-498">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="5c6d8-499">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5c6d8-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5c6d8-500">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5c6d8-501">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="5c6d8-502">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5c6d8-503">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5c6d8-504">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-505">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5c6d8-506">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5c6d8-507">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-508">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="5c6d8-509">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-510">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="5c6d8-511">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-512">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5c6d8-513">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5c6d8-514">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5c6d8-515">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5c6d8-516">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5c6d8-517">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5c6d8-518">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5c6d8-519">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-520">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5c6d8-521">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="5c6d8-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5c6d8-522">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-523">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5c6d8-524">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5c6d8-525">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-526">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="5c6d8-527">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5c6d8-528">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5c6d8-529">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-530">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-531">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5c6d8-532">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="5c6d8-533">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5c6d8-534">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-535">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-536">**webapi**</span></span>

<span data-ttu-id="5c6d8-537">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-538">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-538">The possible values are:</span></span>

- <span data-ttu-id="5c6d8-539">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5c6d8-540">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5c6d8-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5c6d8-541">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5c6d8-542">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5c6d8-543">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5c6d8-544">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-545">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5c6d8-546">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5c6d8-547">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-548">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5c6d8-549">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-550">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5c6d8-551">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5c6d8-552">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-553">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5c6d8-554">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5c6d8-555">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-556">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5c6d8-557">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="5c6d8-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5c6d8-558">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-559">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5c6d8-560">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5c6d8-561">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5c6d8-562">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-563">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-564">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5c6d8-565">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="5c6d8-566">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5c6d8-567">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-568">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-569">**globaljson**</span></span>

<span data-ttu-id="5c6d8-570">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5c6d8-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5c6d8-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="5c6d8-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="5c6d8-573">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-574">**classlib**</span></span>

<span data-ttu-id="5c6d8-575">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-576">Werte: `netcoreapp2.1`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5c6d8-577">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="5c6d8-578">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-579">**mstest, xunit**</span></span>

<span data-ttu-id="5c6d8-580">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="5c6d8-581">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-582">**globaljson**</span></span>

<span data-ttu-id="5c6d8-583">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="5c6d8-584">**web**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-584">**web**</span></span>

<span data-ttu-id="5c6d8-585">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-586">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-587">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-588">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="5c6d8-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-589">**webapi**</span></span>

<span data-ttu-id="5c6d8-590">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-591">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-591">The possible values are:</span></span>

- <span data-ttu-id="5c6d8-592">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5c6d8-593">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5c6d8-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5c6d8-594">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5c6d8-595">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5c6d8-596">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5c6d8-597">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-598">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5c6d8-599">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5c6d8-600">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-601">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5c6d8-602">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-603">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5c6d8-604">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5c6d8-605">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-606">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5c6d8-607">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5c6d8-608">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-609">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5c6d8-610">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="5c6d8-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5c6d8-611">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-612">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5c6d8-613">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5c6d8-614">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5c6d8-615">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-616">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5c6d8-617">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-618">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-619">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-620">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5c6d8-621">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="5c6d8-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-622">**mvc, razor**</span></span>

<span data-ttu-id="5c6d8-623">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-624">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-624">The possible values are:</span></span>

- <span data-ttu-id="5c6d8-625">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5c6d8-626">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="5c6d8-627">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5c6d8-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5c6d8-628">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5c6d8-629">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="5c6d8-630">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5c6d8-631">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5c6d8-632">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-633">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5c6d8-634">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5c6d8-635">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-636">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="5c6d8-637">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-638">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="5c6d8-639">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-640">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5c6d8-641">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5c6d8-642">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5c6d8-643">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5c6d8-644">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5c6d8-645">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5c6d8-646">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5c6d8-647">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-648">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5c6d8-649">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="5c6d8-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5c6d8-650">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-651">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5c6d8-652">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5c6d8-653">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-654">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="5c6d8-655">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5c6d8-656">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5c6d8-657">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5c6d8-658">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="5c6d8-659">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5c6d8-660">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-661">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-662">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5c6d8-663">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5c6d8-664">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="5c6d8-665">**page**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-665">**page**</span></span>

<span data-ttu-id="5c6d8-666">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="5c6d8-667">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="5c6d8-668">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="5c6d8-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="5c6d8-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-669">**viewimports**</span></span>

<span data-ttu-id="5c6d8-670">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="5c6d8-671">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5c6d8-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5c6d8-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="5c6d8-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="5c6d8-674">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-675">**classlib**</span></span>

<span data-ttu-id="5c6d8-676">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-677">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5c6d8-678">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="5c6d8-679">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-680">**mstest, xunit**</span></span>

<span data-ttu-id="5c6d8-681">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5c6d8-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="5c6d8-682">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-683">**globaljson**</span></span>

<span data-ttu-id="5c6d8-684">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="5c6d8-685">**web**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-685">**web**</span></span>

<span data-ttu-id="5c6d8-686">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="5c6d8-687">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-688">**webapi**</span></span>

<span data-ttu-id="5c6d8-689">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-690">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-690">The possible values are:</span></span>

- <span data-ttu-id="5c6d8-691">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5c6d8-692">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5c6d8-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5c6d8-693">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5c6d8-694">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5c6d8-695">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5c6d8-696">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-697">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5c6d8-698">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5c6d8-699">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-700">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5c6d8-701">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-702">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5c6d8-703">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5c6d8-704">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-705">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5c6d8-706">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5c6d8-707">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-708">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5c6d8-709">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="5c6d8-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5c6d8-710">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-711">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5c6d8-712">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5c6d8-713">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5c6d8-714">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="5c6d8-715">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5c6d8-716">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-717">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-718">**mvc, razor**</span></span>

<span data-ttu-id="5c6d8-719">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-720">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-720">The possible values are:</span></span>

- <span data-ttu-id="5c6d8-721">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5c6d8-722">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="5c6d8-723">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5c6d8-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5c6d8-724">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5c6d8-725">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="5c6d8-726">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5c6d8-727">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5c6d8-728">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-729">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5c6d8-730">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5c6d8-731">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-732">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="5c6d8-733">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-734">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="5c6d8-735">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-736">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5c6d8-737">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5c6d8-738">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5c6d8-739">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5c6d8-740">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5c6d8-741">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5c6d8-742">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5c6d8-743">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-744">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5c6d8-745">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="5c6d8-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5c6d8-746">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5c6d8-747">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5c6d8-748">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5c6d8-749">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5c6d8-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5c6d8-750">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="5c6d8-751">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5c6d8-752">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5c6d8-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5c6d8-753">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="5c6d8-754">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="5c6d8-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="5c6d8-755">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5c6d8-756">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5c6d8-757">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5c6d8-758">**page**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-758">**page**</span></span>

<span data-ttu-id="5c6d8-759">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="5c6d8-760">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="5c6d8-761">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="5c6d8-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="5c6d8-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-762">**viewimports**</span></span>

<span data-ttu-id="5c6d8-763">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="5c6d8-764">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5c6d8-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5c6d8-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5c6d8-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="5c6d8-767">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-768">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="5c6d8-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="5c6d8-769">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="5c6d8-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-770">**classlib**</span></span>

<span data-ttu-id="5c6d8-771">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-772">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="5c6d8-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="5c6d8-773">Der Standardwert ist `netstandard1.4`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="5c6d8-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="5c6d8-774">**mvc**</span></span>

<span data-ttu-id="5c6d8-775">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5c6d8-776">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="5c6d8-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="5c6d8-777">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="5c6d8-778">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5c6d8-779">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="5c6d8-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="5c6d8-780">Der Standardwert ist `None`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-780">The default value is `None`.</span></span>

<span data-ttu-id="5c6d8-781">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="5c6d8-782">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="5c6d8-782">Values: `true` or `false`.</span></span> <span data-ttu-id="5c6d8-783">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="5c6d8-784">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5c6d8-784">Examples</span></span>

<span data-ttu-id="5c6d8-785">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="5c6d8-786">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="5c6d8-787">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="5c6d8-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="5c6d8-788">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="5c6d8-789">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="5c6d8-790">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="5c6d8-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="5c6d8-791">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="5c6d8-792">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="5c6d8-793">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="5c6d8-794">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5c6d8-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="5c6d8-795">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="5c6d8-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="5c6d8-796">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="5c6d8-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="5c6d8-797">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c6d8-797">See also</span></span>

- [<span data-ttu-id="5c6d8-798">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="5c6d8-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="5c6d8-799">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="5c6d8-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="5c6d8-800">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="5c6d8-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="5c6d8-801">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="5c6d8-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
