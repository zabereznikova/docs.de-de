---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 04/10/2020
ms.openlocfilehash: 39301ad95761848b60b45cb5c18ede937f70c32c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283974"
---
# <a name="dotnet-new"></a><span data-ttu-id="10bae-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="10bae-103">dotnet new</span></span>

<span data-ttu-id="10bae-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="10bae-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="10bae-105">name</span><span class="sxs-lookup"><span data-stu-id="10bae-105">Name</span></span>

<span data-ttu-id="10bae-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="10bae-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="10bae-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="10bae-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="10bae-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10bae-108">Description</span></span>

<span data-ttu-id="10bae-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="10bae-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="10bae-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="10bae-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="10bae-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="10bae-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="10bae-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="10bae-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="10bae-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="10bae-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="10bae-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="10bae-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="10bae-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="10bae-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="10bae-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10bae-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="10bae-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="10bae-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="10bae-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="10bae-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="10bae-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="10bae-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="10bae-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="10bae-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="10bae-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="10bae-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="10bae-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="10bae-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="10bae-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10bae-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="10bae-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="10bae-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="10bae-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="10bae-125">Templates</span></span>                                    | <span data-ttu-id="10bae-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="10bae-126">Short name</span></span>                      | <span data-ttu-id="10bae-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="10bae-127">Language</span></span>     | <span data-ttu-id="10bae-128">Tags</span><span class="sxs-lookup"><span data-stu-id="10bae-128">Tags</span></span>                                  | <span data-ttu-id="10bae-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="10bae-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="10bae-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="10bae-130">Console Application</span></span>                          | [<span data-ttu-id="10bae-131">console</span><span class="sxs-lookup"><span data-stu-id="10bae-131">console</span></span>](#console)             | <span data-ttu-id="10bae-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10bae-132">[C#], F#, VB</span></span> | <span data-ttu-id="10bae-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="10bae-133">Common/Console</span></span>                        | <span data-ttu-id="10bae-134">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-134">1.0</span></span>        |
| <span data-ttu-id="10bae-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="10bae-135">Class library</span></span>                                | [<span data-ttu-id="10bae-136">classlib</span><span class="sxs-lookup"><span data-stu-id="10bae-136">classlib</span></span>](#classlib)           | <span data-ttu-id="10bae-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10bae-137">[C#], F#, VB</span></span> | <span data-ttu-id="10bae-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="10bae-138">Common/Library</span></span>                        | <span data-ttu-id="10bae-139">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-139">1.0</span></span>        |
| <span data-ttu-id="10bae-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="10bae-140">WPF Application</span></span>                              | [<span data-ttu-id="10bae-141">wpf</span><span class="sxs-lookup"><span data-stu-id="10bae-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="10bae-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-142">[C#]</span></span>         | <span data-ttu-id="10bae-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="10bae-143">Common/WPF</span></span>                            | <span data-ttu-id="10bae-144">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-144">3.0</span></span>        |
| <span data-ttu-id="10bae-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="10bae-145">WPF Class library</span></span>                            | [<span data-ttu-id="10bae-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="10bae-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="10bae-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-147">[C#]</span></span>         | <span data-ttu-id="10bae-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="10bae-148">Common/WPF</span></span>                            | <span data-ttu-id="10bae-149">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-149">3.0</span></span>        |
| <span data-ttu-id="10bae-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="10bae-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="10bae-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="10bae-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="10bae-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-152">[C#]</span></span>         | <span data-ttu-id="10bae-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="10bae-153">Common/WPF</span></span>                            | <span data-ttu-id="10bae-154">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-154">3.0</span></span>        |
| <span data-ttu-id="10bae-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="10bae-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="10bae-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="10bae-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="10bae-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-157">[C#]</span></span>         | <span data-ttu-id="10bae-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="10bae-158">Common/WPF</span></span>                            | <span data-ttu-id="10bae-159">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-159">3.0</span></span>        |
| <span data-ttu-id="10bae-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="10bae-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="10bae-161">winforms</span><span class="sxs-lookup"><span data-stu-id="10bae-161">winforms</span></span>](#winforms)           | <span data-ttu-id="10bae-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-162">[C#]</span></span>         | <span data-ttu-id="10bae-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="10bae-163">Common/WinForms</span></span>                       | <span data-ttu-id="10bae-164">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-164">3.0</span></span>        |
| <span data-ttu-id="10bae-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="10bae-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="10bae-166">winforms</span><span class="sxs-lookup"><span data-stu-id="10bae-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="10bae-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-167">[C#]</span></span>         | <span data-ttu-id="10bae-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="10bae-168">Common/WinForms</span></span>                       | <span data-ttu-id="10bae-169">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-169">3.0</span></span>        |
| <span data-ttu-id="10bae-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="10bae-170">Worker Service</span></span>                               | [<span data-ttu-id="10bae-171">worker</span><span class="sxs-lookup"><span data-stu-id="10bae-171">worker</span></span>](#web-others)           | <span data-ttu-id="10bae-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-172">[C#]</span></span>         | <span data-ttu-id="10bae-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="10bae-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="10bae-174">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-174">3.0</span></span>        |
| <span data-ttu-id="10bae-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="10bae-175">Unit Test Project</span></span>                            | [<span data-ttu-id="10bae-176">mstest</span><span class="sxs-lookup"><span data-stu-id="10bae-176">mstest</span></span>](#test)                 | <span data-ttu-id="10bae-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10bae-177">[C#], F#, VB</span></span> | <span data-ttu-id="10bae-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="10bae-178">Test/MSTest</span></span>                           | <span data-ttu-id="10bae-179">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-179">1.0</span></span>        |
| <span data-ttu-id="10bae-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="10bae-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="10bae-181">nunit</span><span class="sxs-lookup"><span data-stu-id="10bae-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="10bae-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10bae-182">[C#], F#, VB</span></span> | <span data-ttu-id="10bae-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="10bae-183">Test/NUnit</span></span>                            | <span data-ttu-id="10bae-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="10bae-184">2.1.400</span></span>    |
| <span data-ttu-id="10bae-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="10bae-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="10bae-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10bae-186">[C#], F#, VB</span></span> | <span data-ttu-id="10bae-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="10bae-187">Test/NUnit</span></span>                            | <span data-ttu-id="10bae-188">2.2</span><span class="sxs-lookup"><span data-stu-id="10bae-188">2.2</span></span>        |
| <span data-ttu-id="10bae-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="10bae-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="10bae-190">xunit</span><span class="sxs-lookup"><span data-stu-id="10bae-190">xunit</span></span>](#test)                  | <span data-ttu-id="10bae-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="10bae-191">[C#], F#, VB</span></span> | <span data-ttu-id="10bae-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="10bae-192">Test/xUnit</span></span>                            | <span data-ttu-id="10bae-193">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-193">1.0</span></span>        |
| <span data-ttu-id="10bae-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="10bae-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="10bae-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-195">[C#]</span></span>         | <span data-ttu-id="10bae-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="10bae-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="10bae-197">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-197">3.0</span></span>        |
| <span data-ttu-id="10bae-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="10bae-198">Razor Page</span></span>                                   | [<span data-ttu-id="10bae-199">page</span><span class="sxs-lookup"><span data-stu-id="10bae-199">page</span></span>](#page)                   | <span data-ttu-id="10bae-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-200">[C#]</span></span>         | <span data-ttu-id="10bae-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="10bae-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="10bae-202">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-202">2.0</span></span>        |
| <span data-ttu-id="10bae-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="10bae-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="10bae-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="10bae-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="10bae-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-205">[C#]</span></span>         | <span data-ttu-id="10bae-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="10bae-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="10bae-207">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-207">2.0</span></span>        |
| <span data-ttu-id="10bae-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="10bae-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="10bae-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-209">[C#]</span></span>         | <span data-ttu-id="10bae-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="10bae-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="10bae-211">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-211">2.0</span></span>        |
| <span data-ttu-id="10bae-212">Blazor-Server-App</span><span class="sxs-lookup"><span data-stu-id="10bae-212">Blazor Server App</span></span>                            | [<span data-ttu-id="10bae-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="10bae-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="10bae-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-214">[C#]</span></span>         | <span data-ttu-id="10bae-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="10bae-215">Web/Blazor</span></span>                            | <span data-ttu-id="10bae-216">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-216">3.0</span></span>        |
| <span data-ttu-id="10bae-217">Blazor-WebAssembly-App</span><span class="sxs-lookup"><span data-stu-id="10bae-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="10bae-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-218">[C#]</span></span>         | <span data-ttu-id="10bae-219">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="10bae-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="10bae-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="10bae-220">3.1.300</span></span>    |
| <span data-ttu-id="10bae-221">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="10bae-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="10bae-222">web</span><span class="sxs-lookup"><span data-stu-id="10bae-222">web</span></span>](#web)                     | <span data-ttu-id="10bae-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10bae-223">[C#], F#</span></span>     | <span data-ttu-id="10bae-224">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="10bae-224">Web/Empty</span></span>                             | <span data-ttu-id="10bae-225">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-225">1.0</span></span>        |
| <span data-ttu-id="10bae-226">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="10bae-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="10bae-227">mvc</span><span class="sxs-lookup"><span data-stu-id="10bae-227">mvc</span></span>](#web-options)             | <span data-ttu-id="10bae-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10bae-228">[C#], F#</span></span>     | <span data-ttu-id="10bae-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="10bae-229">Web/MVC</span></span>                               | <span data-ttu-id="10bae-230">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-230">1.0</span></span>        |
| <span data-ttu-id="10bae-231">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="10bae-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="10bae-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="10bae-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="10bae-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-233">[C#]</span></span>         | <span data-ttu-id="10bae-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="10bae-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="10bae-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="10bae-236">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="10bae-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="10bae-237">angular</span><span class="sxs-lookup"><span data-stu-id="10bae-237">angular</span></span>](#spa)                 | <span data-ttu-id="10bae-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-238">[C#]</span></span>         | <span data-ttu-id="10bae-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="10bae-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="10bae-240">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-240">2.0</span></span>        |
| <span data-ttu-id="10bae-241">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="10bae-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="10bae-242">react</span><span class="sxs-lookup"><span data-stu-id="10bae-242">react</span></span>](#spa)                   | <span data-ttu-id="10bae-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-243">[C#]</span></span>         | <span data-ttu-id="10bae-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="10bae-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="10bae-245">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-245">2.0</span></span>        |
| <span data-ttu-id="10bae-246">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="10bae-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="10bae-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="10bae-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="10bae-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-248">[C#]</span></span>         | <span data-ttu-id="10bae-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="10bae-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="10bae-250">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-250">2.0</span></span>        |
| <span data-ttu-id="10bae-251">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="10bae-251">Razor Class Library</span></span>                          | [<span data-ttu-id="10bae-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="10bae-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="10bae-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-253">[C#]</span></span>         | <span data-ttu-id="10bae-254">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="10bae-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="10bae-255">2.1</span><span class="sxs-lookup"><span data-stu-id="10bae-255">2.1</span></span>        |
| <span data-ttu-id="10bae-256">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="10bae-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="10bae-257">webapi</span><span class="sxs-lookup"><span data-stu-id="10bae-257">webapi</span></span>](#webapi)               | <span data-ttu-id="10bae-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="10bae-258">[C#], F#</span></span>     | <span data-ttu-id="10bae-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="10bae-259">Web/WebAPI</span></span>                            | <span data-ttu-id="10bae-260">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-260">1.0</span></span>        |
| <span data-ttu-id="10bae-261">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="10bae-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="10bae-262">grpc</span><span class="sxs-lookup"><span data-stu-id="10bae-262">grpc</span></span>](#web-others)             | <span data-ttu-id="10bae-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="10bae-263">[C#]</span></span>         | <span data-ttu-id="10bae-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="10bae-264">Web/gRPC</span></span>                              | <span data-ttu-id="10bae-265">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-265">3.0</span></span>        |
| <span data-ttu-id="10bae-266">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="10bae-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="10bae-267">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="10bae-267">Config</span></span>                                | <span data-ttu-id="10bae-268">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-268">3.0</span></span>        |
| <span data-ttu-id="10bae-269">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="10bae-269">global.json file</span></span>                             | [<span data-ttu-id="10bae-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="10bae-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="10bae-271">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="10bae-271">Config</span></span>                                | <span data-ttu-id="10bae-272">2.0</span><span class="sxs-lookup"><span data-stu-id="10bae-272">2.0</span></span>        |
| <span data-ttu-id="10bae-273">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="10bae-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="10bae-274">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="10bae-274">Config</span></span>                                | <span data-ttu-id="10bae-275">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-275">1.0</span></span>        |
| <span data-ttu-id="10bae-276">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="10bae-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="10bae-277">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="10bae-277">Config</span></span>                                | <span data-ttu-id="10bae-278">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-278">3.0</span></span>        |
| <span data-ttu-id="10bae-279">Web Config</span><span class="sxs-lookup"><span data-stu-id="10bae-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="10bae-280">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="10bae-280">Config</span></span>                                | <span data-ttu-id="10bae-281">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-281">1.0</span></span>        |
| <span data-ttu-id="10bae-282">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="10bae-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="10bae-283">Lösung</span><span class="sxs-lookup"><span data-stu-id="10bae-283">Solution</span></span>                              | <span data-ttu-id="10bae-284">1.0</span><span class="sxs-lookup"><span data-stu-id="10bae-284">1.0</span></span>        |
| <span data-ttu-id="10bae-285">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="10bae-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="10bae-286">proto</span><span class="sxs-lookup"><span data-stu-id="10bae-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="10bae-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="10bae-287">Web/gRPC</span></span>                              | <span data-ttu-id="10bae-288">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="10bae-289">Optionen</span><span class="sxs-lookup"><span data-stu-id="10bae-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="10bae-290">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="10bae-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="10bae-291">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="10bae-292">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="10bae-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="10bae-293">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="10bae-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="10bae-294">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="10bae-294">Prints out help for the command.</span></span> <span data-ttu-id="10bae-295">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="10bae-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="10bae-296">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="10bae-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="10bae-297">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="10bae-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="10bae-298">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="10bae-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="10bae-299">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="10bae-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="10bae-300">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="10bae-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="10bae-301">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="10bae-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="10bae-302">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="10bae-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="10bae-303">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="10bae-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="10bae-304">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="10bae-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="10bae-305">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="10bae-305">The language of the template to create.</span></span> <span data-ttu-id="10bae-306">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="10bae-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="10bae-307">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="10bae-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="10bae-308">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="10bae-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="10bae-309">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="10bae-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="10bae-310">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="10bae-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="10bae-311">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="10bae-311">The name for the created output.</span></span> <span data-ttu-id="10bae-312">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="10bae-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="10bae-313">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="10bae-314">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="10bae-315">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="10bae-315">Location to place the generated output.</span></span> <span data-ttu-id="10bae-316">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="10bae-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="10bae-317">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="10bae-317">Filters templates based on available types.</span></span> <span data-ttu-id="10bae-318">Die Werte `project`, `item` und `other` sind vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="10bae-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="10bae-319">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="10bae-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="10bae-320">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="10bae-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="10bae-321">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="10bae-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="10bae-322">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="10bae-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="10bae-323">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="10bae-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="10bae-324">Beispielsweise funktioniert zwar *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="10bae-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="10bae-325">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="10bae-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="10bae-326">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="10bae-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="10bae-327">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="10bae-328">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="10bae-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="10bae-329">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="10bae-330">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="10bae-330">Template options</span></span>

<span data-ttu-id="10bae-331">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="10bae-331">Each project template may have additional options available.</span></span> <span data-ttu-id="10bae-332">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="10bae-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="10bae-333">Konsole</span><span class="sxs-lookup"><span data-stu-id="10bae-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-334">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-335">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="10bae-336">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-337">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-337">SDK version</span></span> | <span data-ttu-id="10bae-338">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-339">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-340">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="10bae-341">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="10bae-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="10bae-342">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="10bae-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="10bae-343">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10bae-343">Not supported for F#.</span></span> <span data-ttu-id="10bae-344">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="10bae-345">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="10bae-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-346">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="10bae-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="10bae-347">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="10bae-348">classlib</span><span class="sxs-lookup"><span data-stu-id="10bae-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-349">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-350">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="10bae-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="10bae-351">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="10bae-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="10bae-352">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="10bae-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="10bae-353">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="10bae-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="10bae-354">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="10bae-354">Not supported for F#.</span></span> <span data-ttu-id="10bae-355">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="10bae-356">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="10bae-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-357">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="10bae-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="10bae-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-359">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-360">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="10bae-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="10bae-361">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="10bae-362">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="10bae-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="10bae-363">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="10bae-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="10bae-364">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="10bae-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-365">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="10bae-366">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="10bae-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="10bae-367">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="10bae-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="10bae-368">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="10bae-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="10bae-369">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="10bae-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-370">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="10bae-371">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="10bae-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-372">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-373">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="10bae-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="10bae-374">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-375">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-376">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="10bae-377">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="10bae-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-378">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-379">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="10bae-380">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-381">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-381">SDK version</span></span> | <span data-ttu-id="10bae-382">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-383">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-384">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="10bae-385">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="10bae-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-386">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="10bae-387">nunit</span><span class="sxs-lookup"><span data-stu-id="10bae-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-388">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="10bae-389">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-390">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-390">SDK version</span></span> | <span data-ttu-id="10bae-391">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-392">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-393">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="10bae-394">2.2</span><span class="sxs-lookup"><span data-stu-id="10bae-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="10bae-395">2.1</span><span class="sxs-lookup"><span data-stu-id="10bae-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="10bae-396">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="10bae-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-397">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="10bae-398">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="10bae-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="10bae-399">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="10bae-399">Namespace for the generated code.</span></span> <span data-ttu-id="10bae-400">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="10bae-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="10bae-401">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="10bae-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="10bae-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="10bae-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="10bae-403">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="10bae-403">Namespace for the generated code.</span></span> <span data-ttu-id="10bae-404">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="10bae-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="10bae-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="10bae-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="10bae-406">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="10bae-406">The type of authentication to use.</span></span> <span data-ttu-id="10bae-407">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="10bae-407">The possible values are:</span></span>

  - <span data-ttu-id="10bae-408">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="10bae-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="10bae-409">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10bae-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="10bae-410">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="10bae-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="10bae-411">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="10bae-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="10bae-412">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="10bae-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="10bae-413">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10bae-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="10bae-414">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10bae-415">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-416">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="10bae-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="10bae-417">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10bae-418">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="10bae-419">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="10bae-420">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="10bae-421">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="10bae-422">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="10bae-423">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10bae-424">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="10bae-425">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="10bae-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="10bae-426">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-426">The Client ID for this project.</span></span> <span data-ttu-id="10bae-427">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="10bae-428">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="10bae-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="10bae-429">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="10bae-429">The domain for the directory tenant.</span></span> <span data-ttu-id="10bae-430">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-431">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="10bae-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="10bae-432">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10bae-433">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10bae-434">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="10bae-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="10bae-435">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="10bae-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="10bae-436">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-437">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="10bae-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="10bae-438">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="10bae-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="10bae-439">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-440">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="10bae-441">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="10bae-441">Turns off HTTPS.</span></span> <span data-ttu-id="10bae-442">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10bae-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="10bae-443">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10bae-444">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-445">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="10bae-446">Web</span><span class="sxs-lookup"><span data-stu-id="10bae-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-447">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-448">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-449">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="10bae-450">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-451">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-451">SDK version</span></span> | <span data-ttu-id="10bae-452">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-453">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-454">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="10bae-455">2.1</span><span class="sxs-lookup"><span data-stu-id="10bae-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="10bae-456">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="10bae-457">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="10bae-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="10bae-458">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="10bae-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="10bae-459">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="10bae-459">The type of authentication to use.</span></span> <span data-ttu-id="10bae-460">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="10bae-460">The possible values are:</span></span>

  - <span data-ttu-id="10bae-461">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="10bae-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="10bae-462">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10bae-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="10bae-463">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="10bae-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="10bae-464">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="10bae-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="10bae-465">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="10bae-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="10bae-466">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10bae-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="10bae-467">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10bae-468">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-469">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="10bae-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="10bae-470">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10bae-471">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="10bae-472">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="10bae-473">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="10bae-474">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="10bae-475">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="10bae-476">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10bae-477">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="10bae-478">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="10bae-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="10bae-479">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-479">The Client ID for this project.</span></span> <span data-ttu-id="10bae-480">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="10bae-481">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="10bae-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="10bae-482">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="10bae-482">The domain for the directory tenant.</span></span> <span data-ttu-id="10bae-483">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-484">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="10bae-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="10bae-485">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10bae-486">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10bae-487">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="10bae-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="10bae-488">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="10bae-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="10bae-489">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-490">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="10bae-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="10bae-491">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="10bae-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="10bae-492">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-493">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="10bae-494">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="10bae-494">Turns off HTTPS.</span></span> <span data-ttu-id="10bae-495">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10bae-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="10bae-496">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10bae-497">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-498">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-499">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="10bae-500">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-501">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-501">SDK version</span></span> | <span data-ttu-id="10bae-502">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-503">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-504">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="10bae-505">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="10bae-506">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="10bae-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="10bae-507">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="10bae-508">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="10bae-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="10bae-509">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="10bae-510">angular, react</span><span class="sxs-lookup"><span data-stu-id="10bae-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="10bae-511">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="10bae-511">The type of authentication to use.</span></span> <span data-ttu-id="10bae-512">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="10bae-513">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="10bae-513">The possible values are:</span></span>

  - <span data-ttu-id="10bae-514">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="10bae-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="10bae-515">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10bae-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-516">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-517">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="10bae-518">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="10bae-518">Turns off HTTPS.</span></span> <span data-ttu-id="10bae-519">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="10bae-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="10bae-520">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10bae-521">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-522">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-523">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-524">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="10bae-525">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-526">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-526">SDK version</span></span> | <span data-ttu-id="10bae-527">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-528">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-529">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="10bae-530">2.1</span><span class="sxs-lookup"><span data-stu-id="10bae-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="10bae-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="10bae-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-532">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-533">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-534">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="10bae-535">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-536">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-536">SDK version</span></span> | <span data-ttu-id="10bae-537">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-538">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-539">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="10bae-540">2.1</span><span class="sxs-lookup"><span data-stu-id="10bae-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="10bae-541">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="10bae-542">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="10bae-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="10bae-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="10bae-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="10bae-544">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="10bae-545">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="10bae-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="10bae-546">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="10bae-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="10bae-547">Web-API</span><span class="sxs-lookup"><span data-stu-id="10bae-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="10bae-548">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="10bae-548">The type of authentication to use.</span></span> <span data-ttu-id="10bae-549">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="10bae-549">The possible values are:</span></span>

  - <span data-ttu-id="10bae-550">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="10bae-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="10bae-551">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="10bae-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="10bae-552">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="10bae-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="10bae-553">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="10bae-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="10bae-554">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="10bae-555">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="10bae-556">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="10bae-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="10bae-557">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="10bae-558">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="10bae-559">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="10bae-560">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10bae-561">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="10bae-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="10bae-562">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="10bae-562">The Client ID for this project.</span></span> <span data-ttu-id="10bae-563">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="10bae-564">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="10bae-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="10bae-565">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="10bae-565">The domain for the directory tenant.</span></span> <span data-ttu-id="10bae-566">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="10bae-567">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="10bae-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="10bae-568">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="10bae-569">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="10bae-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="10bae-570">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="10bae-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="10bae-571">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="10bae-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="10bae-572">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="10bae-573">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="10bae-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="10bae-574">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="10bae-574">Turns off HTTPS.</span></span> <span data-ttu-id="10bae-575">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="10bae-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="10bae-576">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10bae-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="10bae-577">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="10bae-578">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="10bae-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="10bae-579">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="10bae-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="10bae-580">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="10bae-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="10bae-581">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="10bae-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="10bae-582">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="10bae-582">SDK version</span></span> | <span data-ttu-id="10bae-583">Standardwert</span><span class="sxs-lookup"><span data-stu-id="10bae-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="10bae-584">3.1</span><span class="sxs-lookup"><span data-stu-id="10bae-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="10bae-585">3.0</span><span class="sxs-lookup"><span data-stu-id="10bae-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="10bae-586">2.1</span><span class="sxs-lookup"><span data-stu-id="10bae-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="10bae-587">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="10bae-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="10bae-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="10bae-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="10bae-589">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="10bae-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="10bae-590">Beispiele</span><span class="sxs-lookup"><span data-stu-id="10bae-590">Examples</span></span>

- <span data-ttu-id="10bae-591">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="10bae-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="10bae-592">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="10bae-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="10bae-593">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="10bae-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="10bae-594">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="10bae-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="10bae-595">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="10bae-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="10bae-596">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="10bae-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="10bae-597">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="10bae-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="10bae-598">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="10bae-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="10bae-599">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="10bae-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="10bae-600">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="10bae-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="10bae-601">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="10bae-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="10bae-602">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="10bae-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="10bae-603">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="10bae-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="10bae-604">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10bae-604">See also</span></span>

- [<span data-ttu-id="10bae-605">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="10bae-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="10bae-606">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="10bae-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="10bae-607">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="10bae-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="10bae-608">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="10bae-608">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
