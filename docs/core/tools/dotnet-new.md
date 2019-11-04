---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 05/06/2019
ms.openlocfilehash: c9529e135f48c80f445c91038294a3e7266486f1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420478"
---
# <a name="dotnet-new"></a><span data-ttu-id="9ceda-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9ceda-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9ceda-104">name</span><span class="sxs-lookup"><span data-stu-id="9ceda-104">Name</span></span>

<span data-ttu-id="9ceda-105">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="9ceda-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9ceda-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="9ceda-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="9ceda-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9ceda-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9ceda-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ceda-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9ceda-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9ceda-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ceda-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ceda-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="9ceda-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9ceda-111">Description</span></span>

<span data-ttu-id="9ceda-112">Der Befehl `dotnet new` bietet eine praktische Möglichkeit, ein gültiges .NET Core-Projekt zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9ceda-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="9ceda-113">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="9ceda-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="9ceda-114">Argumente</span><span class="sxs-lookup"><span data-stu-id="9ceda-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="9ceda-115">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="9ceda-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="9ceda-116">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="9ceda-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="9ceda-117">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="9ceda-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="9ceda-118">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** übereinstimmt, wird für diese beiden Spalten ein Abgleich der Teilzeichenfolge durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="9ceda-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9ceda-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="9ceda-120">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-120">The command contains a default list of templates.</span></span> <span data-ttu-id="9ceda-121">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9ceda-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 2.2.100 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="9ceda-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="9ceda-124">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9ceda-124">Templates</span></span>                                    | <span data-ttu-id="9ceda-125">Kurzname</span><span class="sxs-lookup"><span data-stu-id="9ceda-125">Short Name</span></span>        | <span data-ttu-id="9ceda-126">Sprache</span><span class="sxs-lookup"><span data-stu-id="9ceda-126">Language</span></span>     | <span data-ttu-id="9ceda-127">Tags</span><span class="sxs-lookup"><span data-stu-id="9ceda-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="9ceda-128">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="9ceda-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="9ceda-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-129">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-130">Common/Console</span><span class="sxs-lookup"><span data-stu-id="9ceda-130">Common/Console</span></span>                        |
| <span data-ttu-id="9ceda-131">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ceda-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="9ceda-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-132">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-133">Common/Library</span><span class="sxs-lookup"><span data-stu-id="9ceda-133">Common/Library</span></span>                        |
| <span data-ttu-id="9ceda-134">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="9ceda-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-135">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="9ceda-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="9ceda-137">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="9ceda-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-138">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="9ceda-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="9ceda-140">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="9ceda-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="9ceda-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-141">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="9ceda-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="9ceda-143">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="9ceda-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-144">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="9ceda-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="9ceda-146">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="9ceda-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="9ceda-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-147">[C#]</span></span>         | <span data-ttu-id="9ceda-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="9ceda-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="9ceda-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="9ceda-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-150">[C#]</span></span>         | <span data-ttu-id="9ceda-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="9ceda-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9ceda-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="9ceda-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-153">[C#]</span></span>         | <span data-ttu-id="9ceda-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="9ceda-155">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="9ceda-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="9ceda-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-156">[C#], F#</span></span>     | <span data-ttu-id="9ceda-157">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="9ceda-157">Web/Empty</span></span>                             |
| <span data-ttu-id="9ceda-158">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9ceda-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="9ceda-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-159">[C#], F#</span></span>     | <span data-ttu-id="9ceda-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="9ceda-160">Web/MVC</span></span>                               |
| <span data-ttu-id="9ceda-161">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="9ceda-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="9ceda-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="9ceda-162">`webapp`, `razor`</span></span> | <span data-ttu-id="9ceda-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-163">[C#]</span></span>         | <span data-ttu-id="9ceda-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="9ceda-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="9ceda-165">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="9ceda-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="9ceda-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-166">[C#]</span></span>         | <span data-ttu-id="9ceda-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="9ceda-168">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="9ceda-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="9ceda-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-169">[C#]</span></span>         | <span data-ttu-id="9ceda-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="9ceda-171">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="9ceda-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="9ceda-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-172">[C#]</span></span>         | <span data-ttu-id="9ceda-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="9ceda-174">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ceda-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="9ceda-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-175">[C#]</span></span>         | <span data-ttu-id="9ceda-176">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="9ceda-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="9ceda-177">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="9ceda-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="9ceda-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-178">[C#], F#</span></span>     | <span data-ttu-id="9ceda-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="9ceda-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="9ceda-180">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="9ceda-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="9ceda-181">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-181">Config</span></span>                                |
| <span data-ttu-id="9ceda-182">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="9ceda-183">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-183">Config</span></span>                                |
| <span data-ttu-id="9ceda-184">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="9ceda-185">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-185">Config</span></span>                                |
| <span data-ttu-id="9ceda-186">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="9ceda-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="9ceda-187">Lösung</span><span class="sxs-lookup"><span data-stu-id="9ceda-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9ceda-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ceda-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9ceda-189">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-189">The command contains a default list of templates.</span></span> <span data-ttu-id="9ceda-190">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9ceda-191">In der folgenden Tabelle werden die Vorlagen gezeigt, die bereits mit dem .NET Core SDK 2.1.300 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="9ceda-192">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="9ceda-193">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9ceda-193">Templates</span></span>                                    | <span data-ttu-id="9ceda-194">Kurzname</span><span class="sxs-lookup"><span data-stu-id="9ceda-194">Short Name</span></span>      | <span data-ttu-id="9ceda-195">Sprache</span><span class="sxs-lookup"><span data-stu-id="9ceda-195">Language</span></span>     | <span data-ttu-id="9ceda-196">Tags</span><span class="sxs-lookup"><span data-stu-id="9ceda-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="9ceda-197">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="9ceda-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="9ceda-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-198">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-199">Common/Console</span><span class="sxs-lookup"><span data-stu-id="9ceda-199">Common/Console</span></span>                        |
| <span data-ttu-id="9ceda-200">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ceda-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="9ceda-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-201">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-202">Common/Library</span><span class="sxs-lookup"><span data-stu-id="9ceda-202">Common/Library</span></span>                        |
| <span data-ttu-id="9ceda-203">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="9ceda-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-204">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="9ceda-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="9ceda-206">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="9ceda-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-207">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="9ceda-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="9ceda-209">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="9ceda-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="9ceda-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-210">[C#]</span></span>         | <span data-ttu-id="9ceda-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="9ceda-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="9ceda-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="9ceda-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-213">[C#]</span></span>         | <span data-ttu-id="9ceda-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="9ceda-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9ceda-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="9ceda-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-216">[C#]</span></span>         | <span data-ttu-id="9ceda-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="9ceda-218">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="9ceda-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="9ceda-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-219">[C#], F#</span></span>     | <span data-ttu-id="9ceda-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="9ceda-220">Web/Empty</span></span>                             |
| <span data-ttu-id="9ceda-221">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9ceda-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="9ceda-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-222">[C#], F#</span></span>     | <span data-ttu-id="9ceda-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="9ceda-223">Web/MVC</span></span>                               |
| <span data-ttu-id="9ceda-224">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="9ceda-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="9ceda-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-225">[C#]</span></span>         | <span data-ttu-id="9ceda-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="9ceda-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="9ceda-227">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="9ceda-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="9ceda-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-228">[C#]</span></span>         | <span data-ttu-id="9ceda-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="9ceda-230">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="9ceda-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="9ceda-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-231">[C#]</span></span>         | <span data-ttu-id="9ceda-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="9ceda-233">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="9ceda-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="9ceda-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-234">[C#]</span></span>         | <span data-ttu-id="9ceda-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="9ceda-236">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ceda-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="9ceda-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-237">[C#]</span></span>         | <span data-ttu-id="9ceda-238">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="9ceda-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="9ceda-239">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="9ceda-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="9ceda-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-240">[C#], F#</span></span>     | <span data-ttu-id="9ceda-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="9ceda-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="9ceda-242">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="9ceda-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="9ceda-243">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-243">Config</span></span>                                |
| <span data-ttu-id="9ceda-244">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="9ceda-245">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-245">Config</span></span>                                |
| <span data-ttu-id="9ceda-246">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="9ceda-247">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-247">Config</span></span>                                |
| <span data-ttu-id="9ceda-248">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="9ceda-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="9ceda-249">Lösung</span><span class="sxs-lookup"><span data-stu-id="9ceda-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9ceda-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9ceda-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="9ceda-251">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-251">The command contains a default list of templates.</span></span> <span data-ttu-id="9ceda-252">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9ceda-253">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 2.0.0 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="9ceda-254">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="9ceda-255">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9ceda-255">Templates</span></span>                                    | <span data-ttu-id="9ceda-256">Kurzname</span><span class="sxs-lookup"><span data-stu-id="9ceda-256">Short Name</span></span>    | <span data-ttu-id="9ceda-257">Sprache</span><span class="sxs-lookup"><span data-stu-id="9ceda-257">Language</span></span>     | <span data-ttu-id="9ceda-258">Tags</span><span class="sxs-lookup"><span data-stu-id="9ceda-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="9ceda-259">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="9ceda-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="9ceda-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-260">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-261">Common/Console</span><span class="sxs-lookup"><span data-stu-id="9ceda-261">Common/Console</span></span>      |
| <span data-ttu-id="9ceda-262">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ceda-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="9ceda-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-263">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-264">Common/Library</span><span class="sxs-lookup"><span data-stu-id="9ceda-264">Common/Library</span></span>      |
| <span data-ttu-id="9ceda-265">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="9ceda-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-266">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="9ceda-267">Test/MSTest</span></span>         |
| <span data-ttu-id="9ceda-268">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="9ceda-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9ceda-269">[C#], F#, VB</span></span> | <span data-ttu-id="9ceda-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="9ceda-270">Test/xUnit</span></span>          |
| <span data-ttu-id="9ceda-271">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="9ceda-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="9ceda-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-272">[C#], F#</span></span>     | <span data-ttu-id="9ceda-273">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="9ceda-273">Web/Empty</span></span>           |
| <span data-ttu-id="9ceda-274">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9ceda-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="9ceda-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-275">[C#], F#</span></span>     | <span data-ttu-id="9ceda-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="9ceda-276">Web/MVC</span></span>             |
| <span data-ttu-id="9ceda-277">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="9ceda-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="9ceda-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-278">[C#]</span></span>         | <span data-ttu-id="9ceda-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="9ceda-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="9ceda-280">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="9ceda-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="9ceda-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-281">[C#]</span></span>         | <span data-ttu-id="9ceda-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="9ceda-283">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="9ceda-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="9ceda-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-284">[C#]</span></span>         | <span data-ttu-id="9ceda-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="9ceda-286">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="9ceda-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="9ceda-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-287">[C#]</span></span>         | <span data-ttu-id="9ceda-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9ceda-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="9ceda-289">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="9ceda-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="9ceda-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-290">[C#], F#</span></span>     | <span data-ttu-id="9ceda-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="9ceda-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="9ceda-292">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="9ceda-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="9ceda-293">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-293">Config</span></span>              |
| <span data-ttu-id="9ceda-294">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="9ceda-295">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-295">Config</span></span>              |
| <span data-ttu-id="9ceda-296">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="9ceda-297">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-297">Config</span></span>              |
| <span data-ttu-id="9ceda-298">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="9ceda-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="9ceda-299">Lösung</span><span class="sxs-lookup"><span data-stu-id="9ceda-299">Solution</span></span>            |
| <span data-ttu-id="9ceda-300">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="9ceda-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="9ceda-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="9ceda-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="9ceda-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="9ceda-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="9ceda-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9ceda-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="9ceda-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9ceda-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ceda-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ceda-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9ceda-307">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-307">The command contains a default list of templates.</span></span> <span data-ttu-id="9ceda-308">Verwenden Sie `dotnet new -all`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="9ceda-309">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK 1.0.1 vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="9ceda-310">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="9ceda-311">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="9ceda-311">Templates</span></span>            | <span data-ttu-id="9ceda-312">Kurzname</span><span class="sxs-lookup"><span data-stu-id="9ceda-312">Short Name</span></span>    | <span data-ttu-id="9ceda-313">Sprache</span><span class="sxs-lookup"><span data-stu-id="9ceda-313">Language</span></span> | <span data-ttu-id="9ceda-314">Tags</span><span class="sxs-lookup"><span data-stu-id="9ceda-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="9ceda-315">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="9ceda-315">Console Application</span></span>  | `console`     | <span data-ttu-id="9ceda-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-316">[C#], F#</span></span> | <span data-ttu-id="9ceda-317">Common/Console</span><span class="sxs-lookup"><span data-stu-id="9ceda-317">Common/Console</span></span> |
| <span data-ttu-id="9ceda-318">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="9ceda-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="9ceda-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-319">[C#], F#</span></span> | <span data-ttu-id="9ceda-320">Common/Library</span><span class="sxs-lookup"><span data-stu-id="9ceda-320">Common/Library</span></span> |
| <span data-ttu-id="9ceda-321">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="9ceda-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-322">[C#], F#</span></span> | <span data-ttu-id="9ceda-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="9ceda-323">Test/MSTest</span></span>    |
| <span data-ttu-id="9ceda-324">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="9ceda-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-325">[C#], F#</span></span> | <span data-ttu-id="9ceda-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="9ceda-326">Test/xUnit</span></span>     |
| <span data-ttu-id="9ceda-327">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="9ceda-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="9ceda-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-328">[C#]</span></span>     | <span data-ttu-id="9ceda-329">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="9ceda-329">Web/Empty</span></span>      |
| <span data-ttu-id="9ceda-330">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="9ceda-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="9ceda-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9ceda-331">[C#], F#</span></span> | <span data-ttu-id="9ceda-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="9ceda-332">Web/MVC</span></span>        |
| <span data-ttu-id="9ceda-333">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="9ceda-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="9ceda-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="9ceda-334">[C#]</span></span>     | <span data-ttu-id="9ceda-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="9ceda-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="9ceda-336">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="9ceda-337">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-337">Config</span></span>         |
| <span data-ttu-id="9ceda-338">Webkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9ceda-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="9ceda-339">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="9ceda-339">Config</span></span>         |
| <span data-ttu-id="9ceda-340">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="9ceda-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="9ceda-341">Lösung</span><span class="sxs-lookup"><span data-stu-id="9ceda-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="9ceda-342">Optionen</span><span class="sxs-lookup"><span data-stu-id="9ceda-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="9ceda-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9ceda-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="9ceda-344">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="9ceda-345">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9ceda-346">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9ceda-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9ceda-347">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ceda-347">Prints out help for the command.</span></span> <span data-ttu-id="9ceda-348">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9ceda-349">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9ceda-350">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="9ceda-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="9ceda-351">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="9ceda-352">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="9ceda-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="9ceda-353">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9ceda-354">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ceda-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="9ceda-355">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9ceda-356">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="9ceda-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9ceda-357">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-357">The language of the template to create.</span></span> <span data-ttu-id="9ceda-358">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9ceda-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9ceda-359">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9ceda-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-360">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9ceda-361">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9ceda-362">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-362">The name for the created output.</span></span> <span data-ttu-id="9ceda-363">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ceda-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="9ceda-364">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9ceda-365">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-365">Location to place the generated output.</span></span> <span data-ttu-id="9ceda-366">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9ceda-367">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-367">Filters templates based on available types.</span></span> <span data-ttu-id="9ceda-368">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="9ceda-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9ceda-369">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9ceda-370">Wenn der Wert `<PATH|NUGET_ID>` weggelassen wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-371">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="9ceda-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9ceda-372">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="9ceda-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="9ceda-373">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9ceda-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ceda-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="9ceda-375">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9ceda-376">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9ceda-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9ceda-377">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ceda-377">Prints out help for the command.</span></span> <span data-ttu-id="9ceda-378">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9ceda-379">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9ceda-380">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="9ceda-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="9ceda-381">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="9ceda-382">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="9ceda-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="9ceda-383">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9ceda-384">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ceda-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="9ceda-385">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9ceda-386">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="9ceda-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9ceda-387">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-387">The language of the template to create.</span></span> <span data-ttu-id="9ceda-388">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9ceda-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9ceda-389">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9ceda-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-390">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9ceda-391">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9ceda-392">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-392">The name for the created output.</span></span> <span data-ttu-id="9ceda-393">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ceda-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="9ceda-394">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9ceda-395">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-395">Location to place the generated output.</span></span> <span data-ttu-id="9ceda-396">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9ceda-397">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-397">Filters templates based on available types.</span></span> <span data-ttu-id="9ceda-398">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="9ceda-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9ceda-399">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-400">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="9ceda-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9ceda-401">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="9ceda-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="9ceda-402">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9ceda-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9ceda-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="9ceda-404">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9ceda-405">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9ceda-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9ceda-406">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ceda-406">Prints out help for the command.</span></span> <span data-ttu-id="9ceda-407">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9ceda-408">Installiert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9ceda-409">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="9ceda-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="9ceda-410">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die das letzte stabile Paket darstellt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="9ceda-411">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="9ceda-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="9ceda-412">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9ceda-413">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ceda-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="9ceda-414">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9ceda-415">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="9ceda-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9ceda-416">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-416">The language of the template to create.</span></span> <span data-ttu-id="9ceda-417">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9ceda-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9ceda-418">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9ceda-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-419">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9ceda-420">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9ceda-421">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-421">The name for the created output.</span></span> <span data-ttu-id="9ceda-422">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ceda-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9ceda-423">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-423">Location to place the generated output.</span></span> <span data-ttu-id="9ceda-424">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9ceda-425">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-425">Filters templates based on available types.</span></span> <span data-ttu-id="9ceda-426">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="9ceda-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9ceda-427">Deinstalliert ein Quell- oder Vorlagenpack aus den bereitgestellten `PATH` oder`NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-428">Sie müssen den Pfad vollständig qualifizieren, um eine Vorlage durch einen Quell-`PATH` zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="9ceda-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9ceda-429">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="9ceda-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="9ceda-430">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="9ceda-431">Wenn Sie das Argument `PATH` oder `NUGET_ID`, das zum Deinstallieren einer Vorlage benötigt wird, nicht bestimmen können, werden durch Ausführung von `dotnet new --uninstall` ohne Argument alle installierten Vorlagen sowie die Argumente aufgelistet, die für die Deinstallation dieser Vorlagen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ceda-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ceda-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="9ceda-433">Zeigt alle Vorlagen für eine bestimmte Art von Projekt bei Ausführung im Kontext des `dotnet new`-Befehls allein an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="9ceda-434">Bei der Ausführung im Kontext einer bestimmten Vorlage wie z.B. `dotnet new web -all` wird `-all` als Flag zur Erzwingung der Erstellung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="9ceda-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="9ceda-435">Dies ist erforderlich, wenn das Ausgabeverzeichnis bereits ein Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="9ceda-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9ceda-436">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="9ceda-436">Prints out help for the command.</span></span> <span data-ttu-id="9ceda-437">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage wie z.B. `dotnet new mvc --help` aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="9ceda-438">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9ceda-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="9ceda-439">Beim Aufrufen für den `dotnet new`-Befehl werden die möglichen Vorlagen aufgelistet, die für das angegebene Verzeichnis verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="9ceda-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9ceda-440">Wenn das Verzeichnis bereits ein Projekt enthält, listet es z.B. nicht alle Projektvorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="9ceda-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="9ceda-441">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-441">The language of the template to create.</span></span> <span data-ttu-id="9ceda-442">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9ceda-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9ceda-443">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="9ceda-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="9ceda-444">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9ceda-445">In diesen Fällen müssen Sie den Sprachparameterwert einschließen, z.B. `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9ceda-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9ceda-446">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-446">The name for the created output.</span></span> <span data-ttu-id="9ceda-447">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="9ceda-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9ceda-448">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-448">Location to place the generated output.</span></span> <span data-ttu-id="9ceda-449">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="9ceda-450">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="9ceda-450">Template options</span></span>

<span data-ttu-id="9ceda-451">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="9ceda-451">Each project template may have additional options available.</span></span> <span data-ttu-id="9ceda-452">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="9ceda-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="9ceda-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="9ceda-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="9ceda-454">**console**</span><span class="sxs-lookup"><span data-stu-id="9ceda-454">**console**</span></span>

<span data-ttu-id="9ceda-455">`--langVersion <VERSION_NUMBER>`: Legt die `LangVersion`-Eigenschaft in der erstellten Projektdatei fest.</span><span class="sxs-lookup"><span data-stu-id="9ceda-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="9ceda-456">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9ceda-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="9ceda-457">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-457">Not supported for F#.</span></span>

<span data-ttu-id="9ceda-458">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="9ceda-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="9ceda-460">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-461">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-462">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-463">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="9ceda-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="9ceda-464">**razorclasslib**</span></span>

<span data-ttu-id="9ceda-465">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9ceda-466">**classlib**</span></span>

<span data-ttu-id="9ceda-467">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-468">Werte: `netcoreapp2.2`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9ceda-469">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9ceda-470">`--langVersion <VERSION_NUMBER>`: Legt die `LangVersion`-Eigenschaft in der erstellten Projektdatei fest.</span><span class="sxs-lookup"><span data-stu-id="9ceda-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="9ceda-471">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9ceda-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="9ceda-472">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-472">Not supported for F#.</span></span>

<span data-ttu-id="9ceda-473">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9ceda-474">**mstest, xunit**</span></span>

<span data-ttu-id="9ceda-475">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9ceda-476">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="9ceda-477">**nunit**</span></span>

<span data-ttu-id="9ceda-478">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-479">Der Standardwert ist `netcoreapp2.1`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="9ceda-480">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9ceda-481">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-482">**page**</span><span class="sxs-lookup"><span data-stu-id="9ceda-482">**page**</span></span>

<span data-ttu-id="9ceda-483">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="9ceda-484">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9ceda-485">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="9ceda-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9ceda-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9ceda-486">**viewimports**</span></span>

<span data-ttu-id="9ceda-487">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="9ceda-488">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9ceda-489">**web**</span><span class="sxs-lookup"><span data-stu-id="9ceda-489">**web**</span></span>

<span data-ttu-id="9ceda-490">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-491">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-492">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-493">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="9ceda-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="9ceda-494">**mvc, webapp**</span></span>

<span data-ttu-id="9ceda-495">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-496">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ceda-496">The possible values are:</span></span>

- <span data-ttu-id="9ceda-497">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ceda-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ceda-498">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9ceda-499">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ceda-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ceda-500">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ceda-501">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9ceda-502">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ceda-503">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ceda-504">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-505">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ceda-506">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ceda-507">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-508">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9ceda-509">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-510">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9ceda-511">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-512">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ceda-513">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ceda-514">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ceda-515">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ceda-516">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ceda-517">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ceda-518">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ceda-519">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-520">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ceda-521">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ceda-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ceda-522">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-523">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ceda-524">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9ceda-525">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-526">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9ceda-527">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ceda-528">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ceda-529">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-530">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-531">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9ceda-532">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="9ceda-533">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ceda-534">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-535">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9ceda-536">**webapi**</span></span>

<span data-ttu-id="9ceda-537">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-538">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ceda-538">The possible values are:</span></span>

- <span data-ttu-id="9ceda-539">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ceda-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ceda-540">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ceda-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ceda-541">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ceda-542">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ceda-543">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ceda-544">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-545">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ceda-546">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ceda-547">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-548">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ceda-549">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-550">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ceda-551">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ceda-552">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-553">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ceda-554">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ceda-555">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-556">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ceda-557">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ceda-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ceda-558">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-559">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ceda-560">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ceda-561">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ceda-562">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-563">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-564">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9ceda-565">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="9ceda-566">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ceda-567">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-568">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9ceda-569">**globaljson**</span></span>

<span data-ttu-id="9ceda-570">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="9ceda-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9ceda-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="9ceda-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="9ceda-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="9ceda-573">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9ceda-574">**classlib**</span></span>

<span data-ttu-id="9ceda-575">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-576">Werte: `netcoreapp2.1`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9ceda-577">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9ceda-578">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9ceda-579">**mstest, xunit**</span></span>

<span data-ttu-id="9ceda-580">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9ceda-581">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9ceda-582">**globaljson**</span></span>

<span data-ttu-id="9ceda-583">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="9ceda-584">**web**</span><span class="sxs-lookup"><span data-stu-id="9ceda-584">**web**</span></span>

<span data-ttu-id="9ceda-585">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-586">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-587">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-588">Diese Option gilt nur, wenn `IndividualAuth` oder `OrganizationalAuth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="9ceda-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9ceda-589">**webapi**</span></span>

<span data-ttu-id="9ceda-590">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-591">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ceda-591">The possible values are:</span></span>

- <span data-ttu-id="9ceda-592">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ceda-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ceda-593">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ceda-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ceda-594">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ceda-595">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ceda-596">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ceda-597">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-598">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ceda-599">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ceda-600">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-601">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ceda-602">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-603">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ceda-604">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ceda-605">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-606">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ceda-607">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ceda-608">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-609">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ceda-610">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ceda-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ceda-611">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-612">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ceda-613">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ceda-614">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ceda-615">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-616">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ceda-617">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-618">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-619">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-620">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9ceda-621">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="9ceda-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="9ceda-622">**mvc, razor**</span></span>

<span data-ttu-id="9ceda-623">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-624">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ceda-624">The possible values are:</span></span>

- <span data-ttu-id="9ceda-625">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ceda-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ceda-626">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9ceda-627">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ceda-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ceda-628">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ceda-629">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9ceda-630">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ceda-631">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ceda-632">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-633">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ceda-634">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ceda-635">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-636">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9ceda-637">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-638">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9ceda-639">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-640">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ceda-641">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ceda-642">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ceda-643">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ceda-644">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ceda-645">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ceda-646">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ceda-647">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-648">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ceda-649">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ceda-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ceda-650">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-651">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ceda-652">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9ceda-653">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-654">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9ceda-655">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ceda-656">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ceda-657">`--exclude-launch-settings`: schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="9ceda-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="9ceda-658">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="9ceda-659">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ceda-660">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-661">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-662">`--no-https`: Für das Projekt ist HTTPS nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9ceda-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="9ceda-663">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9ceda-664">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="9ceda-665">**page**</span><span class="sxs-lookup"><span data-stu-id="9ceda-665">**page**</span></span>

<span data-ttu-id="9ceda-666">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="9ceda-667">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9ceda-668">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="9ceda-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9ceda-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9ceda-669">**viewimports**</span></span>

<span data-ttu-id="9ceda-670">`-na|--namespace <NAMESPACE_NAME>`: Gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="9ceda-671">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="9ceda-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="9ceda-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="9ceda-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="9ceda-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="9ceda-674">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9ceda-675">**classlib**</span></span>

<span data-ttu-id="9ceda-676">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-677">Werte: `netcoreapp2.0`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard2.0`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ceda-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9ceda-678">Der Standardwert ist `netstandard2.0`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9ceda-679">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9ceda-680">**mstest, xunit**</span></span>

<span data-ttu-id="9ceda-681">`-p|--enable-pack`: ermöglicht das Verpacken des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9ceda-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9ceda-682">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9ceda-683">**globaljson**</span></span>

<span data-ttu-id="9ceda-684">`--sdk-version <VERSION_NUMBER>`: gibt die Version des .NET Core SDK an, das in der *global.json*-Datei werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="9ceda-685">**web**</span><span class="sxs-lookup"><span data-stu-id="9ceda-685">**web**</span></span>

<span data-ttu-id="9ceda-686">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9ceda-687">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9ceda-688">**webapi**</span></span>

<span data-ttu-id="9ceda-689">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-690">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ceda-690">The possible values are:</span></span>

- <span data-ttu-id="9ceda-691">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ceda-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ceda-692">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ceda-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ceda-693">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ceda-694">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ceda-695">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ceda-696">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-697">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ceda-698">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ceda-699">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-700">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ceda-701">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-702">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ceda-703">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ceda-704">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-705">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ceda-706">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ceda-707">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-708">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ceda-709">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ceda-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ceda-710">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-711">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ceda-712">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ceda-713">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ceda-714">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9ceda-715">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ceda-716">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-717">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="9ceda-718">**mvc, razor**</span></span>

<span data-ttu-id="9ceda-719">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-720">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="9ceda-720">The possible values are:</span></span>

- <span data-ttu-id="9ceda-721">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="9ceda-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9ceda-722">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9ceda-723">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="9ceda-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9ceda-724">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9ceda-725">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9ceda-726">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9ceda-727">`--aad-b2c-instance <INSTANCE>`: Die Azure AD B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9ceda-728">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-729">Der Standardwert ist `https://login.microsoftonline.com/tfp/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9ceda-730">`-ssp|--susi-policy-id <ID>`: die ID der Anmelde- und Registrierungsrichtlinien für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9ceda-731">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-732">`-rp|--reset-password-policy-id <ID>`: Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9ceda-733">Mit der `IndividualB2C`-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9ceda-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-734">`-ep|--edit-profile-policy-id <ID>`: Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9ceda-735">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-736">`--aad-instance <INSTANCE>`: Die Azure AD-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9ceda-737">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ceda-738">Der Standardwert ist `https://login.microsoftonline.com/`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9ceda-739">`--client-id <ID>`: Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9ceda-740">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9ceda-741">Der Standardwert ist `11111111-1111-1111-11111111111111111`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9ceda-742">`--domain <DOMAIN>`: Die Domäne für den Verzeichnismandanten</span><span class="sxs-lookup"><span data-stu-id="9ceda-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9ceda-743">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-744">Der Standardwert ist `qualified.domain.name`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9ceda-745">`--tenant-id <ID>`: Die Mandanten-ID der Verzeichnis, mit dem eine Verbindung hergestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="9ceda-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9ceda-746">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9ceda-747">Der Standardwert ist `22222222-2222-2222-2222-222222222222`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9ceda-748">`--callback-path <PATH>`: der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9ceda-749">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="9ceda-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9ceda-750">Der Standardwert ist `/signin-oidc`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9ceda-751">`-r|--org-read-access`: erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9ceda-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9ceda-752">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="9ceda-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9ceda-753">`--use-launch-settings`: enthält *launchSettings.json* in der generierten Vorlagenausgabe.</span><span class="sxs-lookup"><span data-stu-id="9ceda-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9ceda-754">`--use-browserlink`: enthält BrowserLink im Projekt</span><span class="sxs-lookup"><span data-stu-id="9ceda-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="9ceda-755">`-uld|--use-local-db`: gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9ceda-756">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="9ceda-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9ceda-757">`--no-restore`: führt keine implizite Wiederherstellung während der Projekterstellung durch.</span><span class="sxs-lookup"><span data-stu-id="9ceda-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9ceda-758">**page**</span><span class="sxs-lookup"><span data-stu-id="9ceda-758">**page**</span></span>

<span data-ttu-id="9ceda-759">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9ceda-760">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9ceda-761">`-np|--no-pagemodel`: erstellt die Seite ohne ein Seitenmodell</span><span class="sxs-lookup"><span data-stu-id="9ceda-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9ceda-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9ceda-762">**viewimports**</span></span>

<span data-ttu-id="9ceda-763">`-na|--namespace <NAMESPACE_NAME>`: gibt den Namespace für den generierten Code an.</span><span class="sxs-lookup"><span data-stu-id="9ceda-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9ceda-764">Der Standardwert ist `MyApp.Namespace`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9ceda-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9ceda-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9ceda-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="9ceda-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="9ceda-767">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-768">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="9ceda-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9ceda-769">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9ceda-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9ceda-770">**classlib**</span></span>

<span data-ttu-id="9ceda-771">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-772">Werte: `netcoreapp1.0`, `netcoreapp1.1` oder `netstandard1.0` bis `netstandard1.6`</span><span class="sxs-lookup"><span data-stu-id="9ceda-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="9ceda-773">Der Standardwert ist `netstandard1.4`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="9ceda-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="9ceda-774">**mvc**</span></span>

<span data-ttu-id="9ceda-775">`-f|--framework <FRAMEWORK>`: Gibt an, welches [Framework](../../standard/frameworks.md) verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9ceda-776">Werte: `netcoreapp1.0` oder `netcoreapp1.1`</span><span class="sxs-lookup"><span data-stu-id="9ceda-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9ceda-777">Der Standardwert ist `netcoreapp1.0`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9ceda-778">`-au|--auth <AUTHENTICATION_TYPE>`: Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="9ceda-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9ceda-779">Werte: `None` oder `Individual`</span><span class="sxs-lookup"><span data-stu-id="9ceda-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="9ceda-780">Der Standardwert ist `None`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-780">The default value is `None`.</span></span>

<span data-ttu-id="9ceda-781">`-uld|--use-local-db`: Gibt an, ob LocalDB anstelle von SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ceda-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="9ceda-782">Werte: `true` oder `false`</span><span class="sxs-lookup"><span data-stu-id="9ceda-782">Values: `true` or `false`.</span></span> <span data-ttu-id="9ceda-783">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="9ceda-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="9ceda-784">Beispiele</span><span class="sxs-lookup"><span data-stu-id="9ceda-784">Examples</span></span>

<span data-ttu-id="9ceda-785">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="9ceda-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="9ceda-786">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="9ceda-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="9ceda-787">Erstellen Sie ein .NET Standard-Klassenbibliotheksprojekt im angegebenen Verzeichnis (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="9ceda-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="9ceda-788">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="9ceda-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="9ceda-789">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="9ceda-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="9ceda-790">Liste Sie alle für MVC verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="9ceda-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="9ceda-791">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="9ceda-792">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="9ceda-793">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="9ceda-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="9ceda-794">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9ceda-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="9ceda-795">Installieren Sie Version 2.0 der Einzelseitenanwendungsvorlagen für ASP.NET Core (Befehlsoption, die ausschließlich für .NET Core SDK 1.1 und höher verfügbar ist):</span><span class="sxs-lookup"><span data-stu-id="9ceda-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="9ceda-796">Erstellen Sie eine *global.json* im aktuellen Verzeichnis, und legen Sie die SDK Version 2.0.0 fest (nur im .NET Core SDK 2.0 oder höher verfügbar):</span><span class="sxs-lookup"><span data-stu-id="9ceda-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="9ceda-797">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ceda-797">See also</span></span>

- [<span data-ttu-id="9ceda-798">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="9ceda-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="9ceda-799">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="9ceda-799">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="9ceda-800">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="9ceda-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="9ceda-801">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="9ceda-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
