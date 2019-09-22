---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 05/06/2019
ms.openlocfilehash: b61b5fd53f470c30b636026fa19ebfad834d6354
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117660"
---
# <a name="dotnet-new"></a><span data-ttu-id="72bec-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="72bec-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="72bec-104">NAME</span><span class="sxs-lookup"><span data-stu-id="72bec-104">Name</span></span>

<span data-ttu-id="72bec-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="72bec-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="72bec-106">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="72bec-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72bec-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72bec-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72bec-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72bec-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72bec-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72bec-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72bec-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72bec-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="72bec-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="72bec-111">Description</span></span>

<span data-ttu-id="72bec-112">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="72bec-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="72bec-113">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="72bec-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="72bec-114">Argumente</span><span class="sxs-lookup"><span data-stu-id="72bec-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="72bec-115">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="72bec-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="72bec-116">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="72bec-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="72bec-117">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="72bec-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="72bec-118">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** übereinstimmt, wird für diese beiden Spalten ein Abgleich der Teilzeichenfolge durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="72bec-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72bec-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72bec-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="72bec-120">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="72bec-120">The command contains a default list of templates.</span></span> <span data-ttu-id="72bec-121">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="72bec-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="72bec-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 2.2.100 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="72bec-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72bec-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72bec-124">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="72bec-124">Templates</span></span>                                    | <span data-ttu-id="72bec-125">Kurzname</span><span class="sxs-lookup"><span data-stu-id="72bec-125">Short Name</span></span>        | <span data-ttu-id="72bec-126">Sprache</span><span class="sxs-lookup"><span data-stu-id="72bec-126">Language</span></span>     | <span data-ttu-id="72bec-127">`Tags`</span><span class="sxs-lookup"><span data-stu-id="72bec-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="72bec-128">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="72bec-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="72bec-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-129">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-130">Common/Console</span><span class="sxs-lookup"><span data-stu-id="72bec-130">Common/Console</span></span>                        |
| <span data-ttu-id="72bec-131">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="72bec-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="72bec-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-132">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-133">Common/Library</span><span class="sxs-lookup"><span data-stu-id="72bec-133">Common/Library</span></span>                        |
| <span data-ttu-id="72bec-134">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="72bec-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-135">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72bec-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="72bec-137">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="72bec-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-138">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="72bec-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="72bec-140">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="72bec-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="72bec-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-141">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="72bec-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="72bec-143">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="72bec-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-144">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72bec-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="72bec-146">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="72bec-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="72bec-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-147">[C#]</span></span>         | <span data-ttu-id="72bec-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72bec-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="72bec-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="72bec-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-150">[C#]</span></span>         | <span data-ttu-id="72bec-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72bec-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="72bec-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="72bec-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-153">[C#]</span></span>         | <span data-ttu-id="72bec-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72bec-155">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="72bec-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="72bec-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-156">[C#], F#</span></span>     | <span data-ttu-id="72bec-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="72bec-157">Web/Empty</span></span>                             |
| <span data-ttu-id="72bec-158">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="72bec-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="72bec-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-159">[C#], F#</span></span>     | <span data-ttu-id="72bec-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72bec-160">Web/MVC</span></span>                               |
| <span data-ttu-id="72bec-161">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="72bec-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="72bec-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="72bec-162">`webapp`, `razor`</span></span> | <span data-ttu-id="72bec-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-163">[C#]</span></span>         | <span data-ttu-id="72bec-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="72bec-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="72bec-165">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="72bec-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="72bec-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-166">[C#]</span></span>         | <span data-ttu-id="72bec-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72bec-168">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="72bec-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="72bec-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-169">[C#]</span></span>         | <span data-ttu-id="72bec-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72bec-171">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="72bec-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="72bec-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-172">[C#]</span></span>         | <span data-ttu-id="72bec-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72bec-174">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="72bec-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="72bec-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-175">[C#]</span></span>         | <span data-ttu-id="72bec-176">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="72bec-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="72bec-177">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="72bec-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="72bec-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-178">[C#], F#</span></span>     | <span data-ttu-id="72bec-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72bec-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="72bec-180">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="72bec-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="72bec-181">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-181">Config</span></span>                                |
| <span data-ttu-id="72bec-182">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="72bec-183">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-183">Config</span></span>                                |
| <span data-ttu-id="72bec-184">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="72bec-185">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-185">Config</span></span>                                |
| <span data-ttu-id="72bec-186">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="72bec-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="72bec-187">Lösung</span><span class="sxs-lookup"><span data-stu-id="72bec-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72bec-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72bec-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="72bec-189">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="72bec-189">The command contains a default list of templates.</span></span> <span data-ttu-id="72bec-190">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="72bec-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="72bec-191">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="72bec-192">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72bec-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72bec-193">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="72bec-193">Templates</span></span>                                    | <span data-ttu-id="72bec-194">Kurzname</span><span class="sxs-lookup"><span data-stu-id="72bec-194">Short Name</span></span>      | <span data-ttu-id="72bec-195">Sprache</span><span class="sxs-lookup"><span data-stu-id="72bec-195">Language</span></span>     | <span data-ttu-id="72bec-196">`Tags`</span><span class="sxs-lookup"><span data-stu-id="72bec-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="72bec-197">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="72bec-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="72bec-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-198">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-199">Common/Console</span><span class="sxs-lookup"><span data-stu-id="72bec-199">Common/Console</span></span>                        |
| <span data-ttu-id="72bec-200">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="72bec-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="72bec-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-201">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-202">Common/Library</span><span class="sxs-lookup"><span data-stu-id="72bec-202">Common/Library</span></span>                        |
| <span data-ttu-id="72bec-203">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="72bec-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-204">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72bec-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="72bec-206">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="72bec-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-207">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72bec-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="72bec-209">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="72bec-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="72bec-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-210">[C#]</span></span>         | <span data-ttu-id="72bec-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72bec-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="72bec-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="72bec-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-213">[C#]</span></span>         | <span data-ttu-id="72bec-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72bec-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="72bec-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="72bec-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-216">[C#]</span></span>         | <span data-ttu-id="72bec-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72bec-218">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="72bec-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="72bec-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-219">[C#], F#</span></span>     | <span data-ttu-id="72bec-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="72bec-220">Web/Empty</span></span>                             |
| <span data-ttu-id="72bec-221">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="72bec-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="72bec-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-222">[C#], F#</span></span>     | <span data-ttu-id="72bec-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72bec-223">Web/MVC</span></span>                               |
| <span data-ttu-id="72bec-224">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="72bec-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="72bec-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-225">[C#]</span></span>         | <span data-ttu-id="72bec-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="72bec-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="72bec-227">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="72bec-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="72bec-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-228">[C#]</span></span>         | <span data-ttu-id="72bec-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72bec-230">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="72bec-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="72bec-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-231">[C#]</span></span>         | <span data-ttu-id="72bec-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72bec-233">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="72bec-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="72bec-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-234">[C#]</span></span>         | <span data-ttu-id="72bec-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="72bec-236">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="72bec-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="72bec-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-237">[C#]</span></span>         | <span data-ttu-id="72bec-238">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="72bec-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="72bec-239">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="72bec-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="72bec-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-240">[C#], F#</span></span>     | <span data-ttu-id="72bec-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72bec-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="72bec-242">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="72bec-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="72bec-243">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-243">Config</span></span>                                |
| <span data-ttu-id="72bec-244">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="72bec-245">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-245">Config</span></span>                                |
| <span data-ttu-id="72bec-246">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="72bec-247">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-247">Config</span></span>                                |
| <span data-ttu-id="72bec-248">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="72bec-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="72bec-249">Lösung</span><span class="sxs-lookup"><span data-stu-id="72bec-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72bec-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72bec-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="72bec-251">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="72bec-251">The command contains a default list of templates.</span></span> <span data-ttu-id="72bec-252">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="72bec-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="72bec-253">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 2.0.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="72bec-254">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72bec-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72bec-255">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="72bec-255">Templates</span></span>                                    | <span data-ttu-id="72bec-256">Kurzname</span><span class="sxs-lookup"><span data-stu-id="72bec-256">Short Name</span></span>    | <span data-ttu-id="72bec-257">Sprache</span><span class="sxs-lookup"><span data-stu-id="72bec-257">Language</span></span>     | <span data-ttu-id="72bec-258">`Tags`</span><span class="sxs-lookup"><span data-stu-id="72bec-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="72bec-259">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="72bec-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="72bec-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-260">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-261">Common/Console</span><span class="sxs-lookup"><span data-stu-id="72bec-261">Common/Console</span></span>      |
| <span data-ttu-id="72bec-262">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="72bec-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="72bec-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-263">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-264">Common/Library</span><span class="sxs-lookup"><span data-stu-id="72bec-264">Common/Library</span></span>      |
| <span data-ttu-id="72bec-265">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="72bec-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-266">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72bec-267">Test/MSTest</span></span>         |
| <span data-ttu-id="72bec-268">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="72bec-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72bec-269">[C#], F#, VB</span></span> | <span data-ttu-id="72bec-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72bec-270">Test/xUnit</span></span>          |
| <span data-ttu-id="72bec-271">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="72bec-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="72bec-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-272">[C#], F#</span></span>     | <span data-ttu-id="72bec-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="72bec-273">Web/Empty</span></span>           |
| <span data-ttu-id="72bec-274">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="72bec-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="72bec-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-275">[C#], F#</span></span>     | <span data-ttu-id="72bec-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72bec-276">Web/MVC</span></span>             |
| <span data-ttu-id="72bec-277">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="72bec-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="72bec-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-278">[C#]</span></span>         | <span data-ttu-id="72bec-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="72bec-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="72bec-280">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="72bec-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="72bec-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-281">[C#]</span></span>         | <span data-ttu-id="72bec-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="72bec-283">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="72bec-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="72bec-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-284">[C#]</span></span>         | <span data-ttu-id="72bec-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="72bec-286">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="72bec-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="72bec-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-287">[C#]</span></span>         | <span data-ttu-id="72bec-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72bec-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="72bec-289">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="72bec-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="72bec-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-290">[C#], F#</span></span>     | <span data-ttu-id="72bec-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72bec-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="72bec-292">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="72bec-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="72bec-293">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-293">Config</span></span>              |
| <span data-ttu-id="72bec-294">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="72bec-295">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-295">Config</span></span>              |
| <span data-ttu-id="72bec-296">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="72bec-297">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-297">Config</span></span>              |
| <span data-ttu-id="72bec-298">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="72bec-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="72bec-299">Lösung</span><span class="sxs-lookup"><span data-stu-id="72bec-299">Solution</span></span>            |
| <span data-ttu-id="72bec-300">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="72bec-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="72bec-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="72bec-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="72bec-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="72bec-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="72bec-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="72bec-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="72bec-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72bec-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72bec-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72bec-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="72bec-307">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="72bec-307">The command contains a default list of templates.</span></span> <span data-ttu-id="72bec-308">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="72bec-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="72bec-309">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 1.0.1 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="72bec-310">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72bec-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72bec-311">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="72bec-311">Templates</span></span>            | <span data-ttu-id="72bec-312">Kurzname</span><span class="sxs-lookup"><span data-stu-id="72bec-312">Short Name</span></span>    | <span data-ttu-id="72bec-313">Sprache</span><span class="sxs-lookup"><span data-stu-id="72bec-313">Language</span></span> | <span data-ttu-id="72bec-314">`Tags`</span><span class="sxs-lookup"><span data-stu-id="72bec-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="72bec-315">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="72bec-315">Console Application</span></span>  | `console`     | <span data-ttu-id="72bec-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-316">[C#], F#</span></span> | <span data-ttu-id="72bec-317">Common/Console</span><span class="sxs-lookup"><span data-stu-id="72bec-317">Common/Console</span></span> |
| <span data-ttu-id="72bec-318">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="72bec-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="72bec-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-319">[C#], F#</span></span> | <span data-ttu-id="72bec-320">Common/Library</span><span class="sxs-lookup"><span data-stu-id="72bec-320">Common/Library</span></span> |
| <span data-ttu-id="72bec-321">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="72bec-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-322">[C#], F#</span></span> | <span data-ttu-id="72bec-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72bec-323">Test/MSTest</span></span>    |
| <span data-ttu-id="72bec-324">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="72bec-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="72bec-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-325">[C#], F#</span></span> | <span data-ttu-id="72bec-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72bec-326">Test/xUnit</span></span>     |
| <span data-ttu-id="72bec-327">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="72bec-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="72bec-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-328">[C#]</span></span>     | <span data-ttu-id="72bec-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="72bec-329">Web/Empty</span></span>      |
| <span data-ttu-id="72bec-330">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="72bec-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="72bec-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72bec-331">[C#], F#</span></span> | <span data-ttu-id="72bec-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72bec-332">Web/MVC</span></span>        |
| <span data-ttu-id="72bec-333">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="72bec-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="72bec-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="72bec-334">[C#]</span></span>     | <span data-ttu-id="72bec-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72bec-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="72bec-336">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="72bec-337">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-337">Config</span></span>         |
| <span data-ttu-id="72bec-338">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="72bec-339">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="72bec-339">Config</span></span>         |
| <span data-ttu-id="72bec-340">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="72bec-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="72bec-341">Lösung</span><span class="sxs-lookup"><span data-stu-id="72bec-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="72bec-342">Optionen</span><span class="sxs-lookup"><span data-stu-id="72bec-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72bec-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72bec-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="72bec-344">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="72bec-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="72bec-345">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="72bec-346">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="72bec-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72bec-347">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="72bec-347">Prints out help for the command.</span></span> <span data-ttu-id="72bec-348">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="72bec-349">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="72bec-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72bec-350">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="72bec-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="72bec-351">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="72bec-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="72bec-352">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="72bec-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="72bec-353">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="72bec-354">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="72bec-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="72bec-355">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72bec-356">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="72bec-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="72bec-357">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="72bec-357">The language of the template to create.</span></span> <span data-ttu-id="72bec-358">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="72bec-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72bec-359">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="72bec-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-360">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="72bec-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72bec-361">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72bec-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72bec-362">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-362">The name for the created output.</span></span> <span data-ttu-id="72bec-363">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="72bec-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="72bec-364">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72bec-365">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-365">Location to place the generated output.</span></span> <span data-ttu-id="72bec-366">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="72bec-367">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="72bec-367">Filters templates based on available types.</span></span> <span data-ttu-id="72bec-368">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="72bec-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="72bec-369">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="72bec-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72bec-370">Wenn der Wert `<PATH|NUGET_ID>` weggelassen wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72bec-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-371">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="72bec-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="72bec-372">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="72bec-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="72bec-373">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="72bec-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72bec-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72bec-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="72bec-375">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="72bec-376">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="72bec-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72bec-377">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="72bec-377">Prints out help for the command.</span></span> <span data-ttu-id="72bec-378">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="72bec-379">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="72bec-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72bec-380">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="72bec-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="72bec-381">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="72bec-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="72bec-382">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="72bec-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="72bec-383">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="72bec-384">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="72bec-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="72bec-385">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72bec-386">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="72bec-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="72bec-387">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="72bec-387">The language of the template to create.</span></span> <span data-ttu-id="72bec-388">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="72bec-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72bec-389">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="72bec-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-390">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="72bec-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72bec-391">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72bec-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72bec-392">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-392">The name for the created output.</span></span> <span data-ttu-id="72bec-393">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="72bec-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="72bec-394">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72bec-395">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-395">Location to place the generated output.</span></span> <span data-ttu-id="72bec-396">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="72bec-397">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="72bec-397">Filters templates based on available types.</span></span> <span data-ttu-id="72bec-398">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="72bec-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="72bec-399">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="72bec-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-400">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="72bec-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="72bec-401">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="72bec-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="72bec-402">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="72bec-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72bec-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72bec-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="72bec-404">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="72bec-405">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="72bec-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72bec-406">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="72bec-406">Prints out help for the command.</span></span> <span data-ttu-id="72bec-407">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="72bec-408">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="72bec-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72bec-409">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="72bec-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="72bec-410">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="72bec-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="72bec-411">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="72bec-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="72bec-412">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="72bec-413">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="72bec-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="72bec-414">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72bec-415">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="72bec-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="72bec-416">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="72bec-416">The language of the template to create.</span></span> <span data-ttu-id="72bec-417">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="72bec-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72bec-418">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="72bec-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-419">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="72bec-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72bec-420">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72bec-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72bec-421">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-421">The name for the created output.</span></span> <span data-ttu-id="72bec-422">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="72bec-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72bec-423">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-423">Location to place the generated output.</span></span> <span data-ttu-id="72bec-424">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="72bec-425">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="72bec-425">Filters templates based on available types.</span></span> <span data-ttu-id="72bec-426">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="72bec-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="72bec-427">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="72bec-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-428">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="72bec-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="72bec-429">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="72bec-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="72bec-430">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="72bec-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="72bec-431">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72bec-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72bec-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="72bec-433">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="72bec-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="72bec-434">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="72bec-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="72bec-435">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="72bec-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72bec-436">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="72bec-436">Prints out help for the command.</span></span> <span data-ttu-id="72bec-437">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="72bec-438">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="72bec-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="72bec-439">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="72bec-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72bec-440">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="72bec-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="72bec-441">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="72bec-441">The language of the template to create.</span></span> <span data-ttu-id="72bec-442">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="72bec-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72bec-443">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="72bec-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72bec-444">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="72bec-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72bec-445">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72bec-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72bec-446">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-446">The name for the created output.</span></span> <span data-ttu-id="72bec-447">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="72bec-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72bec-448">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-448">Location to place the generated output.</span></span> <span data-ttu-id="72bec-449">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="72bec-450">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="72bec-450">Template options</span></span>

<span data-ttu-id="72bec-451">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="72bec-451">Each project template may have additional options available.</span></span> <span data-ttu-id="72bec-452">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="72bec-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72bec-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72bec-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="72bec-454">**console**</span><span class="sxs-lookup"><span data-stu-id="72bec-454">**console**</span></span>

<span data-ttu-id="72bec-455">`--langVersion <VERSION_NUMBER>`: Legt die `LangVersion`-Eigenschaft in der erstellten Projektdatei fest.</span><span class="sxs-lookup"><span data-stu-id="72bec-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="72bec-456">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="72bec-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="72bec-457">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72bec-457">Not supported for F#.</span></span>

<span data-ttu-id="72bec-458">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="72bec-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="72bec-460">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-461">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-462">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-463">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="72bec-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="72bec-464">**razorclasslib**</span></span>

<span data-ttu-id="72bec-465">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72bec-466">**classlib**</span></span>

<span data-ttu-id="72bec-467">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-468">Werte: `netcoreapp2.2`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72bec-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="72bec-469">Standardwert: `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="72bec-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="72bec-470">`--langVersion <VERSION_NUMBER>`: Legt die `LangVersion`-Eigenschaft in der erstellten Projektdatei fest.</span><span class="sxs-lookup"><span data-stu-id="72bec-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="72bec-471">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="72bec-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="72bec-472">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="72bec-472">Not supported for F#.</span></span>

<span data-ttu-id="72bec-473">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="72bec-474">**mstest, xunit**</span></span>

<span data-ttu-id="72bec-475">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72bec-476">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="72bec-477">**nunit**</span></span>

<span data-ttu-id="72bec-478">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-479">Standardwert: `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="72bec-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="72bec-480">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72bec-481">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-482">**page**</span><span class="sxs-lookup"><span data-stu-id="72bec-482">**page**</span></span>

<span data-ttu-id="72bec-483">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="72bec-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72bec-484">Standardwert: `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72bec-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72bec-485">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="72bec-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="72bec-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="72bec-486">**viewimports**</span></span>

<span data-ttu-id="72bec-487">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="72bec-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72bec-488">Standardwert: `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72bec-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72bec-489">**web**</span><span class="sxs-lookup"><span data-stu-id="72bec-489">**web**</span></span>

<span data-ttu-id="72bec-490">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-491">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-492">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-493">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="72bec-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="72bec-494">**mvc, webapp**</span></span>

<span data-ttu-id="72bec-495">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-496">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="72bec-496">The possible values are:</span></span>

- <span data-ttu-id="72bec-497">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="72bec-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72bec-498">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="72bec-499">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="72bec-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72bec-500">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72bec-501">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="72bec-502">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72bec-503">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72bec-504">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-505">Standardwert: `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72bec-506">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72bec-507">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-508">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="72bec-509">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="72bec-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-510">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="72bec-511">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-512">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72bec-513">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="72bec-514">Standardwert: `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72bec-515">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72bec-516">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="72bec-517">Standardwert: `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72bec-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72bec-518">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72bec-519">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-520">Standardwert: `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72bec-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72bec-521">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="72bec-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72bec-522">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-523">Standardwert: `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72bec-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72bec-524">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="72bec-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="72bec-525">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-526">Standardwert: `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="72bec-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="72bec-527">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72bec-528">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72bec-529">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-530">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-531">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="72bec-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72bec-532">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72bec-533">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72bec-534">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-535">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="72bec-536">**webapi**</span></span>

<span data-ttu-id="72bec-537">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-538">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="72bec-538">The possible values are:</span></span>

- <span data-ttu-id="72bec-539">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="72bec-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72bec-540">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="72bec-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72bec-541">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72bec-542">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72bec-543">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72bec-544">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-545">Standardwert: `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72bec-546">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72bec-547">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-548">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72bec-549">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-550">Standardwert: `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72bec-551">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72bec-552">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-553">Standardwert: `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72bec-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72bec-554">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72bec-555">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-556">Standardwert: `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72bec-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72bec-557">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="72bec-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72bec-558">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-559">Standardwert: `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72bec-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72bec-560">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72bec-561">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72bec-562">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-563">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-564">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="72bec-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72bec-565">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72bec-566">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72bec-567">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-568">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="72bec-569">**globaljson**</span></span>

<span data-ttu-id="72bec-570">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72bec-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72bec-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="72bec-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="72bec-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="72bec-573">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72bec-574">**classlib**</span></span>

<span data-ttu-id="72bec-575">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-576">Werte: `netcoreapp2.1`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72bec-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="72bec-577">Standardwert: `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="72bec-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="72bec-578">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="72bec-579">**mstest, xunit**</span></span>

<span data-ttu-id="72bec-580">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72bec-581">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="72bec-582">**globaljson**</span></span>

<span data-ttu-id="72bec-583">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="72bec-584">**web**</span><span class="sxs-lookup"><span data-stu-id="72bec-584">**web**</span></span>

<span data-ttu-id="72bec-585">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-586">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-587">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-588">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="72bec-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="72bec-589">**webapi**</span></span>

<span data-ttu-id="72bec-590">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-591">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="72bec-591">The possible values are:</span></span>

- <span data-ttu-id="72bec-592">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="72bec-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72bec-593">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="72bec-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72bec-594">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72bec-595">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72bec-596">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72bec-597">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-598">Standardwert: `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72bec-599">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72bec-600">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-601">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72bec-602">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-603">Standardwert: `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72bec-604">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72bec-605">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-606">Standardwert: `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72bec-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72bec-607">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72bec-608">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-609">Standardwert: `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72bec-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72bec-610">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="72bec-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72bec-611">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-612">Standardwert: `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72bec-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72bec-613">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72bec-614">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72bec-615">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-616">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72bec-617">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-618">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-619">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-620">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="72bec-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72bec-621">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72bec-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="72bec-622">**mvc, razor**</span></span>

<span data-ttu-id="72bec-623">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-624">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="72bec-624">The possible values are:</span></span>

- <span data-ttu-id="72bec-625">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="72bec-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72bec-626">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="72bec-627">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="72bec-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72bec-628">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72bec-629">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="72bec-630">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72bec-631">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72bec-632">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-633">Standardwert: `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72bec-634">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72bec-635">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-636">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="72bec-637">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="72bec-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-638">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="72bec-639">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-640">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72bec-641">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="72bec-642">Standardwert: `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72bec-643">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72bec-644">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="72bec-645">Standardwert: `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72bec-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72bec-646">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72bec-647">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-648">Standardwert: `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72bec-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72bec-649">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="72bec-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72bec-650">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-651">Standardwert: `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72bec-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72bec-652">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="72bec-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="72bec-653">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-654">Standardwert: `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="72bec-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="72bec-655">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72bec-656">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72bec-657">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="72bec-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72bec-658">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="72bec-659">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72bec-660">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-661">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-662">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="72bec-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72bec-663">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="72bec-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72bec-664">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bec-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72bec-665">**page**</span><span class="sxs-lookup"><span data-stu-id="72bec-665">**page**</span></span>

<span data-ttu-id="72bec-666">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="72bec-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72bec-667">Standardwert: `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72bec-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72bec-668">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="72bec-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="72bec-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="72bec-669">**viewimports**</span></span>

<span data-ttu-id="72bec-670">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="72bec-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72bec-671">Standardwert: `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72bec-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72bec-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72bec-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="72bec-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="72bec-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="72bec-674">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72bec-675">**classlib**</span></span>

<span data-ttu-id="72bec-676">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-677">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72bec-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="72bec-678">Standardwert: `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="72bec-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="72bec-679">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="72bec-680">**mstest, xunit**</span></span>

<span data-ttu-id="72bec-681">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72bec-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72bec-682">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="72bec-683">**globaljson**</span></span>

<span data-ttu-id="72bec-684">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="72bec-685">**web**</span><span class="sxs-lookup"><span data-stu-id="72bec-685">**web**</span></span>

<span data-ttu-id="72bec-686">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="72bec-687">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="72bec-688">**webapi**</span></span>

<span data-ttu-id="72bec-689">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-690">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="72bec-690">The possible values are:</span></span>

- <span data-ttu-id="72bec-691">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="72bec-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72bec-692">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="72bec-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72bec-693">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72bec-694">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72bec-695">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72bec-696">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-697">Standardwert: `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72bec-698">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72bec-699">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-700">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72bec-701">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-702">Standardwert: `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72bec-703">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72bec-704">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-705">Standardwert: `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72bec-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72bec-706">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72bec-707">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-708">Standardwert: `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72bec-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72bec-709">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="72bec-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72bec-710">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-711">Standardwert: `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72bec-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72bec-712">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72bec-713">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72bec-714">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="72bec-715">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72bec-716">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-717">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="72bec-718">**mvc, razor**</span></span>

<span data-ttu-id="72bec-719">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-720">Mögliche Werte:</span><span class="sxs-lookup"><span data-stu-id="72bec-720">The possible values are:</span></span>

- <span data-ttu-id="72bec-721">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="72bec-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72bec-722">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="72bec-723">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="72bec-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72bec-724">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72bec-725">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="72bec-726">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72bec-727">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72bec-728">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-729">Standardwert: `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72bec-730">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72bec-731">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-732">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="72bec-733">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="72bec-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-734">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="72bec-735">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-736">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72bec-737">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="72bec-738">Standardwert: `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72bec-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72bec-739">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="72bec-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72bec-740">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="72bec-741">Standardwert: `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72bec-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72bec-742">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="72bec-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72bec-743">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-744">Standardwert: `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72bec-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72bec-745">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="72bec-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72bec-746">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72bec-747">Standardwert: `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72bec-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72bec-748">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="72bec-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="72bec-749">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="72bec-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72bec-750">Standardwert: `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="72bec-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="72bec-751">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72bec-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72bec-752">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="72bec-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72bec-753">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="72bec-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="72bec-754">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="72bec-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="72bec-755">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72bec-756">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="72bec-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72bec-757">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="72bec-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72bec-758">**page**</span><span class="sxs-lookup"><span data-stu-id="72bec-758">**page**</span></span>

<span data-ttu-id="72bec-759">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="72bec-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="72bec-760">Standardwert: `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72bec-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72bec-761">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="72bec-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="72bec-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="72bec-762">**viewimports**</span></span>

<span data-ttu-id="72bec-763">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="72bec-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="72bec-764">Standardwert: `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72bec-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72bec-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72bec-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="72bec-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="72bec-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="72bec-767">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-768">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="72bec-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="72bec-769">Standardwert: `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="72bec-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="72bec-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72bec-770">**classlib**</span></span>

<span data-ttu-id="72bec-771">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-772">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="72bec-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="72bec-773">Standardwert: `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="72bec-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="72bec-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="72bec-774">**mvc**</span></span>

<span data-ttu-id="72bec-775">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72bec-776">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="72bec-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="72bec-777">Standardwert: `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="72bec-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="72bec-778">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="72bec-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72bec-779">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="72bec-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="72bec-780">Standardwert: `None`.</span><span class="sxs-lookup"><span data-stu-id="72bec-780">The default value is `None`.</span></span>

<span data-ttu-id="72bec-781">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="72bec-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="72bec-782">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="72bec-782">Values: `true` or `false`.</span></span> <span data-ttu-id="72bec-783">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="72bec-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="72bec-784">Beispiele</span><span class="sxs-lookup"><span data-stu-id="72bec-784">Examples</span></span>

<span data-ttu-id="72bec-785">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="72bec-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="72bec-786">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="72bec-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="72bec-787">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="72bec-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="72bec-788">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="72bec-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="72bec-789">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="72bec-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="72bec-790">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="72bec-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="72bec-791">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="72bec-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="72bec-792">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="72bec-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="72bec-793">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="72bec-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="72bec-794">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="72bec-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="72bec-795">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="72bec-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="72bec-796">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="72bec-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="72bec-797">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72bec-797">See also</span></span>

- [<span data-ttu-id="72bec-798">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="72bec-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="72bec-799">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="72bec-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="72bec-800">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="72bec-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="72bec-801">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="72bec-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
