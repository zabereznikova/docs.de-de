---
title: Befehl „dotnet new“
description: Der Befehl „dotnet new“ erstellt neue .NET-Projekte auf Basis der angegebenen Vorlage.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634454"
---
# <a name="dotnet-new"></a><span data-ttu-id="fe86a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="fe86a-103">dotnet new</span></span>

<span data-ttu-id="fe86a-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="fe86a-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="fe86a-105">name</span><span class="sxs-lookup"><span data-stu-id="fe86a-105">Name</span></span>

<span data-ttu-id="fe86a-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fe86a-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="fe86a-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="fe86a-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="fe86a-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe86a-108">Description</span></span>

<span data-ttu-id="fe86a-109">Der Befehl `dotnet new` erstellt ein .NET-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fe86a-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="fe86a-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="fe86a-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="fe86a-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="fe86a-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="fe86a-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="fe86a-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="fe86a-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fe86a-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="fe86a-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="fe86a-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="fe86a-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="fe86a-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="fe86a-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="fe86a-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="fe86a-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="fe86a-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="fe86a-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="fe86a-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="fe86a-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="fe86a-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="fe86a-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="fe86a-122">Die folgende Tabelle zeigt die Vorlagen, die im Lieferumfang des .NET SDK enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="fe86a-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="fe86a-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="fe86a-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="fe86a-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="fe86a-125">Templates</span></span>                                    | <span data-ttu-id="fe86a-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="fe86a-126">Short name</span></span>                      | <span data-ttu-id="fe86a-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="fe86a-127">Language</span></span>     | <span data-ttu-id="fe86a-128">Tags</span><span class="sxs-lookup"><span data-stu-id="fe86a-128">Tags</span></span>                                  | <span data-ttu-id="fe86a-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="fe86a-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="fe86a-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="fe86a-130">Console Application</span></span>                          | [<span data-ttu-id="fe86a-131">console</span><span class="sxs-lookup"><span data-stu-id="fe86a-131">console</span></span>](#console)             | <span data-ttu-id="fe86a-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-132">[C#], F#, VB</span></span> | <span data-ttu-id="fe86a-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="fe86a-133">Common/Console</span></span>                        | <span data-ttu-id="fe86a-134">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-134">1.0</span></span>        |
| <span data-ttu-id="fe86a-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="fe86a-135">Class library</span></span>                                | [<span data-ttu-id="fe86a-136">classlib</span><span class="sxs-lookup"><span data-stu-id="fe86a-136">classlib</span></span>](#classlib)           | <span data-ttu-id="fe86a-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-137">[C#], F#, VB</span></span> | <span data-ttu-id="fe86a-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="fe86a-138">Common/Library</span></span>                        | <span data-ttu-id="fe86a-139">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-139">1.0</span></span>        |
| <span data-ttu-id="fe86a-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="fe86a-140">WPF Application</span></span>                              | [<span data-ttu-id="fe86a-141">wpf</span><span class="sxs-lookup"><span data-stu-id="fe86a-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="fe86a-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-142">[C#], VB</span></span>     | <span data-ttu-id="fe86a-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="fe86a-143">Common/WPF</span></span>                            | <span data-ttu-id="fe86a-144">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="fe86a-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fe86a-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="fe86a-145">WPF Class library</span></span>                            | [<span data-ttu-id="fe86a-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="fe86a-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="fe86a-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-147">[C#], VB</span></span>     | <span data-ttu-id="fe86a-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="fe86a-148">Common/WPF</span></span>                            | <span data-ttu-id="fe86a-149">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="fe86a-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fe86a-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="fe86a-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="fe86a-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="fe86a-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="fe86a-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-152">[C#], VB</span></span>     | <span data-ttu-id="fe86a-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="fe86a-153">Common/WPF</span></span>                            | <span data-ttu-id="fe86a-154">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="fe86a-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fe86a-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="fe86a-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="fe86a-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="fe86a-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="fe86a-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-157">[C#], VB</span></span>     | <span data-ttu-id="fe86a-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="fe86a-158">Common/WPF</span></span>                            | <span data-ttu-id="fe86a-159">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="fe86a-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fe86a-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="fe86a-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="fe86a-161">winforms</span><span class="sxs-lookup"><span data-stu-id="fe86a-161">winforms</span></span>](#winforms)           | <span data-ttu-id="fe86a-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-162">[C#], VB</span></span>     | <span data-ttu-id="fe86a-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="fe86a-163">Common/WinForms</span></span>                       | <span data-ttu-id="fe86a-164">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="fe86a-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fe86a-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="fe86a-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="fe86a-166">winforms</span><span class="sxs-lookup"><span data-stu-id="fe86a-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="fe86a-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-167">[C#], VB</span></span>     | <span data-ttu-id="fe86a-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="fe86a-168">Common/WinForms</span></span>                       | <span data-ttu-id="fe86a-169">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="fe86a-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="fe86a-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="fe86a-170">Worker Service</span></span>                               | [<span data-ttu-id="fe86a-171">worker</span><span class="sxs-lookup"><span data-stu-id="fe86a-171">worker</span></span>](#web-others)           | <span data-ttu-id="fe86a-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-172">[C#]</span></span>         | <span data-ttu-id="fe86a-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="fe86a-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="fe86a-174">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-174">3.0</span></span>        |
| <span data-ttu-id="fe86a-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="fe86a-175">Unit Test Project</span></span>                            | [<span data-ttu-id="fe86a-176">mstest</span><span class="sxs-lookup"><span data-stu-id="fe86a-176">mstest</span></span>](#test)                 | <span data-ttu-id="fe86a-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-177">[C#], F#, VB</span></span> | <span data-ttu-id="fe86a-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="fe86a-178">Test/MSTest</span></span>                           | <span data-ttu-id="fe86a-179">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-179">1.0</span></span>        |
| <span data-ttu-id="fe86a-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="fe86a-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="fe86a-181">nunit</span><span class="sxs-lookup"><span data-stu-id="fe86a-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="fe86a-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-182">[C#], F#, VB</span></span> | <span data-ttu-id="fe86a-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="fe86a-183">Test/NUnit</span></span>                            | <span data-ttu-id="fe86a-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="fe86a-184">2.1.400</span></span>    |
| <span data-ttu-id="fe86a-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="fe86a-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="fe86a-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-186">[C#], F#, VB</span></span> | <span data-ttu-id="fe86a-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="fe86a-187">Test/NUnit</span></span>                            | <span data-ttu-id="fe86a-188">2.2</span><span class="sxs-lookup"><span data-stu-id="fe86a-188">2.2</span></span>        |
| <span data-ttu-id="fe86a-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="fe86a-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="fe86a-190">xunit</span><span class="sxs-lookup"><span data-stu-id="fe86a-190">xunit</span></span>](#test)                  | <span data-ttu-id="fe86a-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="fe86a-191">[C#], F#, VB</span></span> | <span data-ttu-id="fe86a-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="fe86a-192">Test/xUnit</span></span>                            | <span data-ttu-id="fe86a-193">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-193">1.0</span></span>        |
| <span data-ttu-id="fe86a-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="fe86a-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="fe86a-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-195">[C#]</span></span>         | <span data-ttu-id="fe86a-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fe86a-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="fe86a-197">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-197">3.0</span></span>        |
| <span data-ttu-id="fe86a-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="fe86a-198">Razor Page</span></span>                                   | [<span data-ttu-id="fe86a-199">page</span><span class="sxs-lookup"><span data-stu-id="fe86a-199">page</span></span>](#page)                   | <span data-ttu-id="fe86a-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-200">[C#]</span></span>         | <span data-ttu-id="fe86a-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fe86a-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="fe86a-202">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-202">2.0</span></span>        |
| <span data-ttu-id="fe86a-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="fe86a-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="fe86a-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="fe86a-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="fe86a-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-205">[C#]</span></span>         | <span data-ttu-id="fe86a-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fe86a-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="fe86a-207">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-207">2.0</span></span>        |
| <span data-ttu-id="fe86a-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="fe86a-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="fe86a-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-209">[C#]</span></span>         | <span data-ttu-id="fe86a-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="fe86a-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="fe86a-211">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-211">2.0</span></span>        |
| <span data-ttu-id="fe86a-212">Blazor Server-App</span><span class="sxs-lookup"><span data-stu-id="fe86a-212">Blazor Server App</span></span>                            | [<span data-ttu-id="fe86a-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="fe86a-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="fe86a-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-214">[C#]</span></span>         | <span data-ttu-id="fe86a-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="fe86a-215">Web/Blazor</span></span>                            | <span data-ttu-id="fe86a-216">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-216">3.0</span></span>        |
| <span data-ttu-id="fe86a-217">Blazor WebAssembly-App</span><span class="sxs-lookup"><span data-stu-id="fe86a-217">Blazor WebAssembly App</span></span>                       | [<span data-ttu-id="fe86a-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="fe86a-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="fe86a-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-219">[C#]</span></span>         | <span data-ttu-id="fe86a-220">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="fe86a-220">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="fe86a-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="fe86a-221">3.1.300</span></span>    |
| <span data-ttu-id="fe86a-222">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="fe86a-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="fe86a-223">web</span><span class="sxs-lookup"><span data-stu-id="fe86a-223">web</span></span>](#web)                     | <span data-ttu-id="fe86a-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fe86a-224">[C#], F#</span></span>     | <span data-ttu-id="fe86a-225">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="fe86a-225">Web/Empty</span></span>                             | <span data-ttu-id="fe86a-226">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-226">1.0</span></span>        |
| <span data-ttu-id="fe86a-227">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="fe86a-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="fe86a-228">mvc</span><span class="sxs-lookup"><span data-stu-id="fe86a-228">mvc</span></span>](#web-options)             | <span data-ttu-id="fe86a-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fe86a-229">[C#], F#</span></span>     | <span data-ttu-id="fe86a-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="fe86a-230">Web/MVC</span></span>                               | <span data-ttu-id="fe86a-231">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-231">1.0</span></span>        |
| <span data-ttu-id="fe86a-232">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="fe86a-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="fe86a-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="fe86a-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="fe86a-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-234">[C#]</span></span>         | <span data-ttu-id="fe86a-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="fe86a-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="fe86a-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="fe86a-237">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="fe86a-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="fe86a-238">angular</span><span class="sxs-lookup"><span data-stu-id="fe86a-238">angular</span></span>](#spa)                 | <span data-ttu-id="fe86a-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-239">[C#]</span></span>         | <span data-ttu-id="fe86a-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="fe86a-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="fe86a-241">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-241">2.0</span></span>        |
| <span data-ttu-id="fe86a-242">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="fe86a-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="fe86a-243">react</span><span class="sxs-lookup"><span data-stu-id="fe86a-243">react</span></span>](#spa)                   | <span data-ttu-id="fe86a-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-244">[C#]</span></span>         | <span data-ttu-id="fe86a-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="fe86a-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="fe86a-246">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-246">2.0</span></span>        |
| <span data-ttu-id="fe86a-247">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="fe86a-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="fe86a-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="fe86a-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="fe86a-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-249">[C#]</span></span>         | <span data-ttu-id="fe86a-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="fe86a-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="fe86a-251">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-251">2.0</span></span>        |
| <span data-ttu-id="fe86a-252">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="fe86a-252">Razor Class Library</span></span>                          | [<span data-ttu-id="fe86a-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="fe86a-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="fe86a-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-254">[C#]</span></span>         | <span data-ttu-id="fe86a-255">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="fe86a-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="fe86a-256">2.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-256">2.1</span></span>        |
| <span data-ttu-id="fe86a-257">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="fe86a-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="fe86a-258">webapi</span><span class="sxs-lookup"><span data-stu-id="fe86a-258">webapi</span></span>](#webapi)               | <span data-ttu-id="fe86a-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="fe86a-259">[C#], F#</span></span>     | <span data-ttu-id="fe86a-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="fe86a-260">Web/WebAPI</span></span>                            | <span data-ttu-id="fe86a-261">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-261">1.0</span></span>        |
| <span data-ttu-id="fe86a-262">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="fe86a-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="fe86a-263">grpc</span><span class="sxs-lookup"><span data-stu-id="fe86a-263">grpc</span></span>](#web-others)             | <span data-ttu-id="fe86a-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="fe86a-264">[C#]</span></span>         | <span data-ttu-id="fe86a-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="fe86a-265">Web/gRPC</span></span>                              | <span data-ttu-id="fe86a-266">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-266">3.0</span></span>        |
| <span data-ttu-id="fe86a-267">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="fe86a-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="fe86a-268">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="fe86a-268">Config</span></span>                                | <span data-ttu-id="fe86a-269">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-269">3.0</span></span>        |
| <span data-ttu-id="fe86a-270">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="fe86a-270">global.json file</span></span>                             | [<span data-ttu-id="fe86a-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="fe86a-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="fe86a-272">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="fe86a-272">Config</span></span>                                | <span data-ttu-id="fe86a-273">2.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-273">2.0</span></span>        |
| <span data-ttu-id="fe86a-274">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="fe86a-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="fe86a-275">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="fe86a-275">Config</span></span>                                | <span data-ttu-id="fe86a-276">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-276">1.0</span></span>        |
| <span data-ttu-id="fe86a-277">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="fe86a-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="fe86a-278">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="fe86a-278">Config</span></span>                                | <span data-ttu-id="fe86a-279">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-279">3.0</span></span>        |
| <span data-ttu-id="fe86a-280">Web Config</span><span class="sxs-lookup"><span data-stu-id="fe86a-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="fe86a-281">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="fe86a-281">Config</span></span>                                | <span data-ttu-id="fe86a-282">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-282">1.0</span></span>        |
| <span data-ttu-id="fe86a-283">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="fe86a-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="fe86a-284">Lösung</span><span class="sxs-lookup"><span data-stu-id="fe86a-284">Solution</span></span>                              | <span data-ttu-id="fe86a-285">1.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-285">1.0</span></span>        |
| <span data-ttu-id="fe86a-286">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="fe86a-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="fe86a-287">proto</span><span class="sxs-lookup"><span data-stu-id="fe86a-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="fe86a-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="fe86a-288">Web/gRPC</span></span>                              | <span data-ttu-id="fe86a-289">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="fe86a-290">Optionen</span><span class="sxs-lookup"><span data-stu-id="fe86a-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="fe86a-291">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="fe86a-292">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="fe86a-293">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="fe86a-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="fe86a-294">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="fe86a-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="fe86a-295">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="fe86a-295">Prints out help for the command.</span></span> <span data-ttu-id="fe86a-296">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fe86a-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="fe86a-297">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="fe86a-298">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="fe86a-299">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="fe86a-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="fe86a-300">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="fe86a-301">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="fe86a-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="fe86a-302">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fe86a-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="fe86a-303">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="fe86a-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="fe86a-304">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="fe86a-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="fe86a-305">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="fe86a-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="fe86a-306">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-306">The language of the template to create.</span></span> <span data-ttu-id="fe86a-307">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="fe86a-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="fe86a-308">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="fe86a-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fe86a-309">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="fe86a-310">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="fe86a-311">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="fe86a-312">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fe86a-312">The name for the created output.</span></span> <span data-ttu-id="fe86a-313">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe86a-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="fe86a-314">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-314">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="fe86a-315">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="fe86a-315">Location to place the generated output.</span></span> <span data-ttu-id="fe86a-316">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe86a-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="fe86a-317">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-317">Filters templates based on available types.</span></span> <span data-ttu-id="fe86a-318">Bei `project` und `item` handelt es sich um vordefinierte Werte.</span><span class="sxs-lookup"><span data-stu-id="fe86a-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="fe86a-319">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="fe86a-320">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="fe86a-321">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="fe86a-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="fe86a-322">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="fe86a-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="fe86a-323">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="fe86a-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="fe86a-324">Beispielsweise funktioniert zwar *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="fe86a-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="fe86a-325">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="fe86a-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="fe86a-326">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="fe86a-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="fe86a-327">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="fe86a-328">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fe86a-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="fe86a-329">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="fe86a-330">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="fe86a-330">Template options</span></span>

<span data-ttu-id="fe86a-331">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="fe86a-331">Each project template may have additional options available.</span></span> <span data-ttu-id="fe86a-332">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="fe86a-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="fe86a-333">Konsole</span><span class="sxs-lookup"><span data-stu-id="fe86a-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fe86a-334">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-335">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="fe86a-336">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-337">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-337">SDK version</span></span> | <span data-ttu-id="fe86a-338">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-339">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-339">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-340">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-341">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="fe86a-342">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fe86a-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fe86a-343">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="fe86a-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="fe86a-344">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-344">Not supported for F#.</span></span> <span data-ttu-id="fe86a-345">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fe86a-346">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="fe86a-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-347">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="fe86a-348">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="fe86a-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="fe86a-350">classlib</span><span class="sxs-lookup"><span data-stu-id="fe86a-350">classlib</span></span>

- <span data-ttu-id="fe86a-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fe86a-352">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-353">Werte: `net5.0` oder `netcoreapp<version>`, um eine .NET-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-353">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="fe86a-354">Der Standardwert für das .NET 5.0 SDK ist `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-354">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="fe86a-355">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fe86a-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fe86a-356">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="fe86a-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="fe86a-357">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-357">Not supported for F#.</span></span> <span data-ttu-id="fe86a-358">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fe86a-359">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="fe86a-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-360">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="fe86a-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="fe86a-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="fe86a-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fe86a-364">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-365">Der Standardwert ist `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-365">The default value is `net5.0`.</span></span> <span data-ttu-id="fe86a-366">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="fe86a-367">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fe86a-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fe86a-368">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="fe86a-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="fe86a-369">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="fe86a-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-370">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="fe86a-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="fe86a-372">winforms, winformslib</span></span>

- <span data-ttu-id="fe86a-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="fe86a-374">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fe86a-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="fe86a-375">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="fe86a-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="fe86a-376">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="fe86a-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-377">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="fe86a-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="fe86a-379">worker, grpc</span></span>

- <span data-ttu-id="fe86a-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fe86a-381">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-382">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="fe86a-383">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fe86a-384">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-385">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="fe86a-387">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="fe86a-387">mstest, xunit</span></span>

- <span data-ttu-id="fe86a-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fe86a-389">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-390">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="fe86a-391">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-392">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-392">SDK version</span></span> | <span data-ttu-id="fe86a-393">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-394">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-394">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-395">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-395">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-396">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-396">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="fe86a-397">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="fe86a-397">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-398">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-398">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-399">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-399">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="fe86a-400">nunit</span><span class="sxs-lookup"><span data-stu-id="fe86a-400">nunit</span></span>

- <span data-ttu-id="fe86a-401">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-401">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fe86a-402">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-402">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="fe86a-403">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-403">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-404">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-404">SDK version</span></span> | <span data-ttu-id="fe86a-405">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-405">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-406">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-406">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-407">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-407">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-408">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-408">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fe86a-409">2.2</span><span class="sxs-lookup"><span data-stu-id="fe86a-409">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="fe86a-410">2.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-410">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="fe86a-411">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="fe86a-411">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-412">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-412">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-413">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-413">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="fe86a-414">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="fe86a-414">page</span></span>

- <span data-ttu-id="fe86a-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="fe86a-416">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="fe86a-416">Namespace for the generated code.</span></span> <span data-ttu-id="fe86a-417">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-417">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="fe86a-418">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="fe86a-418">Creates the page without a PageModel.</span></span>

<span data-ttu-id="fe86a-419">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-419">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="fe86a-420">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="fe86a-420">viewimports, proto</span></span>

- <span data-ttu-id="fe86a-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="fe86a-422">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="fe86a-422">Namespace for the generated code.</span></span> <span data-ttu-id="fe86a-423">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-423">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="fe86a-424">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-424">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="fe86a-425">blazorserver</span><span class="sxs-lookup"><span data-stu-id="fe86a-425">blazorserver</span></span>

- <span data-ttu-id="fe86a-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fe86a-427">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="fe86a-427">The type of authentication to use.</span></span> <span data-ttu-id="fe86a-428">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fe86a-428">The possible values are:</span></span>

  - <span data-ttu-id="fe86a-429">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe86a-429">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fe86a-430">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-430">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="fe86a-431">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="fe86a-431">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fe86a-432">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="fe86a-432">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="fe86a-433">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="fe86a-433">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="fe86a-434">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-434">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-435">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-435">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fe86a-436">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-436">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-437">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-437">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fe86a-438">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-438">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fe86a-439">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-439">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="fe86a-440">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-440">The reset password policy ID for this project.</span></span> <span data-ttu-id="fe86a-441">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-441">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="fe86a-442">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-442">The edit profile policy ID for this project.</span></span> <span data-ttu-id="fe86a-443">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-443">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-444">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-444">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fe86a-445">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-445">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="fe86a-446">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-446">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fe86a-447">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-447">The Client ID for this project.</span></span> <span data-ttu-id="fe86a-448">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-448">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="fe86a-449">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-449">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fe86a-450">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="fe86a-450">The domain for the directory tenant.</span></span> <span data-ttu-id="fe86a-451">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-451">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-452">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-452">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fe86a-453">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-453">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fe86a-454">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-454">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-455">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-455">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="fe86a-456">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-456">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="fe86a-457">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-457">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-458">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-458">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fe86a-459">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe86a-459">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fe86a-460">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-460">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fe86a-461">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-461">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-462">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-462">Turns off HTTPS.</span></span> <span data-ttu-id="fe86a-463">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe86a-463">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fe86a-464">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-464">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fe86a-465">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-465">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-466">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-466">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-467">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-467">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="fe86a-468">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="fe86a-468">blazorwasm</span></span>

- <span data-ttu-id="fe86a-469">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-469">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="fe86a-470">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-470">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="fe86a-471">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-471">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-472">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-472">SDK version</span></span> | <span data-ttu-id="fe86a-473">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-473">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-474">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-474">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-475">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-475">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="fe86a-476">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="fe86a-477">Enthält einen ASP.NET Core-Host für die WebAssembly-App Blazor.</span><span class="sxs-lookup"><span data-stu-id="fe86a-477">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="fe86a-478">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="fe86a-478">The type of authentication to use.</span></span> <span data-ttu-id="fe86a-479">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fe86a-479">The possible values are:</span></span>

  - <span data-ttu-id="fe86a-480">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe86a-480">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fe86a-481">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-481">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="fe86a-482">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="fe86a-482">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fe86a-483">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="fe86a-483">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="fe86a-484">Die Autorität des OIDC-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="fe86a-484">The authority of the OIDC provider.</span></span> <span data-ttu-id="fe86a-485">Mit der `Individual`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-485">Use with `Individual` authentication.</span></span> <span data-ttu-id="fe86a-486">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-486">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-487">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-487">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fe86a-488">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-488">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-489">Der Standardwert ist `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-489">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fe86a-490">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-490">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fe86a-491">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-491">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-492">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-492">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fe86a-493">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-493">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-494">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-494">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fe86a-495">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-495">The Client ID for this project.</span></span> <span data-ttu-id="fe86a-496">Wird in eigenständigen Szenarien mit der Authentifizierung `IndividualB2C`, `SingleOrg` oder `Individual` verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe86a-496">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="fe86a-497">Der Standardwert ist `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-497">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fe86a-498">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="fe86a-498">The domain for the directory tenant.</span></span> <span data-ttu-id="fe86a-499">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-499">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-500">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-500">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="fe86a-501">Der APP-ID-URI für die Server-API, die aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-501">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="fe86a-502">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-502">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-503">Der Standardwert ist `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-503">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="fe86a-504">Die Client-ID für die API, die vom Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="fe86a-504">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="fe86a-505">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-506">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-506">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="fe86a-507">Der API-Bereich, der vom Client angefordert werden muss, um ein Zugriffstoken bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-507">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="fe86a-508">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-508">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-509">Der Standardwert ist `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-509">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fe86a-510">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-510">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fe86a-511">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-511">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-512">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-512">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fe86a-513">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe86a-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fe86a-514">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-514">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fe86a-515">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="fe86a-516">Erzeugt eine progressive Webanwendung (PWA), die Installation und Offlinenutzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-516">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-517">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-517">Turns off HTTPS.</span></span> <span data-ttu-id="fe86a-518">Diese Option gilt nur, wenn `Individual`, `IndividualB2C` oder `SingleOrg` für `--auth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe86a-518">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fe86a-519">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-519">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fe86a-520">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-520">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="fe86a-521">URL der API, die von der Web-App aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-521">URL of the API to call from the web app.</span></span> <span data-ttu-id="fe86a-522">Gilt nur für die Authentifizierung `SingleOrg` oder `IndividualB2C` ohne Angabe eines ASP.NET Core-Hosts.</span><span class="sxs-lookup"><span data-stu-id="fe86a-522">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="fe86a-523">Standardwert: `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-523">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="fe86a-524">Gibt an, ob die Web-App Microsoft Graph aufruft.</span><span class="sxs-lookup"><span data-stu-id="fe86a-524">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="fe86a-525">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-525">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="fe86a-526">Bereiche, die angefordert werden müssen, um die API aus der Web-App aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fe86a-526">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="fe86a-527">Gilt nur für die Authentifizierung `SingleOrg` oder `IndividualB2C` ohne Angabe eines ASP.NET Core-Hosts.</span><span class="sxs-lookup"><span data-stu-id="fe86a-527">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="fe86a-528">Der Standardwert ist `user.read`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-528">The default is `user.read`.</span></span>

<span data-ttu-id="fe86a-529">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-529">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="fe86a-530">Web-</span><span class="sxs-lookup"><span data-stu-id="fe86a-530">web</span></span>

- <span data-ttu-id="fe86a-531">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-531">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="fe86a-532">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fe86a-533">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-534">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fe86a-535">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-536">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-536">SDK version</span></span> | <span data-ttu-id="fe86a-537">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-538">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-538">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-539">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-539">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-540">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-540">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fe86a-541">2.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-541">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="fe86a-542">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-543">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-543">Turns off HTTPS.</span></span>

<span data-ttu-id="fe86a-544">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-544">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="fe86a-545">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="fe86a-545">mvc, webapp</span></span>

- <span data-ttu-id="fe86a-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fe86a-547">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="fe86a-547">The type of authentication to use.</span></span> <span data-ttu-id="fe86a-548">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fe86a-548">The possible values are:</span></span>

  - <span data-ttu-id="fe86a-549">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe86a-549">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fe86a-550">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-550">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="fe86a-551">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="fe86a-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fe86a-552">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="fe86a-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="fe86a-553">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="fe86a-553">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="fe86a-554">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-554">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-555">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-555">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fe86a-556">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-556">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-557">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-557">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fe86a-558">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-558">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fe86a-559">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-559">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="fe86a-560">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-560">The reset password policy ID for this project.</span></span> <span data-ttu-id="fe86a-561">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-561">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="fe86a-562">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-562">The edit profile policy ID for this project.</span></span> <span data-ttu-id="fe86a-563">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-563">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-564">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-564">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fe86a-565">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-565">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="fe86a-566">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-566">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fe86a-567">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-567">The Client ID for this project.</span></span> <span data-ttu-id="fe86a-568">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-568">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="fe86a-569">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-569">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fe86a-570">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="fe86a-570">The domain for the directory tenant.</span></span> <span data-ttu-id="fe86a-571">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-571">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-572">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-572">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fe86a-573">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-573">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fe86a-574">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-574">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-575">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-575">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="fe86a-576">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-576">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="fe86a-577">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-577">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-578">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-578">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fe86a-579">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe86a-579">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fe86a-580">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-580">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fe86a-581">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-581">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-582">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-582">Turns off HTTPS.</span></span> <span data-ttu-id="fe86a-583">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe86a-583">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fe86a-584">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-584">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fe86a-585">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-585">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fe86a-586">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-586">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-587">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-587">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="fe86a-588">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-588">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-589">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-589">SDK version</span></span> | <span data-ttu-id="fe86a-590">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-590">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-591">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-591">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-592">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-592">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-593">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-593">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="fe86a-594">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-594">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="fe86a-595">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="fe86a-595">Includes BrowserLink in the project.</span></span> <span data-ttu-id="fe86a-596">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-596">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="fe86a-597">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="fe86a-597">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="fe86a-598">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-598">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="fe86a-599">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-599">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="fe86a-600">angular, react</span><span class="sxs-lookup"><span data-stu-id="fe86a-600">angular, react</span></span>

- <span data-ttu-id="fe86a-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fe86a-602">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="fe86a-602">The type of authentication to use.</span></span> <span data-ttu-id="fe86a-603">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-603">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="fe86a-604">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fe86a-604">The possible values are:</span></span>

  - <span data-ttu-id="fe86a-605">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe86a-605">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fe86a-606">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-606">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fe86a-607">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-607">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="fe86a-608">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-608">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-609">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-609">Turns off HTTPS.</span></span> <span data-ttu-id="fe86a-610">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="fe86a-610">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fe86a-611">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-611">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fe86a-612">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-612">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-613">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-613">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fe86a-614">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-614">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-615">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-615">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fe86a-616">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-616">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-617">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-617">SDK version</span></span> | <span data-ttu-id="fe86a-618">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-618">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-619">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-619">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-620">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-620">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-621">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-621">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fe86a-622">2.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-622">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="fe86a-623">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-623">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="fe86a-624">reactredux</span><span class="sxs-lookup"><span data-stu-id="fe86a-624">reactredux</span></span>

- <span data-ttu-id="fe86a-625">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-625">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="fe86a-626">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-626">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fe86a-627">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-627">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-628">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-628">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fe86a-629">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-629">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-630">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-630">SDK version</span></span> | <span data-ttu-id="fe86a-631">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-631">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-632">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-632">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-633">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-633">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-634">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-634">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fe86a-635">2.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-635">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="fe86a-636">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-636">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-637">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-637">Turns off HTTPS.</span></span>

<span data-ttu-id="fe86a-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-638">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="fe86a-639">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="fe86a-639">razorclasslib</span></span>

- <span data-ttu-id="fe86a-640">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-640">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="fe86a-641">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-641">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="fe86a-642">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="fe86a-642">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="fe86a-643">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="fe86a-643">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="fe86a-644">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-644">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="fe86a-645">Web-API</span><span class="sxs-lookup"><span data-stu-id="fe86a-645">webapi</span></span>

- <span data-ttu-id="fe86a-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="fe86a-647">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="fe86a-647">The type of authentication to use.</span></span> <span data-ttu-id="fe86a-648">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="fe86a-648">The possible values are:</span></span>

  - <span data-ttu-id="fe86a-649">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="fe86a-649">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="fe86a-650">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="fe86a-650">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="fe86a-651">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="fe86a-651">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="fe86a-652">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fe86a-652">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-653">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-653">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="fe86a-654">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-654">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="fe86a-655">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-655">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="fe86a-656">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-656">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="fe86a-657">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-657">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="fe86a-658">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-658">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="fe86a-659">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-659">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-660">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-660">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="fe86a-661">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-661">The Client ID for this project.</span></span> <span data-ttu-id="fe86a-662">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-662">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-663">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-663">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="fe86a-664">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="fe86a-664">The domain for the directory tenant.</span></span> <span data-ttu-id="fe86a-665">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-665">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-666">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-666">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="fe86a-667">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-667">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="fe86a-668">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="fe86a-668">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="fe86a-669">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="fe86a-669">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="fe86a-670">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="fe86a-670">Allows this application read-access to the directory.</span></span> <span data-ttu-id="fe86a-671">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-671">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="fe86a-672">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="fe86a-672">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="fe86a-673">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="fe86a-673">Turns off HTTPS.</span></span> <span data-ttu-id="fe86a-674">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-674">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="fe86a-675">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe86a-675">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="fe86a-676">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe86a-676">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="fe86a-677">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="fe86a-677">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="fe86a-678">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="fe86a-678">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="fe86a-679">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe86a-679">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="fe86a-680">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-680">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="fe86a-681">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="fe86a-681">SDK version</span></span> | <span data-ttu-id="fe86a-682">Standardwert</span><span class="sxs-lookup"><span data-stu-id="fe86a-682">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="fe86a-683">5.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-683">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="fe86a-684">3.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-684">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="fe86a-685">3.0</span><span class="sxs-lookup"><span data-stu-id="fe86a-685">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="fe86a-686">2.1</span><span class="sxs-lookup"><span data-stu-id="fe86a-686">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="fe86a-687">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="fe86a-687">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="fe86a-688">\*\*_</span><span class="sxs-lookup"><span data-stu-id="fe86a-688">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="fe86a-689">globaljson</span><span class="sxs-lookup"><span data-stu-id="fe86a-689">globaljson</span></span>

- <span data-ttu-id="fe86a-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="fe86a-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="fe86a-691">Gibt die Version des .NET SDK an, die in der Datei *global.json* verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="fe86a-691">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="fe86a-692">Beispiele</span><span class="sxs-lookup"><span data-stu-id="fe86a-692">Examples</span></span>

- <span data-ttu-id="fe86a-693">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="fe86a-693">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="fe86a-694">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="fe86a-694">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="fe86a-695">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-695">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="fe86a-696">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="fe86a-696">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="fe86a-697">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="fe86a-697">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="fe86a-698">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="fe86a-698">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="fe86a-699">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-699">List all templates matching the *we* substring.</span></span> <span data-ttu-id="fe86a-700">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-700">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="fe86a-701">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="fe86a-701">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="fe86a-702">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="fe86a-702">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="fe86a-703">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="fe86a-703">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="fe86a-704">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="fe86a-704">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="fe86a-705">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="fe86a-705">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="fe86a-706">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe86a-706">See also</span></span>

- [<span data-ttu-id="fe86a-707">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="fe86a-707">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="fe86a-708">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="fe86a-708">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="fe86a-709">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="fe86a-709">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="fe86a-710">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="fe86a-710">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
