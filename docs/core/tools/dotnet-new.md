---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102826"
---
# <a name="dotnet-new"></a><span data-ttu-id="c7863-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c7863-103">dotnet new</span></span>

<span data-ttu-id="c7863-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c7863-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c7863-105">name</span><span class="sxs-lookup"><span data-stu-id="c7863-105">Name</span></span>

<span data-ttu-id="c7863-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c7863-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c7863-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c7863-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="c7863-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7863-108">Description</span></span>

<span data-ttu-id="c7863-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c7863-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="c7863-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="c7863-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="c7863-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c7863-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="c7863-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="c7863-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="c7863-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c7863-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c7863-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="c7863-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c7863-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="c7863-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="c7863-116">Sie können `dotnet new --list` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c7863-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="c7863-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c7863-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="c7863-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="c7863-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="c7863-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="c7863-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="c7863-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c7863-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="c7863-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="c7863-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="c7863-122">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="c7863-122">The command contains a default list of templates.</span></span> <span data-ttu-id="c7863-123">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c7863-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c7863-124">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="c7863-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="c7863-125">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7863-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="c7863-126">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="c7863-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="c7863-127">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="c7863-127">Templates</span></span>                                    | <span data-ttu-id="c7863-128">Kurzname</span><span class="sxs-lookup"><span data-stu-id="c7863-128">Short name</span></span>                      | <span data-ttu-id="c7863-129">Sprache</span><span class="sxs-lookup"><span data-stu-id="c7863-129">Language</span></span>     | <span data-ttu-id="c7863-130">Tags</span><span class="sxs-lookup"><span data-stu-id="c7863-130">Tags</span></span>                                  | <span data-ttu-id="c7863-131">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="c7863-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="c7863-132">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="c7863-132">Console Application</span></span>                          | [<span data-ttu-id="c7863-133">console</span><span class="sxs-lookup"><span data-stu-id="c7863-133">console</span></span>](#console)             | <span data-ttu-id="c7863-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c7863-134">[C#], F#, VB</span></span> | <span data-ttu-id="c7863-135">Common/Console</span><span class="sxs-lookup"><span data-stu-id="c7863-135">Common/Console</span></span>                        | <span data-ttu-id="c7863-136">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-136">1.0</span></span>        |
| <span data-ttu-id="c7863-137">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="c7863-137">Class library</span></span>                                | [<span data-ttu-id="c7863-138">classlib</span><span class="sxs-lookup"><span data-stu-id="c7863-138">classlib</span></span>](#classlib)           | <span data-ttu-id="c7863-139">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c7863-139">[C#], F#, VB</span></span> | <span data-ttu-id="c7863-140">Common/Library</span><span class="sxs-lookup"><span data-stu-id="c7863-140">Common/Library</span></span>                        | <span data-ttu-id="c7863-141">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-141">1.0</span></span>        |
| <span data-ttu-id="c7863-142">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="c7863-142">WPF Application</span></span>                              | [<span data-ttu-id="c7863-143">wpf</span><span class="sxs-lookup"><span data-stu-id="c7863-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="c7863-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-144">[C#]</span></span>         | <span data-ttu-id="c7863-145">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c7863-145">Common/WPF</span></span>                            | <span data-ttu-id="c7863-146">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-146">3.0</span></span>        |
| <span data-ttu-id="c7863-147">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="c7863-147">WPF Class library</span></span>                            | [<span data-ttu-id="c7863-148">wpflib</span><span class="sxs-lookup"><span data-stu-id="c7863-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="c7863-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-149">[C#]</span></span>         | <span data-ttu-id="c7863-150">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c7863-150">Common/WPF</span></span>                            | <span data-ttu-id="c7863-151">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-151">3.0</span></span>        |
| <span data-ttu-id="c7863-152">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="c7863-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="c7863-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="c7863-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="c7863-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-154">[C#]</span></span>         | <span data-ttu-id="c7863-155">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c7863-155">Common/WPF</span></span>                            | <span data-ttu-id="c7863-156">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-156">3.0</span></span>        |
| <span data-ttu-id="c7863-157">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="c7863-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="c7863-158">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="c7863-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="c7863-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-159">[C#]</span></span>         | <span data-ttu-id="c7863-160">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c7863-160">Common/WPF</span></span>                            | <span data-ttu-id="c7863-161">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-161">3.0</span></span>        |
| <span data-ttu-id="c7863-162">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="c7863-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="c7863-163">winforms</span><span class="sxs-lookup"><span data-stu-id="c7863-163">winforms</span></span>](#winforms)           | <span data-ttu-id="c7863-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-164">[C#]</span></span>         | <span data-ttu-id="c7863-165">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="c7863-165">Common/WinForms</span></span>                       | <span data-ttu-id="c7863-166">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-166">3.0</span></span>        |
| <span data-ttu-id="c7863-167">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="c7863-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="c7863-168">winforms</span><span class="sxs-lookup"><span data-stu-id="c7863-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="c7863-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-169">[C#]</span></span>         | <span data-ttu-id="c7863-170">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="c7863-170">Common/WinForms</span></span>                       | <span data-ttu-id="c7863-171">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-171">3.0</span></span>        |
| <span data-ttu-id="c7863-172">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="c7863-172">Worker Service</span></span>                               | [<span data-ttu-id="c7863-173">worker</span><span class="sxs-lookup"><span data-stu-id="c7863-173">worker</span></span>](#web-others)           | <span data-ttu-id="c7863-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-174">[C#]</span></span>         | <span data-ttu-id="c7863-175">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="c7863-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="c7863-176">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-176">3.0</span></span>        |
| <span data-ttu-id="c7863-177">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="c7863-177">Unit Test Project</span></span>                            | [<span data-ttu-id="c7863-178">mstest</span><span class="sxs-lookup"><span data-stu-id="c7863-178">mstest</span></span>](#test)                 | <span data-ttu-id="c7863-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c7863-179">[C#], F#, VB</span></span> | <span data-ttu-id="c7863-180">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="c7863-180">Test/MSTest</span></span>                           | <span data-ttu-id="c7863-181">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-181">1.0</span></span>        |
| <span data-ttu-id="c7863-182">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="c7863-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="c7863-183">nunit</span><span class="sxs-lookup"><span data-stu-id="c7863-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="c7863-184">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c7863-184">[C#], F#, VB</span></span> | <span data-ttu-id="c7863-185">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c7863-185">Test/NUnit</span></span>                            | <span data-ttu-id="c7863-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="c7863-186">2.1.400</span></span>    |
| <span data-ttu-id="c7863-187">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="c7863-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="c7863-188">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c7863-188">[C#], F#, VB</span></span> | <span data-ttu-id="c7863-189">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c7863-189">Test/NUnit</span></span>                            | <span data-ttu-id="c7863-190">2.2</span><span class="sxs-lookup"><span data-stu-id="c7863-190">2.2</span></span>        |
| <span data-ttu-id="c7863-191">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="c7863-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="c7863-192">xunit</span><span class="sxs-lookup"><span data-stu-id="c7863-192">xunit</span></span>](#test)                  | <span data-ttu-id="c7863-193">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c7863-193">[C#], F#, VB</span></span> | <span data-ttu-id="c7863-194">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="c7863-194">Test/xUnit</span></span>                            | <span data-ttu-id="c7863-195">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-195">1.0</span></span>        |
| <span data-ttu-id="c7863-196">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="c7863-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="c7863-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-197">[C#]</span></span>         | <span data-ttu-id="c7863-198">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c7863-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="c7863-199">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-199">3.0</span></span>        |
| <span data-ttu-id="c7863-200">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="c7863-200">Razor Page</span></span>                                   | [<span data-ttu-id="c7863-201">page</span><span class="sxs-lookup"><span data-stu-id="c7863-201">page</span></span>](#page)                   | <span data-ttu-id="c7863-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-202">[C#]</span></span>         | <span data-ttu-id="c7863-203">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c7863-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="c7863-204">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-204">2.0</span></span>        |
| <span data-ttu-id="c7863-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c7863-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="c7863-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="c7863-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="c7863-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-207">[C#]</span></span>         | <span data-ttu-id="c7863-208">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c7863-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="c7863-209">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-209">2.0</span></span>        |
| <span data-ttu-id="c7863-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c7863-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="c7863-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-211">[C#]</span></span>         | <span data-ttu-id="c7863-212">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c7863-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="c7863-213">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-213">2.0</span></span>        |
| <span data-ttu-id="c7863-214">Blazor-Server-App</span><span class="sxs-lookup"><span data-stu-id="c7863-214">Blazor Server App</span></span>                            | [<span data-ttu-id="c7863-215">blazorserver</span><span class="sxs-lookup"><span data-stu-id="c7863-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="c7863-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-216">[C#]</span></span>         | <span data-ttu-id="c7863-217">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="c7863-217">Web/Blazor</span></span>                            | <span data-ttu-id="c7863-218">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-218">3.0</span></span>        |
| <span data-ttu-id="c7863-219">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="c7863-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="c7863-220">web</span><span class="sxs-lookup"><span data-stu-id="c7863-220">web</span></span>](#web)                     | <span data-ttu-id="c7863-221">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c7863-221">[C#], F#</span></span>     | <span data-ttu-id="c7863-222">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="c7863-222">Web/Empty</span></span>                             | <span data-ttu-id="c7863-223">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-223">1.0</span></span>        |
| <span data-ttu-id="c7863-224">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c7863-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="c7863-225">mvc</span><span class="sxs-lookup"><span data-stu-id="c7863-225">mvc</span></span>](#web-options)             | <span data-ttu-id="c7863-226">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c7863-226">[C#], F#</span></span>     | <span data-ttu-id="c7863-227">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="c7863-227">Web/MVC</span></span>                               | <span data-ttu-id="c7863-228">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-228">1.0</span></span>        |
| <span data-ttu-id="c7863-229">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="c7863-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="c7863-230">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="c7863-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="c7863-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-231">[C#]</span></span>         | <span data-ttu-id="c7863-232">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="c7863-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="c7863-233">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="c7863-234">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="c7863-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="c7863-235">angular</span><span class="sxs-lookup"><span data-stu-id="c7863-235">angular</span></span>](#spa)                 | <span data-ttu-id="c7863-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-236">[C#]</span></span>         | <span data-ttu-id="c7863-237">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c7863-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c7863-238">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-238">2.0</span></span>        |
| <span data-ttu-id="c7863-239">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="c7863-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="c7863-240">react</span><span class="sxs-lookup"><span data-stu-id="c7863-240">react</span></span>](#spa)                   | <span data-ttu-id="c7863-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-241">[C#]</span></span>         | <span data-ttu-id="c7863-242">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c7863-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c7863-243">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-243">2.0</span></span>        |
| <span data-ttu-id="c7863-244">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="c7863-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="c7863-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="c7863-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="c7863-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-246">[C#]</span></span>         | <span data-ttu-id="c7863-247">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c7863-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c7863-248">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-248">2.0</span></span>        |
| <span data-ttu-id="c7863-249">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="c7863-249">Razor Class Library</span></span>                          | [<span data-ttu-id="c7863-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c7863-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="c7863-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-251">[C#]</span></span>         | <span data-ttu-id="c7863-252">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="c7863-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="c7863-253">2.1</span><span class="sxs-lookup"><span data-stu-id="c7863-253">2.1</span></span>        |
| <span data-ttu-id="c7863-254">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="c7863-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="c7863-255">webapi</span><span class="sxs-lookup"><span data-stu-id="c7863-255">webapi</span></span>](#webapi)               | <span data-ttu-id="c7863-256">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c7863-256">[C#], F#</span></span>     | <span data-ttu-id="c7863-257">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="c7863-257">Web/WebAPI</span></span>                            | <span data-ttu-id="c7863-258">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-258">1.0</span></span>        |
| <span data-ttu-id="c7863-259">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="c7863-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="c7863-260">grpc</span><span class="sxs-lookup"><span data-stu-id="c7863-260">grpc</span></span>](#web-others)             | <span data-ttu-id="c7863-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="c7863-261">[C#]</span></span>         | <span data-ttu-id="c7863-262">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c7863-262">Web/gRPC</span></span>                              | <span data-ttu-id="c7863-263">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-263">3.0</span></span>        |
| <span data-ttu-id="c7863-264">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="c7863-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="c7863-265">proto</span><span class="sxs-lookup"><span data-stu-id="c7863-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="c7863-266">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c7863-266">Web/gRPC</span></span>                              | <span data-ttu-id="c7863-267">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-267">3.0</span></span>        |
| <span data-ttu-id="c7863-268">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="c7863-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="c7863-269">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c7863-269">Config</span></span>                                | <span data-ttu-id="c7863-270">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-270">3.0</span></span>        |
| <span data-ttu-id="c7863-271">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="c7863-271">global.json file</span></span>                             | [<span data-ttu-id="c7863-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="c7863-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="c7863-273">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c7863-273">Config</span></span>                                | <span data-ttu-id="c7863-274">2.0</span><span class="sxs-lookup"><span data-stu-id="c7863-274">2.0</span></span>        |
| <span data-ttu-id="c7863-275">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c7863-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="c7863-276">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c7863-276">Config</span></span>                                | <span data-ttu-id="c7863-277">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-277">1.0</span></span>        |
| <span data-ttu-id="c7863-278">dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="c7863-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="c7863-279">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c7863-279">Config</span></span>                                | <span data-ttu-id="c7863-280">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-280">3.0</span></span>        |
| <span data-ttu-id="c7863-281">Web Config</span><span class="sxs-lookup"><span data-stu-id="c7863-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="c7863-282">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c7863-282">Config</span></span>                                | <span data-ttu-id="c7863-283">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-283">1.0</span></span>        |
| <span data-ttu-id="c7863-284">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="c7863-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="c7863-285">Lösung</span><span class="sxs-lookup"><span data-stu-id="c7863-285">Solution</span></span>                              | <span data-ttu-id="c7863-286">1.0</span><span class="sxs-lookup"><span data-stu-id="c7863-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="c7863-287">Optionen</span><span class="sxs-lookup"><span data-stu-id="c7863-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="c7863-288">Zeigt eine Zusammenfassung der Vorgänge an, die auftreten, nachdem der angegebene Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c7863-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="c7863-289">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="c7863-290">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c7863-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c7863-291">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="c7863-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c7863-292">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c7863-292">Prints out help for the command.</span></span> <span data-ttu-id="c7863-293">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c7863-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="c7863-294">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c7863-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="c7863-295">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c7863-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c7863-296">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="c7863-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c7863-297">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7863-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="c7863-298">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="c7863-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="c7863-299">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c7863-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="c7863-300">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c7863-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="c7863-301">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c7863-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="c7863-302">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c7863-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="c7863-303">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="c7863-303">The language of the template to create.</span></span> <span data-ttu-id="c7863-304">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c7863-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c7863-305">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="c7863-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7863-306">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="c7863-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c7863-307">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="c7863-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="c7863-308">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c7863-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="c7863-309">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c7863-309">The name for the created output.</span></span> <span data-ttu-id="c7863-310">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7863-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="c7863-311">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="c7863-312">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c7863-313">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c7863-313">Location to place the generated output.</span></span> <span data-ttu-id="c7863-314">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c7863-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="c7863-315">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="c7863-315">Filters templates based on available types.</span></span> <span data-ttu-id="c7863-316">Folgende Werte sind vordefiniert: `project`, `item` oder `other`.</span><span class="sxs-lookup"><span data-stu-id="c7863-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="c7863-317">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c7863-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c7863-318">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7863-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="c7863-319">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="c7863-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="c7863-320">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="c7863-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c7863-321">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="c7863-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c7863-322">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="c7863-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="c7863-323">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="c7863-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="c7863-324">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="c7863-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="c7863-325">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="c7863-326">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c7863-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="c7863-327">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="c7863-328">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="c7863-328">Template options</span></span>

<span data-ttu-id="c7863-329">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="c7863-329">Each project template may have additional options available.</span></span> <span data-ttu-id="c7863-330">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="c7863-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="c7863-331">Konsole</span><span class="sxs-lookup"><span data-stu-id="c7863-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-332">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-333">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c7863-334">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-335">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-335">SDK version</span></span> | <span data-ttu-id="c7863-336">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-337">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-338">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c7863-339">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c7863-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c7863-340">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c7863-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c7863-341">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7863-341">Not supported for F#.</span></span> <span data-ttu-id="c7863-342">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c7863-343">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c7863-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-344">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="c7863-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="c7863-345">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="c7863-346">classlib</span><span class="sxs-lookup"><span data-stu-id="c7863-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-347">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-348">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c7863-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c7863-349">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c7863-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c7863-350">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c7863-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c7863-351">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c7863-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c7863-352">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c7863-352">Not supported for F#.</span></span> <span data-ttu-id="c7863-353">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c7863-354">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c7863-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-355">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="c7863-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="c7863-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-357">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-358">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="c7863-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c7863-359">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c7863-360">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c7863-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c7863-361">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c7863-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c7863-362">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c7863-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-363">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="c7863-364">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="c7863-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c7863-365">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c7863-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c7863-366">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c7863-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c7863-367">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c7863-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-368">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="c7863-369">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="c7863-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-370">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-371">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="c7863-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c7863-372">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-373">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-374">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="c7863-375">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="c7863-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-376">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-377">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c7863-378">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-379">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-379">SDK version</span></span> | <span data-ttu-id="c7863-380">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-381">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-382">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c7863-383">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c7863-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-384">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="c7863-385">nunit</span><span class="sxs-lookup"><span data-stu-id="c7863-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-386">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="c7863-387">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-388">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-388">SDK version</span></span> | <span data-ttu-id="c7863-389">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-390">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-391">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c7863-392">2.2</span><span class="sxs-lookup"><span data-stu-id="c7863-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="c7863-393">2.1</span><span class="sxs-lookup"><span data-stu-id="c7863-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c7863-394">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c7863-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-395">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="c7863-396">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="c7863-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="c7863-397">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="c7863-397">Namespace for the generated code.</span></span> <span data-ttu-id="c7863-398">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c7863-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="c7863-399">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="c7863-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="c7863-400">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="c7863-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="c7863-401">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="c7863-401">Namespace for the generated code.</span></span> <span data-ttu-id="c7863-402">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c7863-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="c7863-403">blazorserver</span><span class="sxs-lookup"><span data-stu-id="c7863-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c7863-404">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c7863-404">The type of authentication to use.</span></span> <span data-ttu-id="c7863-405">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c7863-405">The possible values are:</span></span>

  - <span data-ttu-id="c7863-406">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c7863-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c7863-407">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7863-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c7863-408">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c7863-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c7863-409">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c7863-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c7863-410">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="c7863-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c7863-411">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7863-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c7863-412">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c7863-413">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-414">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c7863-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c7863-415">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c7863-416">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c7863-417">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="c7863-418">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c7863-419">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c7863-420">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c7863-421">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c7863-422">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c7863-423">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c7863-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c7863-424">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-424">The Client ID for this project.</span></span> <span data-ttu-id="c7863-425">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c7863-426">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c7863-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c7863-427">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c7863-427">The domain for the directory tenant.</span></span> <span data-ttu-id="c7863-428">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-429">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c7863-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c7863-430">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c7863-431">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c7863-432">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c7863-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c7863-433">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c7863-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c7863-434">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-435">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c7863-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c7863-436">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c7863-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c7863-437">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-438">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c7863-439">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7863-439">Turns off HTTPS.</span></span> <span data-ttu-id="c7863-440">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7863-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c7863-441">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c7863-442">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-443">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="c7863-444">Web</span><span class="sxs-lookup"><span data-stu-id="c7863-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-445">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-446">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-447">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c7863-448">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-449">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-449">SDK version</span></span> | <span data-ttu-id="c7863-450">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-451">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-452">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c7863-453">2.1</span><span class="sxs-lookup"><span data-stu-id="c7863-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c7863-454">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c7863-455">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7863-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="c7863-456">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="c7863-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c7863-457">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c7863-457">The type of authentication to use.</span></span> <span data-ttu-id="c7863-458">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c7863-458">The possible values are:</span></span>

  - <span data-ttu-id="c7863-459">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c7863-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c7863-460">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7863-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c7863-461">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c7863-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c7863-462">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c7863-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c7863-463">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="c7863-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c7863-464">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7863-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c7863-465">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c7863-466">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-467">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c7863-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c7863-468">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c7863-469">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c7863-470">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="c7863-471">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c7863-472">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c7863-473">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c7863-474">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c7863-475">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c7863-476">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c7863-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c7863-477">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-477">The Client ID for this project.</span></span> <span data-ttu-id="c7863-478">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c7863-479">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c7863-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c7863-480">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c7863-480">The domain for the directory tenant.</span></span> <span data-ttu-id="c7863-481">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-482">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c7863-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c7863-483">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c7863-484">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c7863-485">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c7863-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c7863-486">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c7863-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c7863-487">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-488">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c7863-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c7863-489">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c7863-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c7863-490">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-491">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c7863-492">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7863-492">Turns off HTTPS.</span></span> <span data-ttu-id="c7863-493">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7863-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c7863-494">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c7863-495">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-496">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-497">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c7863-498">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-499">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-499">SDK version</span></span> | <span data-ttu-id="c7863-500">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-501">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-502">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="c7863-503">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="c7863-504">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="c7863-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="c7863-505">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="c7863-506">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c7863-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="c7863-507">Die Option ist ab .NET Core 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="c7863-508">angular, react</span><span class="sxs-lookup"><span data-stu-id="c7863-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c7863-509">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c7863-509">The type of authentication to use.</span></span> <span data-ttu-id="c7863-510">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="c7863-511">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c7863-511">The possible values are:</span></span>

  - <span data-ttu-id="c7863-512">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c7863-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c7863-513">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7863-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-514">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-515">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c7863-516">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7863-516">Turns off HTTPS.</span></span> <span data-ttu-id="c7863-517">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="c7863-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c7863-518">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c7863-519">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-520">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-521">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-522">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c7863-523">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-524">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-524">SDK version</span></span> | <span data-ttu-id="c7863-525">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-526">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-527">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c7863-528">2.1</span><span class="sxs-lookup"><span data-stu-id="c7863-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="c7863-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="c7863-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-530">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-531">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-532">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c7863-533">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-534">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-534">SDK version</span></span> | <span data-ttu-id="c7863-535">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-536">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-537">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c7863-538">2.1</span><span class="sxs-lookup"><span data-stu-id="c7863-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="c7863-539">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c7863-540">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7863-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="c7863-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c7863-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="c7863-542">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="c7863-543">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="c7863-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="c7863-544">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c7863-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="c7863-545">Web-API</span><span class="sxs-lookup"><span data-stu-id="c7863-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c7863-546">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c7863-546">The type of authentication to use.</span></span> <span data-ttu-id="c7863-547">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c7863-547">The possible values are:</span></span>

  - <span data-ttu-id="c7863-548">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c7863-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c7863-549">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c7863-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c7863-550">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c7863-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c7863-551">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c7863-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c7863-552">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c7863-553">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c7863-554">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c7863-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c7863-555">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c7863-556">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c7863-557">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c7863-558">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c7863-559">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c7863-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c7863-560">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c7863-560">The Client ID for this project.</span></span> <span data-ttu-id="c7863-561">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c7863-562">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c7863-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c7863-563">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c7863-563">The domain for the directory tenant.</span></span> <span data-ttu-id="c7863-564">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c7863-565">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c7863-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c7863-566">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c7863-567">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c7863-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c7863-568">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c7863-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c7863-569">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c7863-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c7863-570">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c7863-571">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c7863-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c7863-572">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c7863-572">Turns off HTTPS.</span></span> <span data-ttu-id="c7863-573">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c7863-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c7863-574">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7863-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c7863-575">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c7863-576">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c7863-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c7863-577">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c7863-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c7863-578">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7863-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c7863-579">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c7863-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c7863-580">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c7863-580">SDK version</span></span> | <span data-ttu-id="c7863-581">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c7863-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c7863-582">3.1</span><span class="sxs-lookup"><span data-stu-id="c7863-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c7863-583">3.0</span><span class="sxs-lookup"><span data-stu-id="c7863-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c7863-584">2.1</span><span class="sxs-lookup"><span data-stu-id="c7863-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c7863-585">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c7863-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="c7863-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="c7863-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="c7863-587">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c7863-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="c7863-588">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c7863-588">Examples</span></span>

- <span data-ttu-id="c7863-589">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="c7863-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="c7863-590">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c7863-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="c7863-591">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="c7863-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="c7863-592">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="c7863-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="c7863-593">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="c7863-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="c7863-594">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="c7863-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="c7863-595">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="c7863-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="c7863-596">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7863-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="c7863-597">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="c7863-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="c7863-598">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c7863-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="c7863-599">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="c7863-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="c7863-600">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="c7863-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="c7863-601">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="c7863-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="c7863-602">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7863-602">See also</span></span>

- [<span data-ttu-id="c7863-603">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="c7863-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="c7863-604">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="c7863-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="c7863-605">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="c7863-605">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="c7863-606">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="c7863-606">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
