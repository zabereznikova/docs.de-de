---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 04/10/2020
ms.openlocfilehash: 1544f519f2a5f6a1a6e042c1db720eff45f5d98c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442240"
---
# <a name="dotnet-new"></a><span data-ttu-id="89491-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="89491-103">dotnet new</span></span>

<span data-ttu-id="89491-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="89491-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="89491-105">name</span><span class="sxs-lookup"><span data-stu-id="89491-105">Name</span></span>

<span data-ttu-id="89491-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="89491-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="89491-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="89491-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="89491-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89491-108">Description</span></span>

<span data-ttu-id="89491-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="89491-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="89491-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="89491-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="89491-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="89491-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="89491-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="89491-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="89491-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="89491-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="89491-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="89491-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="89491-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="89491-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="89491-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="89491-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="89491-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="89491-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="89491-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="89491-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="89491-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="89491-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="89491-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="89491-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="89491-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="89491-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="89491-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="89491-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="89491-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89491-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="89491-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="89491-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="89491-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="89491-125">Templates</span></span>                                    | <span data-ttu-id="89491-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="89491-126">Short name</span></span>                      | <span data-ttu-id="89491-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="89491-127">Language</span></span>     | <span data-ttu-id="89491-128">Tags</span><span class="sxs-lookup"><span data-stu-id="89491-128">Tags</span></span>                                  | <span data-ttu-id="89491-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="89491-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="89491-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="89491-130">Console Application</span></span>                          | [<span data-ttu-id="89491-131">console</span><span class="sxs-lookup"><span data-stu-id="89491-131">console</span></span>](#console)             | <span data-ttu-id="89491-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="89491-132">[C#], F#, VB</span></span> | <span data-ttu-id="89491-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="89491-133">Common/Console</span></span>                        | <span data-ttu-id="89491-134">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-134">1.0</span></span>        |
| <span data-ttu-id="89491-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="89491-135">Class library</span></span>                                | [<span data-ttu-id="89491-136">classlib</span><span class="sxs-lookup"><span data-stu-id="89491-136">classlib</span></span>](#classlib)           | <span data-ttu-id="89491-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="89491-137">[C#], F#, VB</span></span> | <span data-ttu-id="89491-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="89491-138">Common/Library</span></span>                        | <span data-ttu-id="89491-139">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-139">1.0</span></span>        |
| <span data-ttu-id="89491-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="89491-140">WPF Application</span></span>                              | [<span data-ttu-id="89491-141">wpf</span><span class="sxs-lookup"><span data-stu-id="89491-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="89491-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-142">[C#]</span></span>         | <span data-ttu-id="89491-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="89491-143">Common/WPF</span></span>                            | <span data-ttu-id="89491-144">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-144">3.0</span></span>        |
| <span data-ttu-id="89491-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="89491-145">WPF Class library</span></span>                            | [<span data-ttu-id="89491-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="89491-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="89491-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-147">[C#]</span></span>         | <span data-ttu-id="89491-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="89491-148">Common/WPF</span></span>                            | <span data-ttu-id="89491-149">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-149">3.0</span></span>        |
| <span data-ttu-id="89491-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="89491-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="89491-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="89491-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="89491-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-152">[C#]</span></span>         | <span data-ttu-id="89491-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="89491-153">Common/WPF</span></span>                            | <span data-ttu-id="89491-154">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-154">3.0</span></span>        |
| <span data-ttu-id="89491-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="89491-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="89491-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="89491-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="89491-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-157">[C#]</span></span>         | <span data-ttu-id="89491-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="89491-158">Common/WPF</span></span>                            | <span data-ttu-id="89491-159">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-159">3.0</span></span>        |
| <span data-ttu-id="89491-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="89491-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="89491-161">winforms</span><span class="sxs-lookup"><span data-stu-id="89491-161">winforms</span></span>](#winforms)           | <span data-ttu-id="89491-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-162">[C#]</span></span>         | <span data-ttu-id="89491-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="89491-163">Common/WinForms</span></span>                       | <span data-ttu-id="89491-164">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-164">3.0</span></span>        |
| <span data-ttu-id="89491-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="89491-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="89491-166">winforms</span><span class="sxs-lookup"><span data-stu-id="89491-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="89491-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-167">[C#]</span></span>         | <span data-ttu-id="89491-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="89491-168">Common/WinForms</span></span>                       | <span data-ttu-id="89491-169">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-169">3.0</span></span>        |
| <span data-ttu-id="89491-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="89491-170">Worker Service</span></span>                               | [<span data-ttu-id="89491-171">worker</span><span class="sxs-lookup"><span data-stu-id="89491-171">worker</span></span>](#web-others)           | <span data-ttu-id="89491-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-172">[C#]</span></span>         | <span data-ttu-id="89491-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="89491-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="89491-174">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-174">3.0</span></span>        |
| <span data-ttu-id="89491-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="89491-175">Unit Test Project</span></span>                            | [<span data-ttu-id="89491-176">mstest</span><span class="sxs-lookup"><span data-stu-id="89491-176">mstest</span></span>](#test)                 | <span data-ttu-id="89491-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="89491-177">[C#], F#, VB</span></span> | <span data-ttu-id="89491-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="89491-178">Test/MSTest</span></span>                           | <span data-ttu-id="89491-179">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-179">1.0</span></span>        |
| <span data-ttu-id="89491-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="89491-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="89491-181">nunit</span><span class="sxs-lookup"><span data-stu-id="89491-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="89491-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="89491-182">[C#], F#, VB</span></span> | <span data-ttu-id="89491-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="89491-183">Test/NUnit</span></span>                            | <span data-ttu-id="89491-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="89491-184">2.1.400</span></span>    |
| <span data-ttu-id="89491-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="89491-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="89491-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="89491-186">[C#], F#, VB</span></span> | <span data-ttu-id="89491-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="89491-187">Test/NUnit</span></span>                            | <span data-ttu-id="89491-188">2.2</span><span class="sxs-lookup"><span data-stu-id="89491-188">2.2</span></span>        |
| <span data-ttu-id="89491-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="89491-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="89491-190">xunit</span><span class="sxs-lookup"><span data-stu-id="89491-190">xunit</span></span>](#test)                  | <span data-ttu-id="89491-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="89491-191">[C#], F#, VB</span></span> | <span data-ttu-id="89491-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="89491-192">Test/xUnit</span></span>                            | <span data-ttu-id="89491-193">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-193">1.0</span></span>        |
| <span data-ttu-id="89491-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="89491-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="89491-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-195">[C#]</span></span>         | <span data-ttu-id="89491-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89491-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="89491-197">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-197">3.0</span></span>        |
| <span data-ttu-id="89491-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="89491-198">Razor Page</span></span>                                   | [<span data-ttu-id="89491-199">page</span><span class="sxs-lookup"><span data-stu-id="89491-199">page</span></span>](#page)                   | <span data-ttu-id="89491-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-200">[C#]</span></span>         | <span data-ttu-id="89491-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89491-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="89491-202">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-202">2.0</span></span>        |
| <span data-ttu-id="89491-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="89491-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="89491-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="89491-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="89491-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-205">[C#]</span></span>         | <span data-ttu-id="89491-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89491-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="89491-207">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-207">2.0</span></span>        |
| <span data-ttu-id="89491-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="89491-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="89491-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-209">[C#]</span></span>         | <span data-ttu-id="89491-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89491-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="89491-211">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-211">2.0</span></span>        |
| <span data-ttu-id="89491-212">Blazor-Server-App</span><span class="sxs-lookup"><span data-stu-id="89491-212">Blazor Server App</span></span>                            | [<span data-ttu-id="89491-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="89491-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="89491-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-214">[C#]</span></span>         | <span data-ttu-id="89491-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="89491-215">Web/Blazor</span></span>                            | <span data-ttu-id="89491-216">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-216">3.0</span></span>        |
| <span data-ttu-id="89491-217">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="89491-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="89491-218">web</span><span class="sxs-lookup"><span data-stu-id="89491-218">web</span></span>](#web)                     | <span data-ttu-id="89491-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="89491-219">[C#], F#</span></span>     | <span data-ttu-id="89491-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="89491-220">Web/Empty</span></span>                             | <span data-ttu-id="89491-221">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-221">1.0</span></span>        |
| <span data-ttu-id="89491-222">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="89491-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="89491-223">mvc</span><span class="sxs-lookup"><span data-stu-id="89491-223">mvc</span></span>](#web-options)             | <span data-ttu-id="89491-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="89491-224">[C#], F#</span></span>     | <span data-ttu-id="89491-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="89491-225">Web/MVC</span></span>                               | <span data-ttu-id="89491-226">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-226">1.0</span></span>        |
| <span data-ttu-id="89491-227">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="89491-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="89491-228">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="89491-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="89491-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-229">[C#]</span></span>         | <span data-ttu-id="89491-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="89491-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="89491-231">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="89491-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="89491-232">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="89491-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="89491-233">angular</span><span class="sxs-lookup"><span data-stu-id="89491-233">angular</span></span>](#spa)                 | <span data-ttu-id="89491-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-234">[C#]</span></span>         | <span data-ttu-id="89491-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="89491-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="89491-236">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-236">2.0</span></span>        |
| <span data-ttu-id="89491-237">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="89491-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="89491-238">react</span><span class="sxs-lookup"><span data-stu-id="89491-238">react</span></span>](#spa)                   | <span data-ttu-id="89491-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-239">[C#]</span></span>         | <span data-ttu-id="89491-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="89491-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="89491-241">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-241">2.0</span></span>        |
| <span data-ttu-id="89491-242">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="89491-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="89491-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="89491-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="89491-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-244">[C#]</span></span>         | <span data-ttu-id="89491-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="89491-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="89491-246">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-246">2.0</span></span>        |
| <span data-ttu-id="89491-247">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="89491-247">Razor Class Library</span></span>                          | [<span data-ttu-id="89491-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="89491-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="89491-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-249">[C#]</span></span>         | <span data-ttu-id="89491-250">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="89491-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="89491-251">2.1</span><span class="sxs-lookup"><span data-stu-id="89491-251">2.1</span></span>        |
| <span data-ttu-id="89491-252">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="89491-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="89491-253">webapi</span><span class="sxs-lookup"><span data-stu-id="89491-253">webapi</span></span>](#webapi)               | <span data-ttu-id="89491-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="89491-254">[C#], F#</span></span>     | <span data-ttu-id="89491-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="89491-255">Web/WebAPI</span></span>                            | <span data-ttu-id="89491-256">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-256">1.0</span></span>        |
| <span data-ttu-id="89491-257">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="89491-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="89491-258">grpc</span><span class="sxs-lookup"><span data-stu-id="89491-258">grpc</span></span>](#web-others)             | <span data-ttu-id="89491-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="89491-259">[C#]</span></span>         | <span data-ttu-id="89491-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="89491-260">Web/gRPC</span></span>                              | <span data-ttu-id="89491-261">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-261">3.0</span></span>        |
| <span data-ttu-id="89491-262">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="89491-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="89491-263">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="89491-263">Config</span></span>                                | <span data-ttu-id="89491-264">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-264">3.0</span></span>        |
| <span data-ttu-id="89491-265">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="89491-265">global.json file</span></span>                             | [<span data-ttu-id="89491-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="89491-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="89491-267">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="89491-267">Config</span></span>                                | <span data-ttu-id="89491-268">2.0</span><span class="sxs-lookup"><span data-stu-id="89491-268">2.0</span></span>        |
| <span data-ttu-id="89491-269">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="89491-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="89491-270">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="89491-270">Config</span></span>                                | <span data-ttu-id="89491-271">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-271">1.0</span></span>        |
| <span data-ttu-id="89491-272">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="89491-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="89491-273">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="89491-273">Config</span></span>                                | <span data-ttu-id="89491-274">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-274">3.0</span></span>        |
| <span data-ttu-id="89491-275">Web Config</span><span class="sxs-lookup"><span data-stu-id="89491-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="89491-276">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="89491-276">Config</span></span>                                | <span data-ttu-id="89491-277">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-277">1.0</span></span>        |
| <span data-ttu-id="89491-278">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="89491-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="89491-279">Lösung</span><span class="sxs-lookup"><span data-stu-id="89491-279">Solution</span></span>                              | <span data-ttu-id="89491-280">1.0</span><span class="sxs-lookup"><span data-stu-id="89491-280">1.0</span></span>        |
| <span data-ttu-id="89491-281">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="89491-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="89491-282">proto</span><span class="sxs-lookup"><span data-stu-id="89491-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="89491-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="89491-283">Web/gRPC</span></span>                              | <span data-ttu-id="89491-284">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="89491-285">Optionen</span><span class="sxs-lookup"><span data-stu-id="89491-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="89491-286">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="89491-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="89491-287">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="89491-288">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="89491-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="89491-289">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="89491-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="89491-290">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="89491-290">Prints out help for the command.</span></span> <span data-ttu-id="89491-291">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="89491-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="89491-292">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="89491-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="89491-293">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="89491-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="89491-294">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="89491-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="89491-295">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="89491-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="89491-296">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="89491-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="89491-297">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="89491-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="89491-298">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="89491-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="89491-299">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="89491-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="89491-300">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="89491-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="89491-301">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="89491-301">The language of the template to create.</span></span> <span data-ttu-id="89491-302">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="89491-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="89491-303">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="89491-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="89491-304">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="89491-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="89491-305">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="89491-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="89491-306">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="89491-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="89491-307">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="89491-307">The name for the created output.</span></span> <span data-ttu-id="89491-308">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="89491-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="89491-309">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="89491-310">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="89491-311">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="89491-311">Location to place the generated output.</span></span> <span data-ttu-id="89491-312">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="89491-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="89491-313">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="89491-313">Filters templates based on available types.</span></span> <span data-ttu-id="89491-314">Die Werte `project`, `item` und `other` sind vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="89491-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="89491-315">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="89491-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="89491-316">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="89491-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="89491-317">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="89491-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="89491-318">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="89491-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="89491-319">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="89491-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="89491-320">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="89491-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="89491-321">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="89491-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="89491-322">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="89491-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="89491-323">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="89491-324">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="89491-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="89491-325">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="89491-326">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="89491-326">Template options</span></span>

<span data-ttu-id="89491-327">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="89491-327">Each project template may have additional options available.</span></span> <span data-ttu-id="89491-328">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="89491-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="89491-329">Konsole</span><span class="sxs-lookup"><span data-stu-id="89491-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-330">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-331">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="89491-332">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-333">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-333">SDK version</span></span> | <span data-ttu-id="89491-334">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-335">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-336">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="89491-337">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="89491-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="89491-338">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="89491-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="89491-339">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89491-339">Not supported for F#.</span></span> <span data-ttu-id="89491-340">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="89491-341">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="89491-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-342">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="89491-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="89491-343">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="89491-344">classlib</span><span class="sxs-lookup"><span data-stu-id="89491-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-345">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-346">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89491-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="89491-347">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="89491-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="89491-348">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="89491-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="89491-349">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="89491-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="89491-350">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89491-350">Not supported for F#.</span></span> <span data-ttu-id="89491-351">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="89491-352">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="89491-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-353">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="89491-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="89491-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-355">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-356">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="89491-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="89491-357">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="89491-358">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="89491-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="89491-359">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="89491-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="89491-360">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="89491-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-361">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="89491-362">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="89491-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="89491-363">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="89491-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="89491-364">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="89491-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="89491-365">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="89491-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-366">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="89491-367">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="89491-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-368">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-369">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="89491-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="89491-370">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-371">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-372">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="89491-373">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="89491-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-374">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-375">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="89491-376">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-377">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-377">SDK version</span></span> | <span data-ttu-id="89491-378">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-379">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-380">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="89491-381">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="89491-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-382">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="89491-383">nunit</span><span class="sxs-lookup"><span data-stu-id="89491-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-384">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="89491-385">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-386">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-386">SDK version</span></span> | <span data-ttu-id="89491-387">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-388">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-389">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="89491-390">2.2</span><span class="sxs-lookup"><span data-stu-id="89491-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="89491-391">2.1</span><span class="sxs-lookup"><span data-stu-id="89491-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="89491-392">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="89491-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-393">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="89491-394">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="89491-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="89491-395">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="89491-395">Namespace for the generated code.</span></span> <span data-ttu-id="89491-396">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="89491-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="89491-397">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="89491-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="89491-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="89491-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="89491-399">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="89491-399">Namespace for the generated code.</span></span> <span data-ttu-id="89491-400">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="89491-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="89491-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="89491-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="89491-402">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="89491-402">The type of authentication to use.</span></span> <span data-ttu-id="89491-403">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="89491-403">The possible values are:</span></span>

  - <span data-ttu-id="89491-404">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="89491-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="89491-405">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89491-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="89491-406">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="89491-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="89491-407">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="89491-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="89491-408">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="89491-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="89491-409">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89491-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="89491-410">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="89491-411">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-412">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="89491-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="89491-413">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="89491-414">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="89491-415">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="89491-416">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="89491-417">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="89491-418">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="89491-419">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="89491-420">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="89491-421">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="89491-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="89491-422">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-422">The Client ID for this project.</span></span> <span data-ttu-id="89491-423">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="89491-424">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="89491-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="89491-425">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="89491-425">The domain for the directory tenant.</span></span> <span data-ttu-id="89491-426">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-427">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="89491-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="89491-428">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="89491-429">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="89491-430">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="89491-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="89491-431">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="89491-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="89491-432">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-433">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="89491-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="89491-434">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="89491-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="89491-435">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-436">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="89491-437">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89491-437">Turns off HTTPS.</span></span> <span data-ttu-id="89491-438">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89491-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="89491-439">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="89491-440">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-441">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="89491-442">Web</span><span class="sxs-lookup"><span data-stu-id="89491-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-443">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-444">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-445">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="89491-446">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-447">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-447">SDK version</span></span> | <span data-ttu-id="89491-448">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-449">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-450">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="89491-451">2.1</span><span class="sxs-lookup"><span data-stu-id="89491-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="89491-452">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="89491-453">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89491-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="89491-454">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="89491-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="89491-455">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="89491-455">The type of authentication to use.</span></span> <span data-ttu-id="89491-456">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="89491-456">The possible values are:</span></span>

  - <span data-ttu-id="89491-457">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="89491-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="89491-458">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89491-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="89491-459">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="89491-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="89491-460">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="89491-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="89491-461">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="89491-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="89491-462">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89491-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="89491-463">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="89491-464">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-465">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="89491-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="89491-466">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="89491-467">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="89491-468">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="89491-469">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="89491-470">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="89491-471">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="89491-472">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="89491-473">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="89491-474">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="89491-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="89491-475">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-475">The Client ID for this project.</span></span> <span data-ttu-id="89491-476">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="89491-477">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="89491-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="89491-478">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="89491-478">The domain for the directory tenant.</span></span> <span data-ttu-id="89491-479">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-480">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="89491-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="89491-481">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="89491-482">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="89491-483">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="89491-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="89491-484">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="89491-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="89491-485">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-486">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="89491-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="89491-487">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="89491-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="89491-488">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-489">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="89491-490">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89491-490">Turns off HTTPS.</span></span> <span data-ttu-id="89491-491">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89491-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="89491-492">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="89491-493">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-494">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-495">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="89491-496">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-497">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-497">SDK version</span></span> | <span data-ttu-id="89491-498">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-499">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-500">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="89491-501">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="89491-502">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="89491-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="89491-503">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="89491-504">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="89491-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="89491-505">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="89491-506">angular, react</span><span class="sxs-lookup"><span data-stu-id="89491-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="89491-507">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="89491-507">The type of authentication to use.</span></span> <span data-ttu-id="89491-508">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="89491-509">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="89491-509">The possible values are:</span></span>

  - <span data-ttu-id="89491-510">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="89491-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="89491-511">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89491-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-512">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-513">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="89491-514">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89491-514">Turns off HTTPS.</span></span> <span data-ttu-id="89491-515">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="89491-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="89491-516">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="89491-517">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-518">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-519">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-520">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="89491-521">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-522">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-522">SDK version</span></span> | <span data-ttu-id="89491-523">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-524">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-525">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="89491-526">2.1</span><span class="sxs-lookup"><span data-stu-id="89491-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="89491-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="89491-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-528">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-529">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-530">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="89491-531">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-532">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-532">SDK version</span></span> | <span data-ttu-id="89491-533">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-534">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-535">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="89491-536">2.1</span><span class="sxs-lookup"><span data-stu-id="89491-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="89491-537">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="89491-538">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89491-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="89491-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="89491-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="89491-540">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="89491-541">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="89491-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="89491-542">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="89491-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="89491-543">Web-API</span><span class="sxs-lookup"><span data-stu-id="89491-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="89491-544">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="89491-544">The type of authentication to use.</span></span> <span data-ttu-id="89491-545">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="89491-545">The possible values are:</span></span>

  - <span data-ttu-id="89491-546">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="89491-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="89491-547">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="89491-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="89491-548">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="89491-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="89491-549">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89491-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="89491-550">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="89491-551">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="89491-552">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="89491-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="89491-553">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="89491-554">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="89491-555">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="89491-556">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="89491-557">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="89491-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="89491-558">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="89491-558">The Client ID for this project.</span></span> <span data-ttu-id="89491-559">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="89491-560">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="89491-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="89491-561">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="89491-561">The domain for the directory tenant.</span></span> <span data-ttu-id="89491-562">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="89491-563">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="89491-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="89491-564">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="89491-565">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="89491-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="89491-566">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="89491-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="89491-567">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="89491-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="89491-568">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="89491-569">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="89491-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="89491-570">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="89491-570">Turns off HTTPS.</span></span> <span data-ttu-id="89491-571">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="89491-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="89491-572">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89491-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="89491-573">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="89491-574">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="89491-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="89491-575">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="89491-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="89491-576">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="89491-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="89491-577">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="89491-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="89491-578">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="89491-578">SDK version</span></span> | <span data-ttu-id="89491-579">Standardwert</span><span class="sxs-lookup"><span data-stu-id="89491-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="89491-580">3.1</span><span class="sxs-lookup"><span data-stu-id="89491-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="89491-581">3.0</span><span class="sxs-lookup"><span data-stu-id="89491-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="89491-582">2.1</span><span class="sxs-lookup"><span data-stu-id="89491-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="89491-583">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="89491-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="89491-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="89491-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="89491-585">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="89491-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="89491-586">Beispiele</span><span class="sxs-lookup"><span data-stu-id="89491-586">Examples</span></span>

- <span data-ttu-id="89491-587">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="89491-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="89491-588">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="89491-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="89491-589">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="89491-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="89491-590">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="89491-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="89491-591">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="89491-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="89491-592">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="89491-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="89491-593">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="89491-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="89491-594">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="89491-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="89491-595">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="89491-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="89491-596">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="89491-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="89491-597">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="89491-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="89491-598">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="89491-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="89491-599">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="89491-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="89491-600">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89491-600">See also</span></span>

- [<span data-ttu-id="89491-601">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="89491-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="89491-602">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="89491-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="89491-603">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="89491-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="89491-604">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="89491-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
