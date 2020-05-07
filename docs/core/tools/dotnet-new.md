---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 04/10/2020
ms.openlocfilehash: 9a68baafa7ac3e6ad2fdc8f1c6e8621d6e15f1ff
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506856"
---
# <a name="dotnet-new"></a><span data-ttu-id="35f4d-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="35f4d-103">dotnet new</span></span>

<span data-ttu-id="35f4d-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="35f4d-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="35f4d-105">name</span><span class="sxs-lookup"><span data-stu-id="35f4d-105">Name</span></span>

<span data-ttu-id="35f4d-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="35f4d-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="35f4d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="35f4d-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="35f4d-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35f4d-108">Description</span></span>

<span data-ttu-id="35f4d-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="35f4d-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="35f4d-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="35f4d-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="35f4d-111">Implizite Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="35f4d-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="35f4d-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="35f4d-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="35f4d-113">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="35f4d-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="35f4d-114">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="35f4d-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="35f4d-115">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="35f4d-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="35f4d-116">Sie können `dotnet new --list` oder `dotnet new -l` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="35f4d-117">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="35f4d-118">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="35f4d-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="35f4d-119">Wenn die CLI beim Aufruf von `dotnet new` keine Übereinstimmung oder Teilübereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="35f4d-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="35f4d-120">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="35f4d-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="35f4d-121">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="35f4d-122">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="35f4d-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="35f4d-123">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="35f4d-124">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="35f4d-125">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="35f4d-125">Templates</span></span>                                    | <span data-ttu-id="35f4d-126">Kurzname</span><span class="sxs-lookup"><span data-stu-id="35f4d-126">Short name</span></span>                      | <span data-ttu-id="35f4d-127">Sprache</span><span class="sxs-lookup"><span data-stu-id="35f4d-127">Language</span></span>     | <span data-ttu-id="35f4d-128">Tags</span><span class="sxs-lookup"><span data-stu-id="35f4d-128">Tags</span></span>                                  | <span data-ttu-id="35f4d-129">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="35f4d-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="35f4d-130">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="35f4d-130">Console Application</span></span>                          | [<span data-ttu-id="35f4d-131">console</span><span class="sxs-lookup"><span data-stu-id="35f4d-131">console</span></span>](#console)             | <span data-ttu-id="35f4d-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="35f4d-132">[C#], F#, VB</span></span> | <span data-ttu-id="35f4d-133">Common/Console</span><span class="sxs-lookup"><span data-stu-id="35f4d-133">Common/Console</span></span>                        | <span data-ttu-id="35f4d-134">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-134">1.0</span></span>        |
| <span data-ttu-id="35f4d-135">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="35f4d-135">Class library</span></span>                                | [<span data-ttu-id="35f4d-136">classlib</span><span class="sxs-lookup"><span data-stu-id="35f4d-136">classlib</span></span>](#classlib)           | <span data-ttu-id="35f4d-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="35f4d-137">[C#], F#, VB</span></span> | <span data-ttu-id="35f4d-138">Common/Library</span><span class="sxs-lookup"><span data-stu-id="35f4d-138">Common/Library</span></span>                        | <span data-ttu-id="35f4d-139">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-139">1.0</span></span>        |
| <span data-ttu-id="35f4d-140">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="35f4d-140">WPF Application</span></span>                              | [<span data-ttu-id="35f4d-141">wpf</span><span class="sxs-lookup"><span data-stu-id="35f4d-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="35f4d-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-142">[C#]</span></span>         | <span data-ttu-id="35f4d-143">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="35f4d-143">Common/WPF</span></span>                            | <span data-ttu-id="35f4d-144">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-144">3.0</span></span>        |
| <span data-ttu-id="35f4d-145">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="35f4d-145">WPF Class library</span></span>                            | [<span data-ttu-id="35f4d-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="35f4d-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="35f4d-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-147">[C#]</span></span>         | <span data-ttu-id="35f4d-148">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="35f4d-148">Common/WPF</span></span>                            | <span data-ttu-id="35f4d-149">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-149">3.0</span></span>        |
| <span data-ttu-id="35f4d-150">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="35f4d-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="35f4d-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="35f4d-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="35f4d-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-152">[C#]</span></span>         | <span data-ttu-id="35f4d-153">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="35f4d-153">Common/WPF</span></span>                            | <span data-ttu-id="35f4d-154">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-154">3.0</span></span>        |
| <span data-ttu-id="35f4d-155">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="35f4d-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="35f4d-156">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="35f4d-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="35f4d-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-157">[C#]</span></span>         | <span data-ttu-id="35f4d-158">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="35f4d-158">Common/WPF</span></span>                            | <span data-ttu-id="35f4d-159">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-159">3.0</span></span>        |
| <span data-ttu-id="35f4d-160">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="35f4d-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="35f4d-161">winforms</span><span class="sxs-lookup"><span data-stu-id="35f4d-161">winforms</span></span>](#winforms)           | <span data-ttu-id="35f4d-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-162">[C#]</span></span>         | <span data-ttu-id="35f4d-163">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="35f4d-163">Common/WinForms</span></span>                       | <span data-ttu-id="35f4d-164">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-164">3.0</span></span>        |
| <span data-ttu-id="35f4d-165">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="35f4d-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="35f4d-166">winforms</span><span class="sxs-lookup"><span data-stu-id="35f4d-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="35f4d-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-167">[C#]</span></span>         | <span data-ttu-id="35f4d-168">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="35f4d-168">Common/WinForms</span></span>                       | <span data-ttu-id="35f4d-169">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-169">3.0</span></span>        |
| <span data-ttu-id="35f4d-170">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="35f4d-170">Worker Service</span></span>                               | [<span data-ttu-id="35f4d-171">worker</span><span class="sxs-lookup"><span data-stu-id="35f4d-171">worker</span></span>](#web-others)           | <span data-ttu-id="35f4d-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-172">[C#]</span></span>         | <span data-ttu-id="35f4d-173">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="35f4d-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="35f4d-174">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-174">3.0</span></span>        |
| <span data-ttu-id="35f4d-175">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="35f4d-175">Unit Test Project</span></span>                            | [<span data-ttu-id="35f4d-176">mstest</span><span class="sxs-lookup"><span data-stu-id="35f4d-176">mstest</span></span>](#test)                 | <span data-ttu-id="35f4d-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="35f4d-177">[C#], F#, VB</span></span> | <span data-ttu-id="35f4d-178">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="35f4d-178">Test/MSTest</span></span>                           | <span data-ttu-id="35f4d-179">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-179">1.0</span></span>        |
| <span data-ttu-id="35f4d-180">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="35f4d-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="35f4d-181">nunit</span><span class="sxs-lookup"><span data-stu-id="35f4d-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="35f4d-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="35f4d-182">[C#], F#, VB</span></span> | <span data-ttu-id="35f4d-183">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="35f4d-183">Test/NUnit</span></span>                            | <span data-ttu-id="35f4d-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="35f4d-184">2.1.400</span></span>    |
| <span data-ttu-id="35f4d-185">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="35f4d-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="35f4d-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="35f4d-186">[C#], F#, VB</span></span> | <span data-ttu-id="35f4d-187">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="35f4d-187">Test/NUnit</span></span>                            | <span data-ttu-id="35f4d-188">2.2</span><span class="sxs-lookup"><span data-stu-id="35f4d-188">2.2</span></span>        |
| <span data-ttu-id="35f4d-189">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="35f4d-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="35f4d-190">xunit</span><span class="sxs-lookup"><span data-stu-id="35f4d-190">xunit</span></span>](#test)                  | <span data-ttu-id="35f4d-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="35f4d-191">[C#], F#, VB</span></span> | <span data-ttu-id="35f4d-192">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="35f4d-192">Test/xUnit</span></span>                            | <span data-ttu-id="35f4d-193">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-193">1.0</span></span>        |
| <span data-ttu-id="35f4d-194">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="35f4d-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="35f4d-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-195">[C#]</span></span>         | <span data-ttu-id="35f4d-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35f4d-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="35f4d-197">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-197">3.0</span></span>        |
| <span data-ttu-id="35f4d-198">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="35f4d-198">Razor Page</span></span>                                   | [<span data-ttu-id="35f4d-199">page</span><span class="sxs-lookup"><span data-stu-id="35f4d-199">page</span></span>](#page)                   | <span data-ttu-id="35f4d-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-200">[C#]</span></span>         | <span data-ttu-id="35f4d-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35f4d-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="35f4d-202">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-202">2.0</span></span>        |
| <span data-ttu-id="35f4d-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="35f4d-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="35f4d-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="35f4d-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="35f4d-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-205">[C#]</span></span>         | <span data-ttu-id="35f4d-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35f4d-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="35f4d-207">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-207">2.0</span></span>        |
| <span data-ttu-id="35f4d-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="35f4d-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="35f4d-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-209">[C#]</span></span>         | <span data-ttu-id="35f4d-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="35f4d-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="35f4d-211">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-211">2.0</span></span>        |
| <span data-ttu-id="35f4d-212">Blazor-Server-App</span><span class="sxs-lookup"><span data-stu-id="35f4d-212">Blazor Server App</span></span>                            | [<span data-ttu-id="35f4d-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="35f4d-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="35f4d-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-214">[C#]</span></span>         | <span data-ttu-id="35f4d-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="35f4d-215">Web/Blazor</span></span>                            | <span data-ttu-id="35f4d-216">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-216">3.0</span></span>        |
| <span data-ttu-id="35f4d-217">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="35f4d-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="35f4d-218">web</span><span class="sxs-lookup"><span data-stu-id="35f4d-218">web</span></span>](#web)                     | <span data-ttu-id="35f4d-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="35f4d-219">[C#], F#</span></span>     | <span data-ttu-id="35f4d-220">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="35f4d-220">Web/Empty</span></span>                             | <span data-ttu-id="35f4d-221">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-221">1.0</span></span>        |
| <span data-ttu-id="35f4d-222">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="35f4d-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="35f4d-223">mvc</span><span class="sxs-lookup"><span data-stu-id="35f4d-223">mvc</span></span>](#web-options)             | <span data-ttu-id="35f4d-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="35f4d-224">[C#], F#</span></span>     | <span data-ttu-id="35f4d-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="35f4d-225">Web/MVC</span></span>                               | <span data-ttu-id="35f4d-226">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-226">1.0</span></span>        |
| <span data-ttu-id="35f4d-227">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="35f4d-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="35f4d-228">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="35f4d-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="35f4d-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-229">[C#]</span></span>         | <span data-ttu-id="35f4d-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="35f4d-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="35f4d-231">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="35f4d-232">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="35f4d-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="35f4d-233">angular</span><span class="sxs-lookup"><span data-stu-id="35f4d-233">angular</span></span>](#spa)                 | <span data-ttu-id="35f4d-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-234">[C#]</span></span>         | <span data-ttu-id="35f4d-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="35f4d-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="35f4d-236">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-236">2.0</span></span>        |
| <span data-ttu-id="35f4d-237">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="35f4d-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="35f4d-238">react</span><span class="sxs-lookup"><span data-stu-id="35f4d-238">react</span></span>](#spa)                   | <span data-ttu-id="35f4d-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-239">[C#]</span></span>         | <span data-ttu-id="35f4d-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="35f4d-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="35f4d-241">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-241">2.0</span></span>        |
| <span data-ttu-id="35f4d-242">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="35f4d-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="35f4d-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="35f4d-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="35f4d-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-244">[C#]</span></span>         | <span data-ttu-id="35f4d-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="35f4d-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="35f4d-246">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-246">2.0</span></span>        |
| <span data-ttu-id="35f4d-247">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="35f4d-247">Razor Class Library</span></span>                          | [<span data-ttu-id="35f4d-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="35f4d-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="35f4d-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-249">[C#]</span></span>         | <span data-ttu-id="35f4d-250">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="35f4d-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="35f4d-251">2.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-251">2.1</span></span>        |
| <span data-ttu-id="35f4d-252">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="35f4d-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="35f4d-253">webapi</span><span class="sxs-lookup"><span data-stu-id="35f4d-253">webapi</span></span>](#webapi)               | <span data-ttu-id="35f4d-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="35f4d-254">[C#], F#</span></span>     | <span data-ttu-id="35f4d-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="35f4d-255">Web/WebAPI</span></span>                            | <span data-ttu-id="35f4d-256">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-256">1.0</span></span>        |
| <span data-ttu-id="35f4d-257">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="35f4d-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="35f4d-258">grpc</span><span class="sxs-lookup"><span data-stu-id="35f4d-258">grpc</span></span>](#web-others)             | <span data-ttu-id="35f4d-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="35f4d-259">[C#]</span></span>         | <span data-ttu-id="35f4d-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="35f4d-260">Web/gRPC</span></span>                              | <span data-ttu-id="35f4d-261">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-261">3.0</span></span>        |
| <span data-ttu-id="35f4d-262">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="35f4d-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="35f4d-263">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="35f4d-263">Config</span></span>                                | <span data-ttu-id="35f4d-264">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-264">3.0</span></span>        |
| <span data-ttu-id="35f4d-265">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="35f4d-265">global.json file</span></span>                             | [<span data-ttu-id="35f4d-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="35f4d-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="35f4d-267">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="35f4d-267">Config</span></span>                                | <span data-ttu-id="35f4d-268">2.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-268">2.0</span></span>        |
| <span data-ttu-id="35f4d-269">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="35f4d-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="35f4d-270">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="35f4d-270">Config</span></span>                                | <span data-ttu-id="35f4d-271">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-271">1.0</span></span>        |
| <span data-ttu-id="35f4d-272">Dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="35f4d-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="35f4d-273">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="35f4d-273">Config</span></span>                                | <span data-ttu-id="35f4d-274">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-274">3.0</span></span>        |
| <span data-ttu-id="35f4d-275">Web Config</span><span class="sxs-lookup"><span data-stu-id="35f4d-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="35f4d-276">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="35f4d-276">Config</span></span>                                | <span data-ttu-id="35f4d-277">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-277">1.0</span></span>        |
| <span data-ttu-id="35f4d-278">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="35f4d-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="35f4d-279">Lösung</span><span class="sxs-lookup"><span data-stu-id="35f4d-279">Solution</span></span>                              | <span data-ttu-id="35f4d-280">1.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-280">1.0</span></span>        |
| <span data-ttu-id="35f4d-281">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="35f4d-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="35f4d-282">proto</span><span class="sxs-lookup"><span data-stu-id="35f4d-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="35f4d-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="35f4d-283">Web/gRPC</span></span>                              | <span data-ttu-id="35f4d-284">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="35f4d-285">Optionen</span><span class="sxs-lookup"><span data-stu-id="35f4d-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="35f4d-286">Es wird eine Zusammenfassung dazu angezeigt, was passiert, wenn der jeweilige Befehl ausgeführt wird und sich eine Vorlagenerstellung ergibt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="35f4d-287">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="35f4d-288">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="35f4d-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="35f4d-289">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="35f4d-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="35f4d-290">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="35f4d-290">Prints out help for the command.</span></span> <span data-ttu-id="35f4d-291">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="35f4d-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="35f4d-292">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="35f4d-293">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="35f4d-294">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="35f4d-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="35f4d-295">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="35f4d-296">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="35f4d-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="35f4d-297">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="35f4d-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="35f4d-298">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="35f4d-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="35f4d-299">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="35f4d-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="35f4d-300">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="35f4d-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="35f4d-301">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-301">The language of the template to create.</span></span> <span data-ttu-id="35f4d-302">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="35f4d-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="35f4d-303">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="35f4d-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="35f4d-304">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="35f4d-305">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="35f4d-306">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="35f4d-307">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="35f4d-307">The name for the created output.</span></span> <span data-ttu-id="35f4d-308">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="35f4d-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="35f4d-309">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="35f4d-310">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="35f4d-311">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="35f4d-311">Location to place the generated output.</span></span> <span data-ttu-id="35f4d-312">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35f4d-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="35f4d-313">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-313">Filters templates based on available types.</span></span> <span data-ttu-id="35f4d-314">Die Werte `project`, `item` und `other` sind vordefiniert.</span><span class="sxs-lookup"><span data-stu-id="35f4d-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="35f4d-315">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="35f4d-316">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="35f4d-317">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="35f4d-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="35f4d-318">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="35f4d-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="35f4d-319">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="35f4d-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="35f4d-320">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="35f4d-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="35f4d-321">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="35f4d-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="35f4d-322">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="35f4d-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="35f4d-323">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="35f4d-324">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35f4d-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="35f4d-325">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="35f4d-326">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="35f4d-326">Template options</span></span>

<span data-ttu-id="35f4d-327">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="35f4d-327">Each project template may have additional options available.</span></span> <span data-ttu-id="35f4d-328">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="35f4d-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="35f4d-329">Konsole</span><span class="sxs-lookup"><span data-stu-id="35f4d-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-330">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-331">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="35f4d-332">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-333">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-333">SDK version</span></span> | <span data-ttu-id="35f4d-334">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-335">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-336">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="35f4d-337">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="35f4d-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="35f4d-338">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="35f4d-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="35f4d-339">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-339">Not supported for F#.</span></span> <span data-ttu-id="35f4d-340">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="35f4d-341">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="35f4d-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-342">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="35f4d-343">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="35f4d-344">classlib</span><span class="sxs-lookup"><span data-stu-id="35f4d-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-345">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-346">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="35f4d-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="35f4d-347">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="35f4d-348">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="35f4d-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="35f4d-349">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="35f4d-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="35f4d-350">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-350">Not supported for F#.</span></span> <span data-ttu-id="35f4d-351">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="35f4d-352">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="35f4d-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-353">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="35f4d-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="35f4d-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-355">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-356">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="35f4d-357">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="35f4d-358">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="35f4d-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="35f4d-359">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="35f4d-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="35f4d-360">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="35f4d-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-361">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="35f4d-362">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="35f4d-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="35f4d-363">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="35f4d-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="35f4d-364">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="35f4d-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="35f4d-365">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="35f4d-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-366">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="35f4d-367">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="35f4d-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-368">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-369">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="35f4d-370">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-371">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-372">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="35f4d-373">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="35f4d-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-374">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-375">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="35f4d-376">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-377">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-377">SDK version</span></span> | <span data-ttu-id="35f4d-378">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-379">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-380">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="35f4d-381">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="35f4d-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-382">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="35f4d-383">nunit</span><span class="sxs-lookup"><span data-stu-id="35f4d-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-384">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="35f4d-385">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-386">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-386">SDK version</span></span> | <span data-ttu-id="35f4d-387">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-388">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-389">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="35f4d-390">2.2</span><span class="sxs-lookup"><span data-stu-id="35f4d-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="35f4d-391">2.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="35f4d-392">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="35f4d-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-393">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="35f4d-394">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="35f4d-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="35f4d-395">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="35f4d-395">Namespace for the generated code.</span></span> <span data-ttu-id="35f4d-396">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="35f4d-397">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="35f4d-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="35f4d-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="35f4d-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="35f4d-399">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="35f4d-399">Namespace for the generated code.</span></span> <span data-ttu-id="35f4d-400">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="35f4d-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="35f4d-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="35f4d-402">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="35f4d-402">The type of authentication to use.</span></span> <span data-ttu-id="35f4d-403">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35f4d-403">The possible values are:</span></span>

  - <span data-ttu-id="35f4d-404">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="35f4d-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="35f4d-405">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f4d-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="35f4d-406">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="35f4d-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="35f4d-407">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="35f4d-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="35f4d-408">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="35f4d-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="35f4d-409">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f4d-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="35f4d-410">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="35f4d-411">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-412">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="35f4d-413">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="35f4d-414">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="35f4d-415">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="35f4d-416">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="35f4d-417">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="35f4d-418">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="35f4d-419">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="35f4d-420">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="35f4d-421">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="35f4d-422">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-422">The Client ID for this project.</span></span> <span data-ttu-id="35f4d-423">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="35f4d-424">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="35f4d-425">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="35f4d-425">The domain for the directory tenant.</span></span> <span data-ttu-id="35f4d-426">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-427">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="35f4d-428">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="35f4d-429">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="35f4d-430">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="35f4d-431">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="35f4d-432">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-433">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="35f4d-434">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35f4d-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="35f4d-435">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-436">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="35f4d-437">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35f4d-437">Turns off HTTPS.</span></span> <span data-ttu-id="35f4d-438">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35f4d-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="35f4d-439">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="35f4d-440">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-441">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="35f4d-442">Web</span><span class="sxs-lookup"><span data-stu-id="35f4d-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-443">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-444">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-445">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="35f4d-446">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-447">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-447">SDK version</span></span> | <span data-ttu-id="35f4d-448">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-449">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-450">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="35f4d-451">2.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="35f4d-452">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="35f4d-453">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35f4d-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="35f4d-454">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="35f4d-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="35f4d-455">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="35f4d-455">The type of authentication to use.</span></span> <span data-ttu-id="35f4d-456">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35f4d-456">The possible values are:</span></span>

  - <span data-ttu-id="35f4d-457">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="35f4d-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="35f4d-458">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f4d-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="35f4d-459">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="35f4d-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="35f4d-460">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="35f4d-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="35f4d-461">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="35f4d-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="35f4d-462">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f4d-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="35f4d-463">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="35f4d-464">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-465">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="35f4d-466">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="35f4d-467">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="35f4d-468">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="35f4d-469">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="35f4d-470">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="35f4d-471">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="35f4d-472">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="35f4d-473">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="35f4d-474">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="35f4d-475">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-475">The Client ID for this project.</span></span> <span data-ttu-id="35f4d-476">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="35f4d-477">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="35f4d-478">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="35f4d-478">The domain for the directory tenant.</span></span> <span data-ttu-id="35f4d-479">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-480">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="35f4d-481">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="35f4d-482">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="35f4d-483">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="35f4d-484">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="35f4d-485">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-486">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="35f4d-487">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35f4d-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="35f4d-488">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-489">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="35f4d-490">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35f4d-490">Turns off HTTPS.</span></span> <span data-ttu-id="35f4d-491">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35f4d-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="35f4d-492">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="35f4d-493">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-494">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-495">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="35f4d-496">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-497">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-497">SDK version</span></span> | <span data-ttu-id="35f4d-498">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-499">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-500">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="35f4d-501">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="35f4d-502">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="35f4d-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="35f4d-503">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="35f4d-504">Bestimmt, ob das Projekt zur Verwendung der [Razor-Runtimekompilierung](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debugbuilds konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="35f4d-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="35f4d-505">Die Option ist ab .NET Core SDK 3.1.201 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="35f4d-506">angular, react</span><span class="sxs-lookup"><span data-stu-id="35f4d-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="35f4d-507">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="35f4d-507">The type of authentication to use.</span></span> <span data-ttu-id="35f4d-508">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="35f4d-509">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35f4d-509">The possible values are:</span></span>

  - <span data-ttu-id="35f4d-510">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="35f4d-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="35f4d-511">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f4d-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-512">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-513">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="35f4d-514">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35f4d-514">Turns off HTTPS.</span></span> <span data-ttu-id="35f4d-515">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="35f4d-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="35f4d-516">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="35f4d-517">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-518">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-519">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-520">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="35f4d-521">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-522">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-522">SDK version</span></span> | <span data-ttu-id="35f4d-523">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-524">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-525">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="35f4d-526">2.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="35f4d-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="35f4d-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-528">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-529">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-530">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="35f4d-531">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-532">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-532">SDK version</span></span> | <span data-ttu-id="35f4d-533">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-534">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-535">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="35f4d-536">2.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="35f4d-537">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="35f4d-538">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35f4d-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="35f4d-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="35f4d-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="35f4d-540">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="35f4d-541">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="35f4d-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="35f4d-542">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="35f4d-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="35f4d-543">Web-API</span><span class="sxs-lookup"><span data-stu-id="35f4d-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="35f4d-544">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="35f4d-544">The type of authentication to use.</span></span> <span data-ttu-id="35f4d-545">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="35f4d-545">The possible values are:</span></span>

  - <span data-ttu-id="35f4d-546">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="35f4d-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="35f4d-547">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="35f4d-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="35f4d-548">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="35f4d-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="35f4d-549">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="35f4d-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="35f4d-550">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="35f4d-551">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="35f4d-552">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="35f4d-553">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="35f4d-554">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="35f4d-555">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="35f4d-556">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="35f4d-557">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="35f4d-558">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-558">The Client ID for this project.</span></span> <span data-ttu-id="35f4d-559">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="35f4d-560">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="35f4d-561">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="35f4d-561">The domain for the directory tenant.</span></span> <span data-ttu-id="35f4d-562">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="35f4d-563">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="35f4d-564">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="35f4d-565">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="35f4d-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="35f4d-566">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="35f4d-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="35f4d-567">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="35f4d-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="35f4d-568">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="35f4d-569">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="35f4d-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="35f4d-570">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="35f4d-570">Turns off HTTPS.</span></span> <span data-ttu-id="35f4d-571">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="35f4d-572">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="35f4d-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="35f4d-573">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="35f4d-574">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="35f4d-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="35f4d-575">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="35f4d-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="35f4d-576">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="35f4d-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="35f4d-577">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="35f4d-578">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="35f4d-578">SDK version</span></span> | <span data-ttu-id="35f4d-579">Standardwert</span><span class="sxs-lookup"><span data-stu-id="35f4d-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="35f4d-580">3.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="35f4d-581">3.0</span><span class="sxs-lookup"><span data-stu-id="35f4d-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="35f4d-582">2.1</span><span class="sxs-lookup"><span data-stu-id="35f4d-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="35f4d-583">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="35f4d-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="35f4d-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="35f4d-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="35f4d-585">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="35f4d-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="35f4d-586">Beispiele</span><span class="sxs-lookup"><span data-stu-id="35f4d-586">Examples</span></span>

- <span data-ttu-id="35f4d-587">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="35f4d-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="35f4d-588">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="35f4d-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="35f4d-589">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="35f4d-590">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="35f4d-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="35f4d-591">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="35f4d-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="35f4d-592">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="35f4d-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="35f4d-593">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="35f4d-594">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="35f4d-595">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="35f4d-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="35f4d-596">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="35f4d-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="35f4d-597">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="35f4d-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="35f4d-598">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="35f4d-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="35f4d-599">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="35f4d-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="35f4d-600">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35f4d-600">See also</span></span>

- [<span data-ttu-id="35f4d-601">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="35f4d-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="35f4d-602">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="35f4d-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="35f4d-603">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="35f4d-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="35f4d-604">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="35f4d-604">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
