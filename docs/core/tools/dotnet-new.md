---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/01/2020
ms.openlocfilehash: 4a4c8e2806fee663b5f6aa255a6f24250a072a85
ms.sourcegitcommit: 532b03d5bbab764d63356193b04cd2281bc01239
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2020
ms.locfileid: "92526609"
---
# <a name="dotnet-new"></a><span data-ttu-id="43d27-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="43d27-103">dotnet new</span></span>

<span data-ttu-id="43d27-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="43d27-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="43d27-105">name</span><span class="sxs-lookup"><span data-stu-id="43d27-105">Name</span></span>

<span data-ttu-id="43d27-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="43d27-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="43d27-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="43d27-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="43d27-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43d27-108">Description</span></span>

<span data-ttu-id="43d27-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="43d27-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="43d27-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="43d27-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="43d27-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="43d27-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="43d27-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="43d27-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="43d27-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="43d27-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="43d27-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="43d27-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="43d27-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="43d27-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="43d27-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="43d27-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="43d27-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="43d27-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="43d27-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="43d27-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="43d27-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="43d27-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="43d27-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="43d27-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="43d27-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="43d27-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="43d27-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="43d27-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="43d27-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d27-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="43d27-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="43d27-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="43d27-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="43d27-125">Templates</span></span>                                    | <span data-ttu-id="43d27-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="43d27-126">Short name</span></span>                      | <span data-ttu-id="43d27-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="43d27-127">Language</span></span>     | <span data-ttu-id="43d27-128">Tags</span><span class="sxs-lookup"><span data-stu-id="43d27-128">Tags</span></span>                                  | <span data-ttu-id="43d27-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="43d27-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="43d27-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="43d27-130">Console Application</span></span>                          | [<span data-ttu-id="43d27-131">console</span><span class="sxs-lookup"><span data-stu-id="43d27-131">console</span></span>](#console)             | <span data-ttu-id="43d27-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="43d27-132">[C#], F#, VB</span></span> | <span data-ttu-id="43d27-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="43d27-133">Common/Console</span></span>                        | <span data-ttu-id="43d27-134">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-134">1.0</span></span>        |
| <span data-ttu-id="43d27-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="43d27-135">Class library</span></span>                                | [<span data-ttu-id="43d27-136">classlib</span><span class="sxs-lookup"><span data-stu-id="43d27-136">classlib</span></span>](#classlib)           | <span data-ttu-id="43d27-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="43d27-137">[C#], F#, VB</span></span> | <span data-ttu-id="43d27-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="43d27-138">Common/Library</span></span>                        | <span data-ttu-id="43d27-139">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-139">1.0</span></span>        |
| <span data-ttu-id="43d27-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="43d27-140">WPF Application</span></span>                              | [<span data-ttu-id="43d27-141">wpf</span><span class="sxs-lookup"><span data-stu-id="43d27-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="43d27-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="43d27-142">[C#], VB</span></span>     | <span data-ttu-id="43d27-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="43d27-143">Common/WPF</span></span>                            | <span data-ttu-id="43d27-144">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="43d27-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="43d27-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="43d27-145">WPF Class library</span></span>                            | [<span data-ttu-id="43d27-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="43d27-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="43d27-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="43d27-147">[C#], VB</span></span>     | <span data-ttu-id="43d27-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="43d27-148">Common/WPF</span></span>                            | <span data-ttu-id="43d27-149">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="43d27-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="43d27-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="43d27-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="43d27-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="43d27-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="43d27-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="43d27-152">[C#], VB</span></span>     | <span data-ttu-id="43d27-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="43d27-153">Common/WPF</span></span>                            | <span data-ttu-id="43d27-154">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="43d27-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="43d27-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="43d27-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="43d27-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="43d27-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="43d27-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="43d27-157">[C#], VB</span></span>     | <span data-ttu-id="43d27-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="43d27-158">Common/WPF</span></span>                            | <span data-ttu-id="43d27-159">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="43d27-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="43d27-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="43d27-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="43d27-161">winforms</span><span class="sxs-lookup"><span data-stu-id="43d27-161">winforms</span></span>](#winforms)           | <span data-ttu-id="43d27-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="43d27-162">[C#], VB</span></span>     | <span data-ttu-id="43d27-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="43d27-163">Common/WinForms</span></span>                       | <span data-ttu-id="43d27-164">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="43d27-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="43d27-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="43d27-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="43d27-166">winforms</span><span class="sxs-lookup"><span data-stu-id="43d27-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="43d27-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="43d27-167">[C#], VB</span></span>     | <span data-ttu-id="43d27-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="43d27-168">Common/WinForms</span></span>                       | <span data-ttu-id="43d27-169">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="43d27-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="43d27-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="43d27-170">Worker Service</span></span>                               | [<span data-ttu-id="43d27-171">worker</span><span class="sxs-lookup"><span data-stu-id="43d27-171">worker</span></span>](#web-others)           | <span data-ttu-id="43d27-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-172">[C#]</span></span>         | <span data-ttu-id="43d27-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="43d27-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="43d27-174">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-174">3.0</span></span>        |
| <span data-ttu-id="43d27-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="43d27-175">Unit Test Project</span></span>                            | [<span data-ttu-id="43d27-176">mstest</span><span class="sxs-lookup"><span data-stu-id="43d27-176">mstest</span></span>](#test)                 | <span data-ttu-id="43d27-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="43d27-177">[C#], F#, VB</span></span> | <span data-ttu-id="43d27-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="43d27-178">Test/MSTest</span></span>                           | <span data-ttu-id="43d27-179">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-179">1.0</span></span>        |
| <span data-ttu-id="43d27-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="43d27-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="43d27-181">nunit</span><span class="sxs-lookup"><span data-stu-id="43d27-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="43d27-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="43d27-182">[C#], F#, VB</span></span> | <span data-ttu-id="43d27-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="43d27-183">Test/NUnit</span></span>                            | <span data-ttu-id="43d27-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="43d27-184">2.1.400</span></span>    |
| <span data-ttu-id="43d27-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="43d27-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="43d27-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="43d27-186">[C#], F#, VB</span></span> | <span data-ttu-id="43d27-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="43d27-187">Test/NUnit</span></span>                            | <span data-ttu-id="43d27-188">2.2</span><span class="sxs-lookup"><span data-stu-id="43d27-188">2.2</span></span>        |
| <span data-ttu-id="43d27-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="43d27-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="43d27-190">xunit</span><span class="sxs-lookup"><span data-stu-id="43d27-190">xunit</span></span>](#test)                  | <span data-ttu-id="43d27-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="43d27-191">[C#], F#, VB</span></span> | <span data-ttu-id="43d27-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="43d27-192">Test/xUnit</span></span>                            | <span data-ttu-id="43d27-193">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-193">1.0</span></span>        |
| <span data-ttu-id="43d27-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="43d27-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="43d27-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-195">[C#]</span></span>         | <span data-ttu-id="43d27-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43d27-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="43d27-197">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-197">3.0</span></span>        |
| <span data-ttu-id="43d27-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="43d27-198">Razor Page</span></span>                                   | [<span data-ttu-id="43d27-199">page</span><span class="sxs-lookup"><span data-stu-id="43d27-199">page</span></span>](#page)                   | <span data-ttu-id="43d27-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-200">[C#]</span></span>         | <span data-ttu-id="43d27-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43d27-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="43d27-202">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-202">2.0</span></span>        |
| <span data-ttu-id="43d27-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="43d27-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="43d27-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="43d27-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="43d27-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-205">[C#]</span></span>         | <span data-ttu-id="43d27-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43d27-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="43d27-207">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-207">2.0</span></span>        |
| <span data-ttu-id="43d27-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="43d27-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="43d27-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-209">[C#]</span></span>         | <span data-ttu-id="43d27-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="43d27-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="43d27-211">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-211">2.0</span></span>        |
| <span data-ttu-id="43d27-212">:::no-loc(Blazor)::: Server-App</span><span class="sxs-lookup"><span data-stu-id="43d27-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="43d27-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="43d27-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="43d27-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-214">[C#]</span></span>         | <span data-ttu-id="43d27-215">Web/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="43d27-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="43d27-216">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-216">3.0</span></span>        |
| <span data-ttu-id="43d27-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly):::-App</span><span class="sxs-lookup"><span data-stu-id="43d27-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="43d27-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-218">[C#]</span></span>         | <span data-ttu-id="43d27-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="43d27-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="43d27-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="43d27-220">3.1.300</span></span>    |
| <span data-ttu-id="43d27-221">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="43d27-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="43d27-222">web</span><span class="sxs-lookup"><span data-stu-id="43d27-222">web</span></span>](#web)                     | <span data-ttu-id="43d27-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="43d27-223">[C#], F#</span></span>     | <span data-ttu-id="43d27-224">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="43d27-224">Web/Empty</span></span>                             | <span data-ttu-id="43d27-225">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-225">1.0</span></span>        |
| <span data-ttu-id="43d27-226">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="43d27-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="43d27-227">mvc</span><span class="sxs-lookup"><span data-stu-id="43d27-227">mvc</span></span>](#web-options)             | <span data-ttu-id="43d27-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="43d27-228">[C#], F#</span></span>     | <span data-ttu-id="43d27-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="43d27-229">Web/MVC</span></span>                               | <span data-ttu-id="43d27-230">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-230">1.0</span></span>        |
| <span data-ttu-id="43d27-231">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="43d27-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="43d27-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="43d27-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="43d27-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-233">[C#]</span></span>         | <span data-ttu-id="43d27-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="43d27-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="43d27-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="43d27-236">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="43d27-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="43d27-237">angular</span><span class="sxs-lookup"><span data-stu-id="43d27-237">angular</span></span>](#spa)                 | <span data-ttu-id="43d27-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-238">[C#]</span></span>         | <span data-ttu-id="43d27-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="43d27-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="43d27-240">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-240">2.0</span></span>        |
| <span data-ttu-id="43d27-241">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="43d27-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="43d27-242">react</span><span class="sxs-lookup"><span data-stu-id="43d27-242">react</span></span>](#spa)                   | <span data-ttu-id="43d27-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-243">[C#]</span></span>         | <span data-ttu-id="43d27-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="43d27-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="43d27-245">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-245">2.0</span></span>        |
| <span data-ttu-id="43d27-246">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="43d27-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="43d27-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="43d27-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="43d27-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-248">[C#]</span></span>         | <span data-ttu-id="43d27-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="43d27-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="43d27-250">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-250">2.0</span></span>        |
| <span data-ttu-id="43d27-251">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="43d27-251">Razor Class Library</span></span>                          | [<span data-ttu-id="43d27-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="43d27-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="43d27-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-253">[C#]</span></span>         | <span data-ttu-id="43d27-254">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="43d27-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="43d27-255">2.1</span><span class="sxs-lookup"><span data-stu-id="43d27-255">2.1</span></span>        |
| <span data-ttu-id="43d27-256">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="43d27-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="43d27-257">webapi</span><span class="sxs-lookup"><span data-stu-id="43d27-257">webapi</span></span>](#webapi)               | <span data-ttu-id="43d27-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="43d27-258">[C#], F#</span></span>     | <span data-ttu-id="43d27-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="43d27-259">Web/WebAPI</span></span>                            | <span data-ttu-id="43d27-260">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-260">1.0</span></span>        |
| <span data-ttu-id="43d27-261">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="43d27-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="43d27-262">grpc</span><span class="sxs-lookup"><span data-stu-id="43d27-262">grpc</span></span>](#web-others)             | <span data-ttu-id="43d27-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="43d27-263">[C#]</span></span>         | <span data-ttu-id="43d27-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="43d27-264">Web/gRPC</span></span>                              | <span data-ttu-id="43d27-265">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-265">3.0</span></span>        |
| <span data-ttu-id="43d27-266">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="43d27-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="43d27-267">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="43d27-267">Config</span></span>                                | <span data-ttu-id="43d27-268">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-268">3.0</span></span>        |
| <span data-ttu-id="43d27-269">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="43d27-269">global.json file</span></span>                             | [<span data-ttu-id="43d27-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="43d27-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="43d27-271">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="43d27-271">Config</span></span>                                | <span data-ttu-id="43d27-272">2.0</span><span class="sxs-lookup"><span data-stu-id="43d27-272">2.0</span></span>        |
| <span data-ttu-id="43d27-273">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="43d27-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="43d27-274">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="43d27-274">Config</span></span>                                | <span data-ttu-id="43d27-275">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-275">1.0</span></span>        |
| <span data-ttu-id="43d27-276">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="43d27-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="43d27-277">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="43d27-277">Config</span></span>                                | <span data-ttu-id="43d27-278">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-278">3.0</span></span>        |
| <span data-ttu-id="43d27-279">Web Config</span><span class="sxs-lookup"><span data-stu-id="43d27-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="43d27-280">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="43d27-280">Config</span></span>                                | <span data-ttu-id="43d27-281">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-281">1.0</span></span>        |
| <span data-ttu-id="43d27-282">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="43d27-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="43d27-283">Lösung</span><span class="sxs-lookup"><span data-stu-id="43d27-283">Solution</span></span>                              | <span data-ttu-id="43d27-284">1.0</span><span class="sxs-lookup"><span data-stu-id="43d27-284">1.0</span></span>        |
| <span data-ttu-id="43d27-285">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="43d27-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="43d27-286">proto</span><span class="sxs-lookup"><span data-stu-id="43d27-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="43d27-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="43d27-287">Web/gRPC</span></span>                              | <span data-ttu-id="43d27-288">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="43d27-289">Optionen</span><span class="sxs-lookup"><span data-stu-id="43d27-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="43d27-290">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="43d27-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="43d27-291">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="43d27-292">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="43d27-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="43d27-293">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="43d27-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="43d27-294">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="43d27-294">Prints out help for the command.</span></span> <span data-ttu-id="43d27-295">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="43d27-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="43d27-296">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="43d27-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="43d27-297">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="43d27-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="43d27-298">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="43d27-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="43d27-299">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="43d27-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="43d27-300">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="43d27-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="43d27-301">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="43d27-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="43d27-302">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="43d27-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="43d27-303">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="43d27-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="43d27-304">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="43d27-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="43d27-305">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="43d27-305">The language of the template to create.</span></span> <span data-ttu-id="43d27-306">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="43d27-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="43d27-307">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="43d27-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="43d27-308">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="43d27-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="43d27-309">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="43d27-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="43d27-310">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="43d27-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="43d27-311">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="43d27-311">The name for the created output.</span></span> <span data-ttu-id="43d27-312">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="43d27-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="43d27-313">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="43d27-314">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="43d27-315">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="43d27-315">Location to place the generated output.</span></span> <span data-ttu-id="43d27-316">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="43d27-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="43d27-317">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="43d27-317">Filters templates based on available types.</span></span> <span data-ttu-id="43d27-318">Bei `project` und `item` handelt es sich um vordefinierte Werte.</span><span class="sxs-lookup"><span data-stu-id="43d27-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="43d27-319">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="43d27-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="43d27-320">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="43d27-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="43d27-321">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="43d27-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="43d27-322">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="43d27-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="43d27-323">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="43d27-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="43d27-324">Beispielsweise funktioniert zwar *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* , jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="43d27-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="43d27-325">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="43d27-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="43d27-326">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="43d27-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="43d27-327">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="43d27-328">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="43d27-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="43d27-329">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="43d27-330">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="43d27-330">Template options</span></span>

<span data-ttu-id="43d27-331">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="43d27-331">Each project template may have additional options available.</span></span> <span data-ttu-id="43d27-332">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="43d27-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="43d27-333">Konsole</span><span class="sxs-lookup"><span data-stu-id="43d27-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="43d27-334">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-335">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="43d27-336">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-337">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-337">SDK version</span></span> | <span data-ttu-id="43d27-338">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-339">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-340">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="43d27-341">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="43d27-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="43d27-342">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="43d27-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="43d27-343">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43d27-343">Not supported for F#.</span></span> <span data-ttu-id="43d27-344">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="43d27-345">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="43d27-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-346">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="43d27-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="43d27-347">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-347">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="43d27-348">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-348">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="43d27-349">classlib</span><span class="sxs-lookup"><span data-stu-id="43d27-349">classlib</span></span>

- <span data-ttu-id="43d27-350">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-350">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="43d27-351">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-351">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-352">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="43d27-352">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="43d27-353">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="43d27-353">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="43d27-354">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="43d27-354">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="43d27-355">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="43d27-355">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="43d27-356">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43d27-356">Not supported for F#.</span></span> <span data-ttu-id="43d27-357">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-357">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="43d27-358">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="43d27-358">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-359">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-359">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-360">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-360">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="43d27-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="43d27-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="43d27-362">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-362">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="43d27-363">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-363">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-364">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="43d27-364">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="43d27-365">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-365">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="43d27-366">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="43d27-366">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="43d27-367">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="43d27-367">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="43d27-368">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="43d27-368">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-369">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-369">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-370">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-370">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="43d27-371">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="43d27-371">winforms, winformslib</span></span>

- <span data-ttu-id="43d27-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="43d27-373">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="43d27-373">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="43d27-374">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="43d27-374">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="43d27-375">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="43d27-375">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-376">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-376">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-377">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-377">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="43d27-378">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="43d27-378">worker, grpc</span></span>

- <span data-ttu-id="43d27-379">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-379">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="43d27-380">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-380">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-381">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="43d27-381">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="43d27-382">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-382">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="43d27-383">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-383">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-384">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-384">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-385">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-385">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="43d27-386">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="43d27-386">mstest, xunit</span></span>

- <span data-ttu-id="43d27-387">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-387">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="43d27-388">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-389">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-389">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="43d27-390">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-390">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-391">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-391">SDK version</span></span> | <span data-ttu-id="43d27-392">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-392">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-393">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-393">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-394">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-394">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="43d27-395">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="43d27-395">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-396">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-396">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-397">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-397">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="43d27-398">nunit</span><span class="sxs-lookup"><span data-stu-id="43d27-398">nunit</span></span>

- <span data-ttu-id="43d27-399">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-399">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="43d27-400">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-400">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="43d27-401">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-401">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-402">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-402">SDK version</span></span> | <span data-ttu-id="43d27-403">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-403">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-404">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-404">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-405">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-405">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="43d27-406">2.2</span><span class="sxs-lookup"><span data-stu-id="43d27-406">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="43d27-407">2.1</span><span class="sxs-lookup"><span data-stu-id="43d27-407">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="43d27-408">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="43d27-408">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-409">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-409">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-410">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-410">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="43d27-411">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="43d27-411">page</span></span>

- <span data-ttu-id="43d27-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="43d27-413">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="43d27-413">Namespace for the generated code.</span></span> <span data-ttu-id="43d27-414">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="43d27-414">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="43d27-415">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="43d27-415">Creates the page without a PageModel.</span></span>

<span data-ttu-id="43d27-416">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-416">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="43d27-417">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="43d27-417">viewimports, proto</span></span>

- <span data-ttu-id="43d27-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="43d27-419">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="43d27-419">Namespace for the generated code.</span></span> <span data-ttu-id="43d27-420">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="43d27-420">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="43d27-421">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-421">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="43d27-422">blazorserver</span><span class="sxs-lookup"><span data-stu-id="43d27-422">blazorserver</span></span>

- <span data-ttu-id="43d27-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="43d27-424">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="43d27-424">The type of authentication to use.</span></span> <span data-ttu-id="43d27-425">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="43d27-425">The possible values are:</span></span>

  - <span data-ttu-id="43d27-426">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="43d27-426">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="43d27-427">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43d27-427">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="43d27-428">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="43d27-428">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="43d27-429">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="43d27-429">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="43d27-430">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="43d27-430">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="43d27-431">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43d27-431">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="43d27-432">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-432">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="43d27-433">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-433">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-434">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="43d27-434">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="43d27-435">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-435">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="43d27-436">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-436">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="43d27-437">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-437">The reset password policy ID for this project.</span></span> <span data-ttu-id="43d27-438">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-438">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="43d27-439">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-439">The edit profile policy ID for this project.</span></span> <span data-ttu-id="43d27-440">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-440">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="43d27-441">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-441">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="43d27-442">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-442">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="43d27-443">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="43d27-443">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="43d27-444">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-444">The Client ID for this project.</span></span> <span data-ttu-id="43d27-445">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-445">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="43d27-446">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="43d27-446">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="43d27-447">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="43d27-447">The domain for the directory tenant.</span></span> <span data-ttu-id="43d27-448">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-448">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-449">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="43d27-449">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="43d27-450">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-450">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="43d27-451">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-451">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="43d27-452">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="43d27-452">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="43d27-453">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="43d27-453">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="43d27-454">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-454">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-455">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="43d27-455">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="43d27-456">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="43d27-456">Allows this application read-access to the directory.</span></span> <span data-ttu-id="43d27-457">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-457">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="43d27-458">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-458">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="43d27-459">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43d27-459">Turns off HTTPS.</span></span> <span data-ttu-id="43d27-460">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43d27-460">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="43d27-461">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-461">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="43d27-462">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-462">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-463">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-463">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-464">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-464">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="43d27-465">Web-</span><span class="sxs-lookup"><span data-stu-id="43d27-465">web</span></span>

- <span data-ttu-id="43d27-466">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-466">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="43d27-467">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-467">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="43d27-468">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-469">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-469">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="43d27-470">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-470">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-471">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-471">SDK version</span></span> | <span data-ttu-id="43d27-472">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-472">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-473">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-473">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-474">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-474">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="43d27-475">2.1</span><span class="sxs-lookup"><span data-stu-id="43d27-475">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="43d27-476">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="43d27-477">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43d27-477">Turns off HTTPS.</span></span>

<span data-ttu-id="43d27-478">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-478">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="43d27-479">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="43d27-479">mvc, webapp</span></span>

- <span data-ttu-id="43d27-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="43d27-481">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="43d27-481">The type of authentication to use.</span></span> <span data-ttu-id="43d27-482">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="43d27-482">The possible values are:</span></span>

  - <span data-ttu-id="43d27-483">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="43d27-483">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="43d27-484">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43d27-484">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="43d27-485">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="43d27-485">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="43d27-486">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="43d27-486">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="43d27-487">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="43d27-487">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="43d27-488">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43d27-488">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="43d27-489">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-489">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="43d27-490">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-490">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-491">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="43d27-491">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="43d27-492">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-492">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="43d27-493">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-493">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="43d27-494">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-494">The reset password policy ID for this project.</span></span> <span data-ttu-id="43d27-495">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-495">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="43d27-496">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-496">The edit profile policy ID for this project.</span></span> <span data-ttu-id="43d27-497">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-497">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="43d27-498">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-498">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="43d27-499">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-499">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="43d27-500">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="43d27-500">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="43d27-501">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-501">The Client ID for this project.</span></span> <span data-ttu-id="43d27-502">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-502">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="43d27-503">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="43d27-503">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="43d27-504">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="43d27-504">The domain for the directory tenant.</span></span> <span data-ttu-id="43d27-505">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-506">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="43d27-506">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="43d27-507">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-507">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="43d27-508">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-508">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="43d27-509">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="43d27-509">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="43d27-510">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="43d27-510">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="43d27-511">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-511">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-512">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="43d27-512">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="43d27-513">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="43d27-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="43d27-514">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-514">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="43d27-515">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="43d27-516">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43d27-516">Turns off HTTPS.</span></span> <span data-ttu-id="43d27-517">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43d27-517">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="43d27-518">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="43d27-519">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="43d27-520">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-521">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-521">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="43d27-522">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-523">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-523">SDK version</span></span> | <span data-ttu-id="43d27-524">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-525">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-526">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-526">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="43d27-527">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-527">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="43d27-528">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="43d27-528">Includes BrowserLink in the project.</span></span> <span data-ttu-id="43d27-529">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-529">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="43d27-530">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="43d27-530">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="43d27-531">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-531">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="43d27-532">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-532">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="43d27-533">angular, react</span><span class="sxs-lookup"><span data-stu-id="43d27-533">angular, react</span></span>

- <span data-ttu-id="43d27-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="43d27-535">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="43d27-535">The type of authentication to use.</span></span> <span data-ttu-id="43d27-536">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-536">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="43d27-537">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="43d27-537">The possible values are:</span></span>

  - <span data-ttu-id="43d27-538">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="43d27-538">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="43d27-539">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43d27-539">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="43d27-540">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-540">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="43d27-541">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="43d27-542">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43d27-542">Turns off HTTPS.</span></span> <span data-ttu-id="43d27-543">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="43d27-543">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="43d27-544">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-544">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="43d27-545">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-545">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-546">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-546">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="43d27-547">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-547">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-548">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-548">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="43d27-549">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-549">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-550">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-550">SDK version</span></span> | <span data-ttu-id="43d27-551">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-551">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-552">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-552">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-553">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-553">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="43d27-554">2.1</span><span class="sxs-lookup"><span data-stu-id="43d27-554">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="43d27-555">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-555">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="43d27-556">reactredux</span><span class="sxs-lookup"><span data-stu-id="43d27-556">reactredux</span></span>

- <span data-ttu-id="43d27-557">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-557">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="43d27-558">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-558">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="43d27-559">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-559">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-560">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-560">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="43d27-561">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-561">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-562">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-562">SDK version</span></span> | <span data-ttu-id="43d27-563">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-563">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-564">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-564">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-565">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-565">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="43d27-566">2.1</span><span class="sxs-lookup"><span data-stu-id="43d27-566">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="43d27-567">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-567">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="43d27-568">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43d27-568">Turns off HTTPS.</span></span>

<span data-ttu-id="43d27-569">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-569">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="43d27-570">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="43d27-570">razorclasslib</span></span>

- <span data-ttu-id="43d27-571">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-571">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="43d27-572">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-572">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="43d27-573">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="43d27-573">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="43d27-574">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="43d27-574">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="43d27-575">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-575">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="43d27-576">Web-API</span><span class="sxs-lookup"><span data-stu-id="43d27-576">webapi</span></span>

- <span data-ttu-id="43d27-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="43d27-578">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="43d27-578">The type of authentication to use.</span></span> <span data-ttu-id="43d27-579">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="43d27-579">The possible values are:</span></span>

  - <span data-ttu-id="43d27-580">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="43d27-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="43d27-581">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="43d27-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="43d27-582">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="43d27-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="43d27-583">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="43d27-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="43d27-584">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="43d27-585">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="43d27-586">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="43d27-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="43d27-587">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="43d27-588">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="43d27-589">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="43d27-590">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="43d27-591">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="43d27-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="43d27-592">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="43d27-592">The Client ID for this project.</span></span> <span data-ttu-id="43d27-593">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="43d27-594">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="43d27-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="43d27-595">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="43d27-595">The domain for the directory tenant.</span></span> <span data-ttu-id="43d27-596">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="43d27-597">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="43d27-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="43d27-598">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="43d27-599">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="43d27-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="43d27-600">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="43d27-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="43d27-601">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="43d27-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="43d27-602">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="43d27-603">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="43d27-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="43d27-604">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="43d27-604">Turns off HTTPS.</span></span> <span data-ttu-id="43d27-605">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="43d27-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="43d27-606">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43d27-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="43d27-607">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="43d27-608">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="43d27-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="43d27-609">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="43d27-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="43d27-610">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="43d27-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="43d27-611">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="43d27-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="43d27-612">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="43d27-612">SDK version</span></span> | <span data-ttu-id="43d27-613">Standardwert</span><span class="sxs-lookup"><span data-stu-id="43d27-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="43d27-614">3.1</span><span class="sxs-lookup"><span data-stu-id="43d27-614">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="43d27-615">3.0</span><span class="sxs-lookup"><span data-stu-id="43d27-615">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="43d27-616">2.1</span><span class="sxs-lookup"><span data-stu-id="43d27-616">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="43d27-617">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="43d27-617">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="43d27-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="43d27-618">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="43d27-619">globaljson</span><span class="sxs-lookup"><span data-stu-id="43d27-619">globaljson</span></span>

- <span data-ttu-id="43d27-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="43d27-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="43d27-621">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="43d27-621">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="43d27-622">Beispiele</span><span class="sxs-lookup"><span data-stu-id="43d27-622">Examples</span></span>

- <span data-ttu-id="43d27-623">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="43d27-623">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="43d27-624">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="43d27-624">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="43d27-625">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="43d27-625">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="43d27-626">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="43d27-626">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="43d27-627">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="43d27-627">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="43d27-628">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="43d27-628">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="43d27-629">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="43d27-629">List all templates matching the *we* substring.</span></span> <span data-ttu-id="43d27-630">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="43d27-630">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="43d27-631">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="43d27-631">Attempt to invoke the template matching *ng* .</span></span> <span data-ttu-id="43d27-632">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="43d27-632">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="43d27-633">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="43d27-633">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="43d27-634">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="43d27-634">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="43d27-635">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json* , und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="43d27-635">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="43d27-636">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43d27-636">See also</span></span>

- [<span data-ttu-id="43d27-637">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="43d27-637">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="43d27-638">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="43d27-638">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="43d27-639">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="43d27-639">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="43d27-640">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="43d27-640">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
