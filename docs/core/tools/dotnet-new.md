---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/04/2020
ms.openlocfilehash: 2ee06c37cd950f3b9771db2f30fe353435641d67
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400590"
---
# <a name="dotnet-new"></a><span data-ttu-id="c24f7-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c24f7-103">dotnet new</span></span>

<span data-ttu-id="c24f7-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="c24f7-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c24f7-105">name</span><span class="sxs-lookup"><span data-stu-id="c24f7-105">Name</span></span>

<span data-ttu-id="c24f7-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c24f7-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c24f7-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c24f7-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="c24f7-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c24f7-108">Description</span></span>

<span data-ttu-id="c24f7-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c24f7-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="c24f7-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="c24f7-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="c24f7-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c24f7-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="c24f7-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="c24f7-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="c24f7-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c24f7-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c24f7-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="c24f7-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c24f7-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="c24f7-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="c24f7-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="c24f7-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="c24f7-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="c24f7-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="c24f7-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="c24f7-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="c24f7-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c24f7-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="c24f7-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="c24f7-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="c24f7-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="c24f7-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="c24f7-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="c24f7-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="c24f7-125">Templates</span></span>                                    | <span data-ttu-id="c24f7-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="c24f7-126">Short name</span></span>                      | <span data-ttu-id="c24f7-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="c24f7-127">Language</span></span>     | <span data-ttu-id="c24f7-128">Tags</span><span class="sxs-lookup"><span data-stu-id="c24f7-128">Tags</span></span>                                  | <span data-ttu-id="c24f7-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="c24f7-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="c24f7-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="c24f7-130">Console Application</span></span>                          | [<span data-ttu-id="c24f7-131">console</span><span class="sxs-lookup"><span data-stu-id="c24f7-131">console</span></span>](#console)             | <span data-ttu-id="c24f7-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-132">[C#], F#, VB</span></span> | <span data-ttu-id="c24f7-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="c24f7-133">Common/Console</span></span>                        | <span data-ttu-id="c24f7-134">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-134">1.0</span></span>        |
| <span data-ttu-id="c24f7-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="c24f7-135">Class library</span></span>                                | [<span data-ttu-id="c24f7-136">classlib</span><span class="sxs-lookup"><span data-stu-id="c24f7-136">classlib</span></span>](#classlib)           | <span data-ttu-id="c24f7-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-137">[C#], F#, VB</span></span> | <span data-ttu-id="c24f7-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="c24f7-138">Common/Library</span></span>                        | <span data-ttu-id="c24f7-139">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-139">1.0</span></span>        |
| <span data-ttu-id="c24f7-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="c24f7-140">WPF Application</span></span>                              | [<span data-ttu-id="c24f7-141">wpf</span><span class="sxs-lookup"><span data-stu-id="c24f7-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="c24f7-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-142">[C#], VB</span></span>     | <span data-ttu-id="c24f7-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c24f7-143">Common/WPF</span></span>                            | <span data-ttu-id="c24f7-144">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="c24f7-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c24f7-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="c24f7-145">WPF Class library</span></span>                            | [<span data-ttu-id="c24f7-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="c24f7-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="c24f7-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-147">[C#], VB</span></span>     | <span data-ttu-id="c24f7-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c24f7-148">Common/WPF</span></span>                            | <span data-ttu-id="c24f7-149">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="c24f7-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c24f7-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="c24f7-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="c24f7-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="c24f7-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="c24f7-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-152">[C#], VB</span></span>     | <span data-ttu-id="c24f7-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c24f7-153">Common/WPF</span></span>                            | <span data-ttu-id="c24f7-154">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="c24f7-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c24f7-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="c24f7-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="c24f7-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="c24f7-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="c24f7-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-157">[C#], VB</span></span>     | <span data-ttu-id="c24f7-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="c24f7-158">Common/WPF</span></span>                            | <span data-ttu-id="c24f7-159">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="c24f7-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c24f7-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="c24f7-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="c24f7-161">winforms</span><span class="sxs-lookup"><span data-stu-id="c24f7-161">winforms</span></span>](#winforms)           | <span data-ttu-id="c24f7-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-162">[C#], VB</span></span>     | <span data-ttu-id="c24f7-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="c24f7-163">Common/WinForms</span></span>                       | <span data-ttu-id="c24f7-164">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="c24f7-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c24f7-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="c24f7-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="c24f7-166">winforms</span><span class="sxs-lookup"><span data-stu-id="c24f7-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="c24f7-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-167">[C#], VB</span></span>     | <span data-ttu-id="c24f7-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="c24f7-168">Common/WinForms</span></span>                       | <span data-ttu-id="c24f7-169">3.0 (5.0 für VB)</span><span class="sxs-lookup"><span data-stu-id="c24f7-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="c24f7-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="c24f7-170">Worker Service</span></span>                               | [<span data-ttu-id="c24f7-171">worker</span><span class="sxs-lookup"><span data-stu-id="c24f7-171">worker</span></span>](#web-others)           | <span data-ttu-id="c24f7-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-172">[C#]</span></span>         | <span data-ttu-id="c24f7-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="c24f7-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="c24f7-174">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-174">3.0</span></span>        |
| <span data-ttu-id="c24f7-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="c24f7-175">Unit Test Project</span></span>                            | [<span data-ttu-id="c24f7-176">mstest</span><span class="sxs-lookup"><span data-stu-id="c24f7-176">mstest</span></span>](#test)                 | <span data-ttu-id="c24f7-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-177">[C#], F#, VB</span></span> | <span data-ttu-id="c24f7-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="c24f7-178">Test/MSTest</span></span>                           | <span data-ttu-id="c24f7-179">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-179">1.0</span></span>        |
| <span data-ttu-id="c24f7-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="c24f7-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="c24f7-181">nunit</span><span class="sxs-lookup"><span data-stu-id="c24f7-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="c24f7-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-182">[C#], F#, VB</span></span> | <span data-ttu-id="c24f7-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c24f7-183">Test/NUnit</span></span>                            | <span data-ttu-id="c24f7-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="c24f7-184">2.1.400</span></span>    |
| <span data-ttu-id="c24f7-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="c24f7-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="c24f7-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-186">[C#], F#, VB</span></span> | <span data-ttu-id="c24f7-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="c24f7-187">Test/NUnit</span></span>                            | <span data-ttu-id="c24f7-188">2.2</span><span class="sxs-lookup"><span data-stu-id="c24f7-188">2.2</span></span>        |
| <span data-ttu-id="c24f7-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="c24f7-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="c24f7-190">xunit</span><span class="sxs-lookup"><span data-stu-id="c24f7-190">xunit</span></span>](#test)                  | <span data-ttu-id="c24f7-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c24f7-191">[C#], F#, VB</span></span> | <span data-ttu-id="c24f7-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="c24f7-192">Test/xUnit</span></span>                            | <span data-ttu-id="c24f7-193">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-193">1.0</span></span>        |
| <span data-ttu-id="c24f7-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="c24f7-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="c24f7-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-195">[C#]</span></span>         | <span data-ttu-id="c24f7-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c24f7-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="c24f7-197">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-197">3.0</span></span>        |
| <span data-ttu-id="c24f7-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="c24f7-198">Razor Page</span></span>                                   | [<span data-ttu-id="c24f7-199">page</span><span class="sxs-lookup"><span data-stu-id="c24f7-199">page</span></span>](#page)                   | <span data-ttu-id="c24f7-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-200">[C#]</span></span>         | <span data-ttu-id="c24f7-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c24f7-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="c24f7-202">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-202">2.0</span></span>        |
| <span data-ttu-id="c24f7-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c24f7-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="c24f7-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="c24f7-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="c24f7-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-205">[C#]</span></span>         | <span data-ttu-id="c24f7-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c24f7-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="c24f7-207">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-207">2.0</span></span>        |
| <span data-ttu-id="c24f7-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c24f7-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="c24f7-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-209">[C#]</span></span>         | <span data-ttu-id="c24f7-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="c24f7-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="c24f7-211">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-211">2.0</span></span>        |
| <span data-ttu-id="c24f7-212">:::no-loc(Blazor)::: Server-App</span><span class="sxs-lookup"><span data-stu-id="c24f7-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="c24f7-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="c24f7-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="c24f7-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-214">[C#]</span></span>         | <span data-ttu-id="c24f7-215">Web/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="c24f7-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="c24f7-216">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-216">3.0</span></span>        |
| <span data-ttu-id="c24f7-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly):::-App</span><span class="sxs-lookup"><span data-stu-id="c24f7-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | [<span data-ttu-id="c24f7-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="c24f7-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="c24f7-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-219">[C#]</span></span>         | <span data-ttu-id="c24f7-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="c24f7-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="c24f7-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="c24f7-221">3.1.300</span></span>    |
| <span data-ttu-id="c24f7-222">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="c24f7-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="c24f7-223">web</span><span class="sxs-lookup"><span data-stu-id="c24f7-223">web</span></span>](#web)                     | <span data-ttu-id="c24f7-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c24f7-224">[C#], F#</span></span>     | <span data-ttu-id="c24f7-225">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="c24f7-225">Web/Empty</span></span>                             | <span data-ttu-id="c24f7-226">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-226">1.0</span></span>        |
| <span data-ttu-id="c24f7-227">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c24f7-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="c24f7-228">mvc</span><span class="sxs-lookup"><span data-stu-id="c24f7-228">mvc</span></span>](#web-options)             | <span data-ttu-id="c24f7-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c24f7-229">[C#], F#</span></span>     | <span data-ttu-id="c24f7-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="c24f7-230">Web/MVC</span></span>                               | <span data-ttu-id="c24f7-231">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-231">1.0</span></span>        |
| <span data-ttu-id="c24f7-232">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="c24f7-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="c24f7-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="c24f7-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="c24f7-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-234">[C#]</span></span>         | <span data-ttu-id="c24f7-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="c24f7-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="c24f7-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="c24f7-237">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="c24f7-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="c24f7-238">angular</span><span class="sxs-lookup"><span data-stu-id="c24f7-238">angular</span></span>](#spa)                 | <span data-ttu-id="c24f7-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-239">[C#]</span></span>         | <span data-ttu-id="c24f7-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c24f7-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c24f7-241">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-241">2.0</span></span>        |
| <span data-ttu-id="c24f7-242">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="c24f7-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="c24f7-243">react</span><span class="sxs-lookup"><span data-stu-id="c24f7-243">react</span></span>](#spa)                   | <span data-ttu-id="c24f7-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-244">[C#]</span></span>         | <span data-ttu-id="c24f7-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c24f7-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c24f7-246">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-246">2.0</span></span>        |
| <span data-ttu-id="c24f7-247">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="c24f7-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="c24f7-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="c24f7-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="c24f7-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-249">[C#]</span></span>         | <span data-ttu-id="c24f7-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="c24f7-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="c24f7-251">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-251">2.0</span></span>        |
| <span data-ttu-id="c24f7-252">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="c24f7-252">Razor Class Library</span></span>                          | [<span data-ttu-id="c24f7-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c24f7-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="c24f7-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-254">[C#]</span></span>         | <span data-ttu-id="c24f7-255">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="c24f7-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="c24f7-256">2.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-256">2.1</span></span>        |
| <span data-ttu-id="c24f7-257">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="c24f7-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="c24f7-258">webapi</span><span class="sxs-lookup"><span data-stu-id="c24f7-258">webapi</span></span>](#webapi)               | <span data-ttu-id="c24f7-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c24f7-259">[C#], F#</span></span>     | <span data-ttu-id="c24f7-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="c24f7-260">Web/WebAPI</span></span>                            | <span data-ttu-id="c24f7-261">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-261">1.0</span></span>        |
| <span data-ttu-id="c24f7-262">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="c24f7-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="c24f7-263">grpc</span><span class="sxs-lookup"><span data-stu-id="c24f7-263">grpc</span></span>](#web-others)             | <span data-ttu-id="c24f7-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="c24f7-264">[C#]</span></span>         | <span data-ttu-id="c24f7-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c24f7-265">Web/gRPC</span></span>                              | <span data-ttu-id="c24f7-266">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-266">3.0</span></span>        |
| <span data-ttu-id="c24f7-267">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="c24f7-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="c24f7-268">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c24f7-268">Config</span></span>                                | <span data-ttu-id="c24f7-269">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-269">3.0</span></span>        |
| <span data-ttu-id="c24f7-270">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="c24f7-270">global.json file</span></span>                             | [<span data-ttu-id="c24f7-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="c24f7-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="c24f7-272">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c24f7-272">Config</span></span>                                | <span data-ttu-id="c24f7-273">2.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-273">2.0</span></span>        |
| <span data-ttu-id="c24f7-274">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="c24f7-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="c24f7-275">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c24f7-275">Config</span></span>                                | <span data-ttu-id="c24f7-276">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-276">1.0</span></span>        |
| <span data-ttu-id="c24f7-277">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="c24f7-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="c24f7-278">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c24f7-278">Config</span></span>                                | <span data-ttu-id="c24f7-279">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-279">3.0</span></span>        |
| <span data-ttu-id="c24f7-280">Web Config</span><span class="sxs-lookup"><span data-stu-id="c24f7-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="c24f7-281">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="c24f7-281">Config</span></span>                                | <span data-ttu-id="c24f7-282">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-282">1.0</span></span>        |
| <span data-ttu-id="c24f7-283">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="c24f7-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="c24f7-284">Lösung</span><span class="sxs-lookup"><span data-stu-id="c24f7-284">Solution</span></span>                              | <span data-ttu-id="c24f7-285">1.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-285">1.0</span></span>        |
| <span data-ttu-id="c24f7-286">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="c24f7-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="c24f7-287">proto</span><span class="sxs-lookup"><span data-stu-id="c24f7-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="c24f7-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="c24f7-288">Web/gRPC</span></span>                              | <span data-ttu-id="c24f7-289">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="c24f7-290">Optionen</span><span class="sxs-lookup"><span data-stu-id="c24f7-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="c24f7-291">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="c24f7-292">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="c24f7-293">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c24f7-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c24f7-294">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="c24f7-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c24f7-295">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="c24f7-295">Prints out help for the command.</span></span> <span data-ttu-id="c24f7-296">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c24f7-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="c24f7-297">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="c24f7-298">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c24f7-299">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="c24f7-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c24f7-300">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="c24f7-301">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="c24f7-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="c24f7-302">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c24f7-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="c24f7-303">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c24f7-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="c24f7-304">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c24f7-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="c24f7-305">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c24f7-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="c24f7-306">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-306">The language of the template to create.</span></span> <span data-ttu-id="c24f7-307">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c24f7-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c24f7-308">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="c24f7-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c24f7-309">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c24f7-310">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="c24f7-311">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="c24f7-312">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c24f7-312">The name for the created output.</span></span> <span data-ttu-id="c24f7-313">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="c24f7-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="c24f7-314">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-314">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="c24f7-315">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-315">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="c24f7-316">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="c24f7-316">Location to place the generated output.</span></span> <span data-ttu-id="c24f7-317">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c24f7-317">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="c24f7-318">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-318">Filters templates based on available types.</span></span> <span data-ttu-id="c24f7-319">Bei `project` und `item` handelt es sich um vordefinierte Werte.</span><span class="sxs-lookup"><span data-stu-id="c24f7-319">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="c24f7-320">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-320">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c24f7-321">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-321">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="c24f7-322">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="c24f7-322">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="c24f7-323">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="c24f7-323">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c24f7-324">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="c24f7-324">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c24f7-325">Beispielsweise funktioniert zwar *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* , jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="c24f7-325">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="c24f7-326">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="c24f7-326">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="c24f7-327">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="c24f7-327">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="c24f7-328">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-328">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="c24f7-329">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="c24f7-329">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="c24f7-330">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-330">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="c24f7-331">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="c24f7-331">Template options</span></span>

<span data-ttu-id="c24f7-332">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="c24f7-332">Each project template may have additional options available.</span></span> <span data-ttu-id="c24f7-333">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="c24f7-333">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="c24f7-334">Konsole</span><span class="sxs-lookup"><span data-stu-id="c24f7-334">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c24f7-335">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-335">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-336">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-336">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c24f7-337">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-337">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-338">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-338">SDK version</span></span> | <span data-ttu-id="c24f7-339">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-339">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-340">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-341">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c24f7-342">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c24f7-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c24f7-343">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c24f7-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c24f7-344">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-344">Not supported for F#.</span></span> <span data-ttu-id="c24f7-345">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c24f7-346">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c24f7-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-347">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="c24f7-348">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="c24f7-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="c24f7-350">classlib</span><span class="sxs-lookup"><span data-stu-id="c24f7-350">classlib</span></span>

- <span data-ttu-id="c24f7-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c24f7-352">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-353">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-353">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c24f7-354">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-354">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c24f7-355">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c24f7-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c24f7-356">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c24f7-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="c24f7-357">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-357">Not supported for F#.</span></span> <span data-ttu-id="c24f7-358">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c24f7-359">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c24f7-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-360">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="c24f7-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="c24f7-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="c24f7-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c24f7-364">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-365">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-365">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c24f7-366">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="c24f7-367">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c24f7-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c24f7-368">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c24f7-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c24f7-369">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c24f7-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-370">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="c24f7-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="c24f7-372">winforms, winformslib</span></span>

- <span data-ttu-id="c24f7-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="c24f7-374">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="c24f7-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="c24f7-375">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="c24f7-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="c24f7-376">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="c24f7-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-377">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="c24f7-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="c24f7-379">worker, grpc</span></span>

- <span data-ttu-id="c24f7-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c24f7-381">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-382">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="c24f7-383">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c24f7-384">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-385">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="c24f7-387">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="c24f7-387">mstest, xunit</span></span>

- <span data-ttu-id="c24f7-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c24f7-389">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-390">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c24f7-391">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-392">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-392">SDK version</span></span> | <span data-ttu-id="c24f7-393">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-394">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-394">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-395">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-395">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c24f7-396">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c24f7-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-397">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-397">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-398">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-398">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="c24f7-399">nunit</span><span class="sxs-lookup"><span data-stu-id="c24f7-399">nunit</span></span>

- <span data-ttu-id="c24f7-400">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-400">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c24f7-401">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-401">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="c24f7-402">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-402">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-403">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-403">SDK version</span></span> | <span data-ttu-id="c24f7-404">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-404">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-405">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-405">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-406">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-406">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c24f7-407">2.2</span><span class="sxs-lookup"><span data-stu-id="c24f7-407">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="c24f7-408">2.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-408">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="c24f7-409">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c24f7-409">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-410">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-410">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-411">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-411">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="c24f7-412">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="c24f7-412">page</span></span>

- <span data-ttu-id="c24f7-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="c24f7-414">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="c24f7-414">Namespace for the generated code.</span></span> <span data-ttu-id="c24f7-415">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-415">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="c24f7-416">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="c24f7-416">Creates the page without a PageModel.</span></span>

<span data-ttu-id="c24f7-417">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-417">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="c24f7-418">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="c24f7-418">viewimports, proto</span></span>

- <span data-ttu-id="c24f7-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="c24f7-420">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="c24f7-420">Namespace for the generated code.</span></span> <span data-ttu-id="c24f7-421">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-421">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c24f7-422">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-422">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="c24f7-423">blazorserver</span><span class="sxs-lookup"><span data-stu-id="c24f7-423">blazorserver</span></span>

- <span data-ttu-id="c24f7-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c24f7-425">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c24f7-425">The type of authentication to use.</span></span> <span data-ttu-id="c24f7-426">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c24f7-426">The possible values are:</span></span>

  - <span data-ttu-id="c24f7-427">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c24f7-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c24f7-428">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c24f7-429">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c24f7-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c24f7-430">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c24f7-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c24f7-431">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="c24f7-431">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c24f7-432">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-432">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-433">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-433">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c24f7-434">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-434">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-435">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-435">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c24f7-436">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-436">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c24f7-437">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-437">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c24f7-438">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-438">The reset password policy ID for this project.</span></span> <span data-ttu-id="c24f7-439">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-439">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c24f7-440">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-440">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c24f7-441">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-441">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-442">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-442">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c24f7-443">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-443">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c24f7-444">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-444">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c24f7-445">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-445">The Client ID for this project.</span></span> <span data-ttu-id="c24f7-446">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-446">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c24f7-447">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-447">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c24f7-448">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c24f7-448">The domain for the directory tenant.</span></span> <span data-ttu-id="c24f7-449">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-450">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-450">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c24f7-451">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-451">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c24f7-452">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-452">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-453">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-453">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c24f7-454">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-454">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c24f7-455">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-456">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-456">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c24f7-457">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c24f7-457">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c24f7-458">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-458">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c24f7-459">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-459">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-460">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-460">Turns off HTTPS.</span></span> <span data-ttu-id="c24f7-461">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c24f7-461">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c24f7-462">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-462">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c24f7-463">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-463">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-464">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-464">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-465">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-465">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="c24f7-466">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="c24f7-466">blazorwasm</span></span>

- <span data-ttu-id="c24f7-467">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-467">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="c24f7-468">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="c24f7-469">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-469">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-470">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-470">SDK version</span></span> | <span data-ttu-id="c24f7-471">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-471">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-472">5.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-472">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="c24f7-473">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-473">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="c24f7-474">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-474">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="c24f7-475">Enthält einen ASP.NET Core-Host für die :::no-loc(WebAssembly):::-App :::no-loc(Blazor):::.</span><span class="sxs-lookup"><span data-stu-id="c24f7-475">Includes an ASP.NET Core host for the :::no-loc(Blazor)::: :::no-loc(WebAssembly)::: app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="c24f7-476">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c24f7-476">The type of authentication to use.</span></span> <span data-ttu-id="c24f7-477">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c24f7-477">The possible values are:</span></span>

  - <span data-ttu-id="c24f7-478">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c24f7-478">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c24f7-479">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-479">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c24f7-480">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c24f7-480">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c24f7-481">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c24f7-481">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="c24f7-482">Die Autorität des OIDC-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="c24f7-482">The authority of the OIDC provider.</span></span> <span data-ttu-id="c24f7-483">Mit der `Individual`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-483">Use with `Individual` authentication.</span></span> <span data-ttu-id="c24f7-484">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-484">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-485">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-485">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c24f7-486">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-486">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-487">Der Standardwert ist `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-487">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c24f7-488">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-488">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c24f7-489">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-489">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-490">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-490">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c24f7-491">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-491">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-492">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-492">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c24f7-493">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-493">The Client ID for this project.</span></span> <span data-ttu-id="c24f7-494">Wird in eigenständigen Szenarien mit der Authentifizierung `IndividualB2C`, `SingleOrg` oder `Individual` verwendet.</span><span class="sxs-lookup"><span data-stu-id="c24f7-494">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="c24f7-495">Der Standardwert ist `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-495">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c24f7-496">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c24f7-496">The domain for the directory tenant.</span></span> <span data-ttu-id="c24f7-497">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-497">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-498">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-498">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="c24f7-499">Der APP-ID-URI für die Server-API, die aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-499">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="c24f7-500">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-500">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-501">Der Standardwert ist `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-501">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="c24f7-502">Die Client-ID für die API, die vom Server gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="c24f7-502">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="c24f7-503">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-503">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-504">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-504">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="c24f7-505">Der API-Bereich, der vom Client angefordert werden muss, um ein Zugriffstoken bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-505">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="c24f7-506">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-506">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-507">Der Standardwert ist `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-507">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c24f7-508">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-508">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c24f7-509">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-509">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-510">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-510">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c24f7-511">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c24f7-511">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c24f7-512">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-512">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c24f7-513">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="c24f7-514">Erzeugt eine progressive Webanwendung (PWA), die Installation und Offlinenutzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-514">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-515">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-515">Turns off HTTPS.</span></span> <span data-ttu-id="c24f7-516">Diese Option gilt nur, wenn `Individual`, `IndividualB2C` oder `SingleOrg` für `--auth` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c24f7-516">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c24f7-517">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c24f7-518">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="c24f7-519">URL der API, die von der Web-App aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-519">URL of the API to call from the web app.</span></span> <span data-ttu-id="c24f7-520">Gilt nur für die Authentifizierung `SingleOrg` oder `IndividualB2C` ohne Angabe eines ASP.NET Core-Hosts.</span><span class="sxs-lookup"><span data-stu-id="c24f7-520">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="c24f7-521">Standardwert: `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-521">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="c24f7-522">Gibt an, ob die Web-App Microsoft Graph aufruft.</span><span class="sxs-lookup"><span data-stu-id="c24f7-522">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="c24f7-523">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-523">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="c24f7-524">Bereiche, die angefordert werden müssen, um die API aus der Web-App aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="c24f7-524">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="c24f7-525">Gilt nur für die Authentifizierung `SingleOrg` oder `IndividualB2C` ohne Angabe eines ASP.NET Core-Hosts.</span><span class="sxs-lookup"><span data-stu-id="c24f7-525">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="c24f7-526">Der Standardwert ist `user.read`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-526">The default is `user.read`.</span></span>

<span data-ttu-id="c24f7-527">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-527">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="c24f7-528">Web-</span><span class="sxs-lookup"><span data-stu-id="c24f7-528">web</span></span>

- <span data-ttu-id="c24f7-529">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-529">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="c24f7-530">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c24f7-531">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-532">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c24f7-533">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-534">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-534">SDK version</span></span> | <span data-ttu-id="c24f7-535">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-536">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-537">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c24f7-538">2.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-538">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c24f7-539">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-540">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-540">Turns off HTTPS.</span></span>

<span data-ttu-id="c24f7-541">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-541">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="c24f7-542">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="c24f7-542">mvc, webapp</span></span>

- <span data-ttu-id="c24f7-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c24f7-544">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c24f7-544">The type of authentication to use.</span></span> <span data-ttu-id="c24f7-545">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c24f7-545">The possible values are:</span></span>

  - <span data-ttu-id="c24f7-546">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c24f7-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c24f7-547">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-547">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="c24f7-548">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c24f7-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c24f7-549">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c24f7-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c24f7-550">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="c24f7-550">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="c24f7-551">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-552">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c24f7-553">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-554">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c24f7-555">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c24f7-556">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-556">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="c24f7-557">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-557">The reset password policy ID for this project.</span></span> <span data-ttu-id="c24f7-558">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-558">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="c24f7-559">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-559">The edit profile policy ID for this project.</span></span> <span data-ttu-id="c24f7-560">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-560">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-561">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-561">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c24f7-562">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-562">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c24f7-563">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-563">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c24f7-564">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-564">The Client ID for this project.</span></span> <span data-ttu-id="c24f7-565">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-565">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c24f7-566">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-566">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c24f7-567">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c24f7-567">The domain for the directory tenant.</span></span> <span data-ttu-id="c24f7-568">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-568">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-569">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-569">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c24f7-570">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-570">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c24f7-571">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-571">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-572">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-572">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="c24f7-573">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-573">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c24f7-574">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-574">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-575">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-575">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c24f7-576">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c24f7-576">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c24f7-577">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-577">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c24f7-578">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-578">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-579">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-579">Turns off HTTPS.</span></span> <span data-ttu-id="c24f7-580">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c24f7-580">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c24f7-581">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-581">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c24f7-582">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-582">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c24f7-583">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-583">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-584">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-584">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="c24f7-585">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-585">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-586">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-586">SDK version</span></span> | <span data-ttu-id="c24f7-587">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-587">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-588">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-588">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-589">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-589">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="c24f7-590">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-590">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="c24f7-591">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="c24f7-591">Includes BrowserLink in the project.</span></span> <span data-ttu-id="c24f7-592">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-592">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="c24f7-593">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="c24f7-593">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="c24f7-594">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-594">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="c24f7-595">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-595">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="c24f7-596">angular, react</span><span class="sxs-lookup"><span data-stu-id="c24f7-596">angular, react</span></span>

- <span data-ttu-id="c24f7-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c24f7-598">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c24f7-598">The type of authentication to use.</span></span> <span data-ttu-id="c24f7-599">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-599">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="c24f7-600">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c24f7-600">The possible values are:</span></span>

  - <span data-ttu-id="c24f7-601">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c24f7-601">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c24f7-602">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-602">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c24f7-603">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="c24f7-604">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-604">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-605">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-605">Turns off HTTPS.</span></span> <span data-ttu-id="c24f7-606">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="c24f7-606">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c24f7-607">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c24f7-608">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-608">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-609">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-609">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c24f7-610">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-610">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-611">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-611">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c24f7-612">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-612">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-613">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-613">SDK version</span></span> | <span data-ttu-id="c24f7-614">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-614">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-615">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-616">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c24f7-617">2.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-617">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="c24f7-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-618">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="c24f7-619">reactredux</span><span class="sxs-lookup"><span data-stu-id="c24f7-619">reactredux</span></span>

- <span data-ttu-id="c24f7-620">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-620">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="c24f7-621">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-621">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c24f7-622">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-622">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-623">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-623">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c24f7-624">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-624">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-625">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-625">SDK version</span></span> | <span data-ttu-id="c24f7-626">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-626">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-627">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-627">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-628">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-628">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c24f7-629">2.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-629">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="c24f7-630">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-630">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-631">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-631">Turns off HTTPS.</span></span>

<span data-ttu-id="c24f7-632">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-632">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="c24f7-633">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="c24f7-633">razorclasslib</span></span>

- <span data-ttu-id="c24f7-634">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-634">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="c24f7-635">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-635">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="c24f7-636">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="c24f7-636">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="c24f7-637">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="c24f7-637">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="c24f7-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-638">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="c24f7-639">Web-API</span><span class="sxs-lookup"><span data-stu-id="c24f7-639">webapi</span></span>

- <span data-ttu-id="c24f7-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="c24f7-641">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="c24f7-641">The type of authentication to use.</span></span> <span data-ttu-id="c24f7-642">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="c24f7-642">The possible values are:</span></span>

  - <span data-ttu-id="c24f7-643">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="c24f7-643">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="c24f7-644">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="c24f7-644">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="c24f7-645">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="c24f7-645">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="c24f7-646">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c24f7-646">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-647">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-647">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c24f7-648">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-648">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c24f7-649">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-649">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="c24f7-650">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-650">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c24f7-651">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-651">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="c24f7-652">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-652">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c24f7-653">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-653">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-654">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-654">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="c24f7-655">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-655">The Client ID for this project.</span></span> <span data-ttu-id="c24f7-656">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-656">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-657">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-657">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="c24f7-658">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="c24f7-658">The domain for the directory tenant.</span></span> <span data-ttu-id="c24f7-659">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-659">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-660">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-660">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="c24f7-661">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-661">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c24f7-662">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="c24f7-662">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c24f7-663">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c24f7-663">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="c24f7-664">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c24f7-664">Allows this application read-access to the directory.</span></span> <span data-ttu-id="c24f7-665">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-665">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="c24f7-666">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="c24f7-666">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="c24f7-667">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c24f7-667">Turns off HTTPS.</span></span> <span data-ttu-id="c24f7-668">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-668">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c24f7-669">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c24f7-669">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="c24f7-670">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-670">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c24f7-671">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="c24f7-671">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c24f7-672">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="c24f7-672">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c24f7-673">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c24f7-673">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="c24f7-674">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-674">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="c24f7-675">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="c24f7-675">SDK version</span></span> | <span data-ttu-id="c24f7-676">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c24f7-676">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="c24f7-677">3.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-677">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="c24f7-678">3.0</span><span class="sxs-lookup"><span data-stu-id="c24f7-678">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="c24f7-679">2.1</span><span class="sxs-lookup"><span data-stu-id="c24f7-679">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="c24f7-680">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="c24f7-680">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c24f7-681">\*\*_</span><span class="sxs-lookup"><span data-stu-id="c24f7-681">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="c24f7-682">globaljson</span><span class="sxs-lookup"><span data-stu-id="c24f7-682">globaljson</span></span>

- <span data-ttu-id="c24f7-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="c24f7-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="c24f7-684">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c24f7-684">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="c24f7-685">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c24f7-685">Examples</span></span>

- <span data-ttu-id="c24f7-686">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="c24f7-686">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="c24f7-687">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="c24f7-687">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="c24f7-688">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-688">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="c24f7-689">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="c24f7-689">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="c24f7-690">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="c24f7-690">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="c24f7-691">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="c24f7-691">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="c24f7-692">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-692">List all templates matching the *we* substring.</span></span> <span data-ttu-id="c24f7-693">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-693">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="c24f7-694">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="c24f7-694">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="c24f7-695">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c24f7-695">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="c24f7-696">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="c24f7-696">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="c24f7-697">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="c24f7-697">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="c24f7-698">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json* , und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="c24f7-698">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="c24f7-699">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c24f7-699">See also</span></span>

- [<span data-ttu-id="c24f7-700">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="c24f7-700">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="c24f7-701">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="c24f7-701">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="c24f7-702">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="c24f7-702">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="c24f7-703">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="c24f7-703">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
