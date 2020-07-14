---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
no-loc:
- Blazor
- WebAssembly
ms.date: 04/10/2020
ms.openlocfilehash: ec41b3b79ed5eded7c9124d3e4d95c658ee39580
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173119"
---
# <a name="dotnet-new"></a><span data-ttu-id="a4ca8-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="a4ca8-103">dotnet new</span></span>

<span data-ttu-id="a4ca8-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a4ca8-105">name</span><span class="sxs-lookup"><span data-stu-id="a4ca8-105">Name</span></span>

<span data-ttu-id="a4ca8-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a4ca8-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a4ca8-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="a4ca8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-108">Description</span></span>

<span data-ttu-id="a4ca8-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="a4ca8-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="a4ca8-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="a4ca8-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="a4ca8-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="a4ca8-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="a4ca8-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="a4ca8-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="a4ca8-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="a4ca8-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="a4ca8-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="a4ca8-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="a4ca8-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="a4ca8-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="a4ca8-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="a4ca8-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="a4ca8-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="a4ca8-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-125">Templates</span></span>                                    | <span data-ttu-id="a4ca8-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="a4ca8-126">Short name</span></span>                      | <span data-ttu-id="a4ca8-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="a4ca8-127">Language</span></span>     | <span data-ttu-id="a4ca8-128">Tags</span><span class="sxs-lookup"><span data-stu-id="a4ca8-128">Tags</span></span>                                  | <span data-ttu-id="a4ca8-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="a4ca8-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="a4ca8-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-130">Console Application</span></span>                          | [<span data-ttu-id="a4ca8-131">console</span><span class="sxs-lookup"><span data-stu-id="a4ca8-131">console</span></span>](#console)             | <span data-ttu-id="a4ca8-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a4ca8-132">[C#], F#, VB</span></span> | <span data-ttu-id="a4ca8-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="a4ca8-133">Common/Console</span></span>                        | <span data-ttu-id="a4ca8-134">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-134">1.0</span></span>        |
| <span data-ttu-id="a4ca8-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="a4ca8-135">Class library</span></span>                                | [<span data-ttu-id="a4ca8-136">classlib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-136">classlib</span></span>](#classlib)           | <span data-ttu-id="a4ca8-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a4ca8-137">[C#], F#, VB</span></span> | <span data-ttu-id="a4ca8-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="a4ca8-138">Common/Library</span></span>                        | <span data-ttu-id="a4ca8-139">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-139">1.0</span></span>        |
| <span data-ttu-id="a4ca8-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-140">WPF Application</span></span>                              | [<span data-ttu-id="a4ca8-141">wpf</span><span class="sxs-lookup"><span data-stu-id="a4ca8-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="a4ca8-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-142">[C#]</span></span>         | <span data-ttu-id="a4ca8-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="a4ca8-143">Common/WPF</span></span>                            | <span data-ttu-id="a4ca8-144">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-144">3.0</span></span>        |
| <span data-ttu-id="a4ca8-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="a4ca8-145">WPF Class library</span></span>                            | [<span data-ttu-id="a4ca8-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="a4ca8-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-147">[C#]</span></span>         | <span data-ttu-id="a4ca8-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="a4ca8-148">Common/WPF</span></span>                            | <span data-ttu-id="a4ca8-149">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-149">3.0</span></span>        |
| <span data-ttu-id="a4ca8-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="a4ca8-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="a4ca8-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="a4ca8-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-152">[C#]</span></span>         | <span data-ttu-id="a4ca8-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="a4ca8-153">Common/WPF</span></span>                            | <span data-ttu-id="a4ca8-154">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-154">3.0</span></span>        |
| <span data-ttu-id="a4ca8-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="a4ca8-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="a4ca8-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-157">[C#]</span></span>         | <span data-ttu-id="a4ca8-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="a4ca8-158">Common/WPF</span></span>                            | <span data-ttu-id="a4ca8-159">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-159">3.0</span></span>        |
| <span data-ttu-id="a4ca8-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="a4ca8-161">winforms</span><span class="sxs-lookup"><span data-stu-id="a4ca8-161">winforms</span></span>](#winforms)           | <span data-ttu-id="a4ca8-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-162">[C#]</span></span>         | <span data-ttu-id="a4ca8-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="a4ca8-163">Common/WinForms</span></span>                       | <span data-ttu-id="a4ca8-164">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-164">3.0</span></span>        |
| <span data-ttu-id="a4ca8-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="a4ca8-166">winforms</span><span class="sxs-lookup"><span data-stu-id="a4ca8-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="a4ca8-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-167">[C#]</span></span>         | <span data-ttu-id="a4ca8-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="a4ca8-168">Common/WinForms</span></span>                       | <span data-ttu-id="a4ca8-169">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-169">3.0</span></span>        |
| <span data-ttu-id="a4ca8-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="a4ca8-170">Worker Service</span></span>                               | [<span data-ttu-id="a4ca8-171">worker</span><span class="sxs-lookup"><span data-stu-id="a4ca8-171">worker</span></span>](#web-others)           | <span data-ttu-id="a4ca8-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-172">[C#]</span></span>         | <span data-ttu-id="a4ca8-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="a4ca8-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="a4ca8-174">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-174">3.0</span></span>        |
| <span data-ttu-id="a4ca8-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="a4ca8-175">Unit Test Project</span></span>                            | [<span data-ttu-id="a4ca8-176">mstest</span><span class="sxs-lookup"><span data-stu-id="a4ca8-176">mstest</span></span>](#test)                 | <span data-ttu-id="a4ca8-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a4ca8-177">[C#], F#, VB</span></span> | <span data-ttu-id="a4ca8-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="a4ca8-178">Test/MSTest</span></span>                           | <span data-ttu-id="a4ca8-179">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-179">1.0</span></span>        |
| <span data-ttu-id="a4ca8-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="a4ca8-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="a4ca8-181">nunit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="a4ca8-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a4ca8-182">[C#], F#, VB</span></span> | <span data-ttu-id="a4ca8-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-183">Test/NUnit</span></span>                            | <span data-ttu-id="a4ca8-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="a4ca8-184">2.1.400</span></span>    |
| <span data-ttu-id="a4ca8-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="a4ca8-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="a4ca8-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a4ca8-186">[C#], F#, VB</span></span> | <span data-ttu-id="a4ca8-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-187">Test/NUnit</span></span>                            | <span data-ttu-id="a4ca8-188">2.2</span><span class="sxs-lookup"><span data-stu-id="a4ca8-188">2.2</span></span>        |
| <span data-ttu-id="a4ca8-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="a4ca8-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="a4ca8-190">xunit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-190">xunit</span></span>](#test)                  | <span data-ttu-id="a4ca8-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a4ca8-191">[C#], F#, VB</span></span> | <span data-ttu-id="a4ca8-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-192">Test/xUnit</span></span>                            | <span data-ttu-id="a4ca8-193">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-193">1.0</span></span>        |
| <span data-ttu-id="a4ca8-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="a4ca8-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="a4ca8-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-195">[C#]</span></span>         | <span data-ttu-id="a4ca8-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a4ca8-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="a4ca8-197">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-197">3.0</span></span>        |
| <span data-ttu-id="a4ca8-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="a4ca8-198">Razor Page</span></span>                                   | [<span data-ttu-id="a4ca8-199">page</span><span class="sxs-lookup"><span data-stu-id="a4ca8-199">page</span></span>](#page)                   | <span data-ttu-id="a4ca8-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-200">[C#]</span></span>         | <span data-ttu-id="a4ca8-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a4ca8-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="a4ca8-202">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-202">2.0</span></span>        |
| <span data-ttu-id="a4ca8-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="a4ca8-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="a4ca8-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="a4ca8-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="a4ca8-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-205">[C#]</span></span>         | <span data-ttu-id="a4ca8-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a4ca8-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="a4ca8-207">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-207">2.0</span></span>        |
| <span data-ttu-id="a4ca8-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="a4ca8-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="a4ca8-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-209">[C#]</span></span>         | <span data-ttu-id="a4ca8-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a4ca8-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="a4ca8-211">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-211">2.0</span></span>        |
| Blazor<span data-ttu-id="a4ca8-212"> Server-App</span><span class="sxs-lookup"><span data-stu-id="a4ca8-212"> Server App</span></span>                            | [<span data-ttu-id="a4ca8-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="a4ca8-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="a4ca8-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-214">[C#]</span></span>         | <span data-ttu-id="a4ca8-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="a4ca8-215">Web/Blazor</span></span>                            | <span data-ttu-id="a4ca8-216">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-216">3.0</span></span>        |
| Blazor<span data-ttu-id="a4ca8-217"> WebAssembly-App</span><span class="sxs-lookup"><span data-stu-id="a4ca8-217"> WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="a4ca8-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-218">[C#]</span></span>         | <span data-ttu-id="a4ca8-219">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="a4ca8-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="a4ca8-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="a4ca8-220">3.1.300</span></span>    |
| <span data-ttu-id="a4ca8-221">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="a4ca8-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="a4ca8-222">web</span><span class="sxs-lookup"><span data-stu-id="a4ca8-222">web</span></span>](#web)                     | <span data-ttu-id="a4ca8-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a4ca8-223">[C#], F#</span></span>     | <span data-ttu-id="a4ca8-224">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="a4ca8-224">Web/Empty</span></span>                             | <span data-ttu-id="a4ca8-225">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-225">1.0</span></span>        |
| <span data-ttu-id="a4ca8-226">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="a4ca8-227">mvc</span><span class="sxs-lookup"><span data-stu-id="a4ca8-227">mvc</span></span>](#web-options)             | <span data-ttu-id="a4ca8-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a4ca8-228">[C#], F#</span></span>     | <span data-ttu-id="a4ca8-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="a4ca8-229">Web/MVC</span></span>                               | <span data-ttu-id="a4ca8-230">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-230">1.0</span></span>        |
| <span data-ttu-id="a4ca8-231">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="a4ca8-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="a4ca8-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="a4ca8-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="a4ca8-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-233">[C#]</span></span>         | <span data-ttu-id="a4ca8-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="a4ca8-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="a4ca8-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="a4ca8-236">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="a4ca8-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="a4ca8-237">angular</span><span class="sxs-lookup"><span data-stu-id="a4ca8-237">angular</span></span>](#spa)                 | <span data-ttu-id="a4ca8-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-238">[C#]</span></span>         | <span data-ttu-id="a4ca8-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a4ca8-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="a4ca8-240">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-240">2.0</span></span>        |
| <span data-ttu-id="a4ca8-241">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="a4ca8-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="a4ca8-242">react</span><span class="sxs-lookup"><span data-stu-id="a4ca8-242">react</span></span>](#spa)                   | <span data-ttu-id="a4ca8-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-243">[C#]</span></span>         | <span data-ttu-id="a4ca8-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a4ca8-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="a4ca8-245">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-245">2.0</span></span>        |
| <span data-ttu-id="a4ca8-246">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="a4ca8-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="a4ca8-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="a4ca8-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="a4ca8-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-248">[C#]</span></span>         | <span data-ttu-id="a4ca8-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a4ca8-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="a4ca8-250">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-250">2.0</span></span>        |
| <span data-ttu-id="a4ca8-251">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="a4ca8-251">Razor Class Library</span></span>                          | [<span data-ttu-id="a4ca8-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="a4ca8-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-253">[C#]</span></span>         | <span data-ttu-id="a4ca8-254">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="a4ca8-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="a4ca8-255">2.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-255">2.1</span></span>        |
| <span data-ttu-id="a4ca8-256">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="a4ca8-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="a4ca8-257">webapi</span><span class="sxs-lookup"><span data-stu-id="a4ca8-257">webapi</span></span>](#webapi)               | <span data-ttu-id="a4ca8-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a4ca8-258">[C#], F#</span></span>     | <span data-ttu-id="a4ca8-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="a4ca8-259">Web/WebAPI</span></span>                            | <span data-ttu-id="a4ca8-260">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-260">1.0</span></span>        |
| <span data-ttu-id="a4ca8-261">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="a4ca8-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="a4ca8-262">grpc</span><span class="sxs-lookup"><span data-stu-id="a4ca8-262">grpc</span></span>](#web-others)             | <span data-ttu-id="a4ca8-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="a4ca8-263">[C#]</span></span>         | <span data-ttu-id="a4ca8-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="a4ca8-264">Web/gRPC</span></span>                              | <span data-ttu-id="a4ca8-265">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-265">3.0</span></span>        |
| <span data-ttu-id="a4ca8-266">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="a4ca8-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="a4ca8-267">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-267">Config</span></span>                                | <span data-ttu-id="a4ca8-268">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-268">3.0</span></span>        |
| <span data-ttu-id="a4ca8-269">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="a4ca8-269">global.json file</span></span>                             | [<span data-ttu-id="a4ca8-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="a4ca8-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="a4ca8-271">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-271">Config</span></span>                                | <span data-ttu-id="a4ca8-272">2.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-272">2.0</span></span>        |
| <span data-ttu-id="a4ca8-273">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a4ca8-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="a4ca8-274">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-274">Config</span></span>                                | <span data-ttu-id="a4ca8-275">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-275">1.0</span></span>        |
| <span data-ttu-id="a4ca8-276">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="a4ca8-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="a4ca8-277">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-277">Config</span></span>                                | <span data-ttu-id="a4ca8-278">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-278">3.0</span></span>        |
| <span data-ttu-id="a4ca8-279">Web Config</span><span class="sxs-lookup"><span data-stu-id="a4ca8-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="a4ca8-280">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-280">Config</span></span>                                | <span data-ttu-id="a4ca8-281">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-281">1.0</span></span>        |
| <span data-ttu-id="a4ca8-282">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="a4ca8-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="a4ca8-283">Lösung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-283">Solution</span></span>                              | <span data-ttu-id="a4ca8-284">1.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-284">1.0</span></span>        |
| <span data-ttu-id="a4ca8-285">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="a4ca8-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="a4ca8-286">proto</span><span class="sxs-lookup"><span data-stu-id="a4ca8-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="a4ca8-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="a4ca8-287">Web/gRPC</span></span>                              | <span data-ttu-id="a4ca8-288">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="a4ca8-289">Optionen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="a4ca8-290">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="a4ca8-291">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="a4ca8-292">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="a4ca8-293">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="a4ca8-294">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-294">Prints out help for the command.</span></span> <span data-ttu-id="a4ca8-295">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="a4ca8-296">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="a4ca8-297">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a4ca8-298">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="a4ca8-299">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="a4ca8-300">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="a4ca8-301">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="a4ca8-302">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="a4ca8-303">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="a4ca8-304">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="a4ca8-305">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-305">The language of the template to create.</span></span> <span data-ttu-id="a4ca8-306">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="a4ca8-307">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a4ca8-308">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="a4ca8-309">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="a4ca8-310">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="a4ca8-311">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-311">The name for the created output.</span></span> <span data-ttu-id="a4ca8-312">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="a4ca8-313">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="a4ca8-314">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="a4ca8-315">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-315">Location to place the generated output.</span></span> <span data-ttu-id="a4ca8-316">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="a4ca8-317">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-317">Filters templates based on available types.</span></span> <span data-ttu-id="a4ca8-318">Die Werte `project`, `item` und `other` sind vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="a4ca8-319">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a4ca8-320">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="a4ca8-321">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="a4ca8-322">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a4ca8-323">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="a4ca8-324">Beispielsweise funktioniert zwar *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="a4ca8-325">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="a4ca8-326">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="a4ca8-327">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="a4ca8-328">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="a4ca8-329">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="a4ca8-330">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="a4ca8-330">Template options</span></span>

<span data-ttu-id="a4ca8-331">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-331">Each project template may have additional options available.</span></span> <span data-ttu-id="a4ca8-332">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="a4ca8-333">Konsole</span><span class="sxs-lookup"><span data-stu-id="a4ca8-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-334">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-335">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="a4ca8-336">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-337">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-337">SDK version</span></span> | <span data-ttu-id="a4ca8-338">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-339">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-340">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a4ca8-341">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a4ca8-342">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="a4ca8-343">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-343">Not supported for F#.</span></span> <span data-ttu-id="a4ca8-344">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a4ca8-345">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-346">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="a4ca8-347">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="a4ca8-348">classlib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-349">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-350">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="a4ca8-351">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a4ca8-352">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a4ca8-353">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="a4ca8-354">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-354">Not supported for F#.</span></span> <span data-ttu-id="a4ca8-355">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a4ca8-356">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-357">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="a4ca8-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-359">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-360">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="a4ca8-361">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a4ca8-362">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a4ca8-363">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="a4ca8-364">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-365">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="a4ca8-366">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="a4ca8-367">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a4ca8-368">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="a4ca8-369">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-370">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="a4ca8-371">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="a4ca8-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-372">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-373">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="a4ca8-374">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-375">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-376">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="a4ca8-377">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-378">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-379">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="a4ca8-380">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-381">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-381">SDK version</span></span> | <span data-ttu-id="a4ca8-382">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-383">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-384">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="a4ca8-385">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-386">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="a4ca8-387">nunit</span><span class="sxs-lookup"><span data-stu-id="a4ca8-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-388">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="a4ca8-389">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-390">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-390">SDK version</span></span> | <span data-ttu-id="a4ca8-391">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-392">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-393">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a4ca8-394">2.2</span><span class="sxs-lookup"><span data-stu-id="a4ca8-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="a4ca8-395">2.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="a4ca8-396">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a4ca8-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-397">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="a4ca8-398">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="a4ca8-399">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-399">Namespace for the generated code.</span></span> <span data-ttu-id="a4ca8-400">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="a4ca8-401">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="a4ca8-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="a4ca8-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="a4ca8-403">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-403">Namespace for the generated code.</span></span> <span data-ttu-id="a4ca8-404">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="a4ca8-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="a4ca8-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="a4ca8-406">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-406">The type of authentication to use.</span></span> <span data-ttu-id="a4ca8-407">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-407">The possible values are:</span></span>

  - <span data-ttu-id="a4ca8-408">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a4ca8-409">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="a4ca8-410">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="a4ca8-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a4ca8-411">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="a4ca8-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="a4ca8-412">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="a4ca8-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="a4ca8-413">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a4ca8-414">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a4ca8-415">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-416">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a4ca8-417">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a4ca8-418">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="a4ca8-419">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="a4ca8-420">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="a4ca8-421">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="a4ca8-422">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a4ca8-423">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a4ca8-424">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a4ca8-425">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a4ca8-426">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-426">The Client ID for this project.</span></span> <span data-ttu-id="a4ca8-427">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a4ca8-428">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a4ca8-429">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-429">The domain for the directory tenant.</span></span> <span data-ttu-id="a4ca8-430">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-431">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a4ca8-432">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a4ca8-433">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a4ca8-434">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="a4ca8-435">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a4ca8-436">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-437">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a4ca8-438">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a4ca8-439">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-440">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="a4ca8-441">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-441">Turns off HTTPS.</span></span> <span data-ttu-id="a4ca8-442">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a4ca8-443">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a4ca8-444">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-445">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="a4ca8-446">Web</span><span class="sxs-lookup"><span data-stu-id="a4ca8-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-447">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-448">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-449">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a4ca8-450">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-451">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-451">SDK version</span></span> | <span data-ttu-id="a4ca8-452">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-453">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-454">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a4ca8-455">2.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="a4ca8-456">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="a4ca8-457">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="a4ca8-458">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="a4ca8-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="a4ca8-459">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-459">The type of authentication to use.</span></span> <span data-ttu-id="a4ca8-460">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-460">The possible values are:</span></span>

  - <span data-ttu-id="a4ca8-461">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a4ca8-462">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="a4ca8-463">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="a4ca8-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a4ca8-464">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="a4ca8-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="a4ca8-465">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="a4ca8-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="a4ca8-466">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a4ca8-467">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a4ca8-468">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-469">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a4ca8-470">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a4ca8-471">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="a4ca8-472">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="a4ca8-473">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="a4ca8-474">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="a4ca8-475">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a4ca8-476">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a4ca8-477">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a4ca8-478">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a4ca8-479">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-479">The Client ID for this project.</span></span> <span data-ttu-id="a4ca8-480">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a4ca8-481">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a4ca8-482">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-482">The domain for the directory tenant.</span></span> <span data-ttu-id="a4ca8-483">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-484">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a4ca8-485">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a4ca8-486">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a4ca8-487">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="a4ca8-488">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a4ca8-489">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-490">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a4ca8-491">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a4ca8-492">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-493">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="a4ca8-494">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-494">Turns off HTTPS.</span></span> <span data-ttu-id="a4ca8-495">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a4ca8-496">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a4ca8-497">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-498">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-499">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="a4ca8-500">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-501">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-501">SDK version</span></span> | <span data-ttu-id="a4ca8-502">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-503">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-504">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="a4ca8-505">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="a4ca8-506">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="a4ca8-507">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="a4ca8-508">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="a4ca8-509">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="a4ca8-510">angular, react</span><span class="sxs-lookup"><span data-stu-id="a4ca8-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="a4ca8-511">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-511">The type of authentication to use.</span></span> <span data-ttu-id="a4ca8-512">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="a4ca8-513">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-513">The possible values are:</span></span>

  - <span data-ttu-id="a4ca8-514">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a4ca8-515">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-516">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-517">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="a4ca8-518">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-518">Turns off HTTPS.</span></span> <span data-ttu-id="a4ca8-519">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a4ca8-520">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a4ca8-521">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-522">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-523">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-524">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a4ca8-525">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-526">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-526">SDK version</span></span> | <span data-ttu-id="a4ca8-527">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-528">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-529">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a4ca8-530">2.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="a4ca8-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="a4ca8-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-532">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-533">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-534">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a4ca8-535">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-536">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-536">SDK version</span></span> | <span data-ttu-id="a4ca8-537">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-538">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-539">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a4ca8-540">2.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="a4ca8-541">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="a4ca8-542">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="a4ca8-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="a4ca8-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="a4ca8-544">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="a4ca8-545">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="a4ca8-546">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="a4ca8-547">Web-API</span><span class="sxs-lookup"><span data-stu-id="a4ca8-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="a4ca8-548">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-548">The type of authentication to use.</span></span> <span data-ttu-id="a4ca8-549">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-549">The possible values are:</span></span>

  - <span data-ttu-id="a4ca8-550">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="a4ca8-551">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="a4ca8-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="a4ca8-552">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="a4ca8-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="a4ca8-553">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a4ca8-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="a4ca8-554">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a4ca8-555">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a4ca8-556">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="a4ca8-557">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a4ca8-558">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="a4ca8-559">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a4ca8-560">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a4ca8-561">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="a4ca8-562">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-562">The Client ID for this project.</span></span> <span data-ttu-id="a4ca8-563">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a4ca8-564">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="a4ca8-565">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-565">The domain for the directory tenant.</span></span> <span data-ttu-id="a4ca8-566">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a4ca8-567">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="a4ca8-568">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a4ca8-569">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="a4ca8-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a4ca8-570">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="a4ca8-571">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="a4ca8-572">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="a4ca8-573">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="a4ca8-574">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-574">Turns off HTTPS.</span></span> <span data-ttu-id="a4ca8-575">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="a4ca8-576">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="a4ca8-577">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a4ca8-578">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="a4ca8-579">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a4ca8-580">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="a4ca8-581">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="a4ca8-582">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="a4ca8-582">SDK version</span></span> | <span data-ttu-id="a4ca8-583">Standardwert</span><span class="sxs-lookup"><span data-stu-id="a4ca8-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="a4ca8-584">3.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="a4ca8-585">3.0</span><span class="sxs-lookup"><span data-stu-id="a4ca8-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="a4ca8-586">2.1</span><span class="sxs-lookup"><span data-stu-id="a4ca8-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="a4ca8-587">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="a4ca8-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="a4ca8-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="a4ca8-589">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="a4ca8-590">Beispiele</span><span class="sxs-lookup"><span data-stu-id="a4ca8-590">Examples</span></span>

- <span data-ttu-id="a4ca8-591">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="a4ca8-592">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="a4ca8-593">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="a4ca8-594">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="a4ca8-595">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="a4ca8-596">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="a4ca8-597">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="a4ca8-598">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="a4ca8-599">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="a4ca8-600">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a4ca8-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="a4ca8-601">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="a4ca8-602">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="a4ca8-603">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="a4ca8-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="a4ca8-604">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4ca8-604">See also</span></span>

- [<span data-ttu-id="a4ca8-605">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="a4ca8-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="a4ca8-606">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="a4ca8-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="a4ca8-607">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="a4ca8-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="a4ca8-608">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="a4ca8-608">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
