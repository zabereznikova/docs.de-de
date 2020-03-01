---
title: Befehl „dotnet new“
description: Der dotnet new Befehl erstellt neue .NET Core-Projekte basierend auf der angegebenen Vorlage
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157218"
---
# <a name="dotnet-new"></a><span data-ttu-id="5b14f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="5b14f-103">dotnet new</span></span>

<span data-ttu-id="5b14f-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.0 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="5b14f-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="5b14f-105">name</span><span class="sxs-lookup"><span data-stu-id="5b14f-105">Name</span></span>

<span data-ttu-id="5b14f-106">`dotnet new`: Erstellt ein neues Projekt, eine Konfigurationsdatei oder eine Lösung auf Grundlage der angegebenen Vorlage.</span><span class="sxs-lookup"><span data-stu-id="5b14f-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5b14f-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5b14f-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="5b14f-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b14f-108">Description</span></span>

<span data-ttu-id="5b14f-109">Der Befehl `dotnet new` erstellt ein .NET Core-Projekt oder andere Artefakte auf Grundlage einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="5b14f-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="5b14f-110">Der Befehl ruft die [Vorlagen-Engine](https://github.com/dotnet/templating) zum Erstellen der Elemente auf dem Datenträger auf, die auf der angegebenen Vorlage und den Optionen basieren.</span><span class="sxs-lookup"><span data-stu-id="5b14f-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="5b14f-111">Argumente</span><span class="sxs-lookup"><span data-stu-id="5b14f-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="5b14f-112">Die Vorlage, die instanziiert werden soll, wenn der Befehl aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5b14f-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="5b14f-113">Jede Vorlage verfügt möglicherweise über bestimmte Optionen, die Sie übergeben können.</span><span class="sxs-lookup"><span data-stu-id="5b14f-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="5b14f-114">Weitere Informationen finden Sie unter [Vorlagenoptionen](#template-options).</span><span class="sxs-lookup"><span data-stu-id="5b14f-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="5b14f-115">Sie können `dotnet new --list` ausführen, um eine Liste aller installierten Vorlagen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="5b14f-116">Wenn der Wert `TEMPLATE` nicht genau mit dem Text in der Spalte **Vorlagen** oder **Kurzname** in der zurückgegebenen Tabelle übereinstimmt, erfolgt für diese beiden Spalten ein Abgleich von Teilzeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="5b14f-117">Ab .NET Core 3.0 SDK sucht die CLI auf NuGet.org nach Vorlagen, wenn Sie den Befehl `dotnet new` unter den folgenden Bedingungen aufrufen:</span><span class="sxs-lookup"><span data-stu-id="5b14f-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="5b14f-118">Wenn die CLI beim Aufruf von `dotnet new` keine (Teil-) Übereinstimmung mit einer Vorlage finden kann.</span><span class="sxs-lookup"><span data-stu-id="5b14f-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="5b14f-119">Wenn eine neuere Version der Vorlage verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5b14f-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="5b14f-120">In diesem Fall wird das Projekt oder Artefakt erstellt, wobei die CLI Sie über eine aktualisierte Version der Vorlage warnt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="5b14f-121">Der Befehl enthält eine Standardliste mit Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-121">The command contains a default list of templates.</span></span> <span data-ttu-id="5b14f-122">Verwenden Sie `dotnet new -l`, um eine Liste der verfügbaren Vorlagen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="5b14f-123">In der folgenden Tabelle sind die Vorlagen angegeben, die bereits mit dem .NET Core SDK vorinstalliert sind.</span><span class="sxs-lookup"><span data-stu-id="5b14f-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="5b14f-124">Die Standardsprache für die Vorlage wird in den Klammern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="5b14f-125">Klicken Sie auf den Kurznamenlink, um die spezifischen Vorlagenoptionen einzusehen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="5b14f-126">Vorlagen</span><span class="sxs-lookup"><span data-stu-id="5b14f-126">Templates</span></span>                                    | <span data-ttu-id="5b14f-127">Kurzname</span><span class="sxs-lookup"><span data-stu-id="5b14f-127">Short name</span></span>                      | <span data-ttu-id="5b14f-128">Sprache</span><span class="sxs-lookup"><span data-stu-id="5b14f-128">Language</span></span>     | <span data-ttu-id="5b14f-129">Tags</span><span class="sxs-lookup"><span data-stu-id="5b14f-129">Tags</span></span>                                  | <span data-ttu-id="5b14f-130">Eingeführt</span><span class="sxs-lookup"><span data-stu-id="5b14f-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="5b14f-131">Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="5b14f-131">Console Application</span></span>                          | [<span data-ttu-id="5b14f-132">console</span><span class="sxs-lookup"><span data-stu-id="5b14f-132">console</span></span>](#console)             | <span data-ttu-id="5b14f-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b14f-133">[C#], F#, VB</span></span> | <span data-ttu-id="5b14f-134">Common/Console</span><span class="sxs-lookup"><span data-stu-id="5b14f-134">Common/Console</span></span>                        | <span data-ttu-id="5b14f-135">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-135">1.0</span></span>        |
| <span data-ttu-id="5b14f-136">Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5b14f-136">Class library</span></span>                                | [<span data-ttu-id="5b14f-137">classlib</span><span class="sxs-lookup"><span data-stu-id="5b14f-137">classlib</span></span>](#classlib)           | <span data-ttu-id="5b14f-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b14f-138">[C#], F#, VB</span></span> | <span data-ttu-id="5b14f-139">Common/Library</span><span class="sxs-lookup"><span data-stu-id="5b14f-139">Common/Library</span></span>                        | <span data-ttu-id="5b14f-140">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-140">1.0</span></span>        |
| <span data-ttu-id="5b14f-141">WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="5b14f-141">WPF Application</span></span>                              | [<span data-ttu-id="5b14f-142">wpf</span><span class="sxs-lookup"><span data-stu-id="5b14f-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="5b14f-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-143">[C#]</span></span>         | <span data-ttu-id="5b14f-144">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="5b14f-144">Common/WPF</span></span>                            | <span data-ttu-id="5b14f-145">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-145">3.0</span></span>        |
| <span data-ttu-id="5b14f-146">WPF-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5b14f-146">WPF Class library</span></span>                            | [<span data-ttu-id="5b14f-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="5b14f-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="5b14f-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-148">[C#]</span></span>         | <span data-ttu-id="5b14f-149">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="5b14f-149">Common/WPF</span></span>                            | <span data-ttu-id="5b14f-150">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-150">3.0</span></span>        |
| <span data-ttu-id="5b14f-151">WPF-Benutzerdefinierte Steuerelementbibliothek</span><span class="sxs-lookup"><span data-stu-id="5b14f-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="5b14f-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="5b14f-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="5b14f-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-153">[C#]</span></span>         | <span data-ttu-id="5b14f-154">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="5b14f-154">Common/WPF</span></span>                            | <span data-ttu-id="5b14f-155">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-155">3.0</span></span>        |
| <span data-ttu-id="5b14f-156">Bibliothek mit WPF-Benutzersteuerelementen</span><span class="sxs-lookup"><span data-stu-id="5b14f-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="5b14f-157">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="5b14f-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="5b14f-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-158">[C#]</span></span>         | <span data-ttu-id="5b14f-159">Common/WPF</span><span class="sxs-lookup"><span data-stu-id="5b14f-159">Common/WPF</span></span>                            | <span data-ttu-id="5b14f-160">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-160">3.0</span></span>        |
| <span data-ttu-id="5b14f-161">Windows Forms-Anwendung (WinForms)</span><span class="sxs-lookup"><span data-stu-id="5b14f-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="5b14f-162">winforms</span><span class="sxs-lookup"><span data-stu-id="5b14f-162">winforms</span></span>](#winforms)           | <span data-ttu-id="5b14f-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-163">[C#]</span></span>         | <span data-ttu-id="5b14f-164">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="5b14f-164">Common/WinForms</span></span>                       | <span data-ttu-id="5b14f-165">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-165">3.0</span></span>        |
| <span data-ttu-id="5b14f-166">Windows Forms-Klassenbibliothek (WinForms)</span><span class="sxs-lookup"><span data-stu-id="5b14f-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="5b14f-167">winforms</span><span class="sxs-lookup"><span data-stu-id="5b14f-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="5b14f-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-168">[C#]</span></span>         | <span data-ttu-id="5b14f-169">Common/WinForms</span><span class="sxs-lookup"><span data-stu-id="5b14f-169">Common/WinForms</span></span>                       | <span data-ttu-id="5b14f-170">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-170">3.0</span></span>        |
| <span data-ttu-id="5b14f-171">Workerdienst</span><span class="sxs-lookup"><span data-stu-id="5b14f-171">Worker Service</span></span>                               | [<span data-ttu-id="5b14f-172">worker</span><span class="sxs-lookup"><span data-stu-id="5b14f-172">worker</span></span>](#web-others)           | <span data-ttu-id="5b14f-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-173">[C#]</span></span>         | <span data-ttu-id="5b14f-174">Common/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="5b14f-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="5b14f-175">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-175">3.0</span></span>        |
| <span data-ttu-id="5b14f-176">Komponententestprojekt</span><span class="sxs-lookup"><span data-stu-id="5b14f-176">Unit Test Project</span></span>                            | [<span data-ttu-id="5b14f-177">mstest</span><span class="sxs-lookup"><span data-stu-id="5b14f-177">mstest</span></span>](#test)                 | <span data-ttu-id="5b14f-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b14f-178">[C#], F#, VB</span></span> | <span data-ttu-id="5b14f-179">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="5b14f-179">Test/MSTest</span></span>                           | <span data-ttu-id="5b14f-180">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-180">1.0</span></span>        |
| <span data-ttu-id="5b14f-181">NUnit 3-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5b14f-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="5b14f-182">nunit</span><span class="sxs-lookup"><span data-stu-id="5b14f-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="5b14f-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b14f-183">[C#], F#, VB</span></span> | <span data-ttu-id="5b14f-184">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="5b14f-184">Test/NUnit</span></span>                            | <span data-ttu-id="5b14f-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="5b14f-185">2.1.400</span></span>    |
| <span data-ttu-id="5b14f-186">NUnit 3-Testelement</span><span class="sxs-lookup"><span data-stu-id="5b14f-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="5b14f-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b14f-187">[C#], F#, VB</span></span> | <span data-ttu-id="5b14f-188">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="5b14f-188">Test/NUnit</span></span>                            | <span data-ttu-id="5b14f-189">2.2</span><span class="sxs-lookup"><span data-stu-id="5b14f-189">2.2</span></span>        |
| <span data-ttu-id="5b14f-190">xUnit-Testprojekt</span><span class="sxs-lookup"><span data-stu-id="5b14f-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="5b14f-191">xunit</span><span class="sxs-lookup"><span data-stu-id="5b14f-191">xunit</span></span>](#test)                  | <span data-ttu-id="5b14f-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b14f-192">[C#], F#, VB</span></span> | <span data-ttu-id="5b14f-193">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="5b14f-193">Test/xUnit</span></span>                            | <span data-ttu-id="5b14f-194">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-194">1.0</span></span>        |
| <span data-ttu-id="5b14f-195">Razor-Komponente</span><span class="sxs-lookup"><span data-stu-id="5b14f-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="5b14f-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-196">[C#]</span></span>         | <span data-ttu-id="5b14f-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5b14f-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="5b14f-198">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-198">3.0</span></span>        |
| <span data-ttu-id="5b14f-199">Seite „Razor“</span><span class="sxs-lookup"><span data-stu-id="5b14f-199">Razor Page</span></span>                                   | [<span data-ttu-id="5b14f-200">page</span><span class="sxs-lookup"><span data-stu-id="5b14f-200">page</span></span>](#page)                   | <span data-ttu-id="5b14f-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-201">[C#]</span></span>         | <span data-ttu-id="5b14f-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5b14f-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="5b14f-203">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-203">2.0</span></span>        |
| <span data-ttu-id="5b14f-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5b14f-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="5b14f-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="5b14f-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="5b14f-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-206">[C#]</span></span>         | <span data-ttu-id="5b14f-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5b14f-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="5b14f-208">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-208">2.0</span></span>        |
| <span data-ttu-id="5b14f-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5b14f-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="5b14f-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-210">[C#]</span></span>         | <span data-ttu-id="5b14f-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5b14f-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="5b14f-212">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-212">2.0</span></span>        |
| <span data-ttu-id="5b14f-213">Blazor-Server-App</span><span class="sxs-lookup"><span data-stu-id="5b14f-213">Blazor Server App</span></span>                            | [<span data-ttu-id="5b14f-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="5b14f-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="5b14f-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-215">[C#]</span></span>         | <span data-ttu-id="5b14f-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="5b14f-216">Web/Blazor</span></span>                            | <span data-ttu-id="5b14f-217">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-217">3.0</span></span>        |
| <span data-ttu-id="5b14f-218">ASP.NET Core leer</span><span class="sxs-lookup"><span data-stu-id="5b14f-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="5b14f-219">web</span><span class="sxs-lookup"><span data-stu-id="5b14f-219">web</span></span>](#web)                     | <span data-ttu-id="5b14f-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b14f-220">[C#], F#</span></span>     | <span data-ttu-id="5b14f-221">Web/Empty</span><span class="sxs-lookup"><span data-stu-id="5b14f-221">Web/Empty</span></span>                             | <span data-ttu-id="5b14f-222">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-222">1.0</span></span>        |
| <span data-ttu-id="5b14f-223">ASP.NET Core-Web-App (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="5b14f-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="5b14f-224">mvc</span><span class="sxs-lookup"><span data-stu-id="5b14f-224">mvc</span></span>](#web-options)             | <span data-ttu-id="5b14f-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b14f-225">[C#], F#</span></span>     | <span data-ttu-id="5b14f-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="5b14f-226">Web/MVC</span></span>                               | <span data-ttu-id="5b14f-227">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-227">1.0</span></span>        |
| <span data-ttu-id="5b14f-228">ASP.NET Core-Web-App</span><span class="sxs-lookup"><span data-stu-id="5b14f-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="5b14f-229">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="5b14f-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="5b14f-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-230">[C#]</span></span>         | <span data-ttu-id="5b14f-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="5b14f-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="5b14f-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="5b14f-233">ASP.NET Core mit Angular</span><span class="sxs-lookup"><span data-stu-id="5b14f-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="5b14f-234">angular</span><span class="sxs-lookup"><span data-stu-id="5b14f-234">angular</span></span>](#spa)                 | <span data-ttu-id="5b14f-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-235">[C#]</span></span>         | <span data-ttu-id="5b14f-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5b14f-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="5b14f-237">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-237">2.0</span></span>        |
| <span data-ttu-id="5b14f-238">ASP.NET Core mit React.js</span><span class="sxs-lookup"><span data-stu-id="5b14f-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="5b14f-239">react</span><span class="sxs-lookup"><span data-stu-id="5b14f-239">react</span></span>](#spa)                   | <span data-ttu-id="5b14f-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-240">[C#]</span></span>         | <span data-ttu-id="5b14f-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5b14f-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="5b14f-242">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-242">2.0</span></span>        |
| <span data-ttu-id="5b14f-243">ASP.NET Core mit React.js und Redux</span><span class="sxs-lookup"><span data-stu-id="5b14f-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="5b14f-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="5b14f-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="5b14f-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-245">[C#]</span></span>         | <span data-ttu-id="5b14f-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="5b14f-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="5b14f-247">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-247">2.0</span></span>        |
| <span data-ttu-id="5b14f-248">Razor-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="5b14f-248">Razor Class Library</span></span>                          | [<span data-ttu-id="5b14f-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="5b14f-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="5b14f-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-250">[C#]</span></span>         | <span data-ttu-id="5b14f-251">Web/Razor/Library/Razor Class Library</span><span class="sxs-lookup"><span data-stu-id="5b14f-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="5b14f-252">2.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-252">2.1</span></span>        |
| <span data-ttu-id="5b14f-253">ASP.NET Core-Web-API</span><span class="sxs-lookup"><span data-stu-id="5b14f-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="5b14f-254">webapi</span><span class="sxs-lookup"><span data-stu-id="5b14f-254">webapi</span></span>](#webapi)               | <span data-ttu-id="5b14f-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b14f-255">[C#], F#</span></span>     | <span data-ttu-id="5b14f-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="5b14f-256">Web/WebAPI</span></span>                            | <span data-ttu-id="5b14f-257">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-257">1.0</span></span>        |
| <span data-ttu-id="5b14f-258">ASP.NET Core: gRPC-Dienst</span><span class="sxs-lookup"><span data-stu-id="5b14f-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="5b14f-259">grpc</span><span class="sxs-lookup"><span data-stu-id="5b14f-259">grpc</span></span>](#web-others)             | <span data-ttu-id="5b14f-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b14f-260">[C#]</span></span>         | <span data-ttu-id="5b14f-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="5b14f-261">Web/gRPC</span></span>                              | <span data-ttu-id="5b14f-262">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-262">3.0</span></span>        |
| <span data-ttu-id="5b14f-263">Protokollpufferdatei</span><span class="sxs-lookup"><span data-stu-id="5b14f-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="5b14f-264">proto</span><span class="sxs-lookup"><span data-stu-id="5b14f-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="5b14f-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="5b14f-265">Web/gRPC</span></span>                              | <span data-ttu-id="5b14f-266">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-266">3.0</span></span>        |
| <span data-ttu-id="5b14f-267">dotnet: GITIGNORE-Datei</span><span class="sxs-lookup"><span data-stu-id="5b14f-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="5b14f-268">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5b14f-268">Config</span></span>                                | <span data-ttu-id="5b14f-269">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-269">3.0</span></span>        |
| <span data-ttu-id="5b14f-270">global.json-Datei</span><span class="sxs-lookup"><span data-stu-id="5b14f-270">global.json file</span></span>                             | [<span data-ttu-id="5b14f-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="5b14f-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="5b14f-272">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5b14f-272">Config</span></span>                                | <span data-ttu-id="5b14f-273">2.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-273">2.0</span></span>        |
| <span data-ttu-id="5b14f-274">NuGet-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5b14f-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="5b14f-275">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5b14f-275">Config</span></span>                                | <span data-ttu-id="5b14f-276">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-276">1.0</span></span>        |
| <span data-ttu-id="5b14f-277">dotnet: Manifestdatei des lokalen Tools</span><span class="sxs-lookup"><span data-stu-id="5b14f-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="5b14f-278">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5b14f-278">Config</span></span>                                | <span data-ttu-id="5b14f-279">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-279">3.0</span></span>        |
| <span data-ttu-id="5b14f-280">Web Config</span><span class="sxs-lookup"><span data-stu-id="5b14f-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="5b14f-281">Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="5b14f-281">Config</span></span>                                | <span data-ttu-id="5b14f-282">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-282">1.0</span></span>        |
| <span data-ttu-id="5b14f-283">Projektmappendatei</span><span class="sxs-lookup"><span data-stu-id="5b14f-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="5b14f-284">Lösung</span><span class="sxs-lookup"><span data-stu-id="5b14f-284">Solution</span></span>                              | <span data-ttu-id="5b14f-285">1.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="5b14f-286">Optionen</span><span class="sxs-lookup"><span data-stu-id="5b14f-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="5b14f-287">Zeigt eine Zusammenfassung der Vorgänge an, die auftreten, nachdem der angegebene Befehl ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="5b14f-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="5b14f-288">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="5b14f-289">Erzwingt das Generieren von Inhalt, auch wenn dadurch vorhandene Dateien geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b14f-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5b14f-290">Dies ist erforderlich, wenn die ausgewählte Vorlage vorhandene Dateien im Ausgabeverzeichnis überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="5b14f-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5b14f-291">Druckt Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5b14f-291">Prints out help for the command.</span></span> <span data-ttu-id="5b14f-292">Kann für den `dotnet new`-Befehl selbst oder für jede Vorlage aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5b14f-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="5b14f-293">Beispielsweise `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="5b14f-294">Installiert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5b14f-295">Wenn Sie eine Vorabversion eines Vorlagenpakets installieren möchten, müssen Sie die Version im Format `<package-name>::<package-version>` angeben.</span><span class="sxs-lookup"><span data-stu-id="5b14f-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5b14f-296">Standardmäßig übergibt `dotnet new` das Symbol \* für die Version, die die letzte stabile Paketversion darstellt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="5b14f-297">Ein Beispiel finden Sie im Abschnitt [Beispiele](#examples).</span><span class="sxs-lookup"><span data-stu-id="5b14f-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="5b14f-298">Wenn beim Ausführen dieses Befehls bereits eine Version der Vorlage installiert war, wird die Vorlage auf die angegebene Version oder die letzte stabile Version aktualisiert, sofern keine Version angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5b14f-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="5b14f-299">Informationen zum Erstellen von Benutzerdefinierten Vorlagen finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5b14f-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="5b14f-300">Listet Vorlagen auf, die den angegebenen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="5b14f-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="5b14f-301">Listet alle Vorlagen auf, wenn kein Name angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="5b14f-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="5b14f-302">Gibt die Sprache der zu erstellenden Vorlage an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-302">The language of the template to create.</span></span> <span data-ttu-id="5b14f-303">Die akzeptierte Sprache variiert je nach Vorlage (siehe Standardwerte im Abschnitt [Argumente](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="5b14f-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5b14f-304">Für einige Vorlagen nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="5b14f-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5b14f-305">Einige Shells interpretieren `#` als Sonderzeichen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5b14f-306">In diesen Fällen müssen Sie den Sprachparameterwert in Klammern setzen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="5b14f-307">Beispielsweise `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="5b14f-308">Der Name für die erstellte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5b14f-308">The name for the created output.</span></span> <span data-ttu-id="5b14f-309">Wird kein Name angegeben , wird der Name des aktuellen Verzeichnisses verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b14f-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="5b14f-310">Gibt eine NuGet-Quelle an, die bei der Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="5b14f-311">Verfügbar ab .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="5b14f-312">Speicherort für die generierte Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="5b14f-312">Location to place the generated output.</span></span> <span data-ttu-id="5b14f-313">Der Standardwert ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5b14f-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="5b14f-314">Filtert Vorlagen auf Grundlage verfügbarer Typen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-314">Filters templates based on available types.</span></span> <span data-ttu-id="5b14f-315">Vordefinierte Werte sind „project“, „item“ oder „other“.</span><span class="sxs-lookup"><span data-stu-id="5b14f-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="5b14f-316">Deinstalliert ein Vorlagenpaket aus den Angaben für `PATH` oder `NUGET_ID`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5b14f-317">Wenn der Wert `<PATH|NUGET_ID>` nicht angegeben wird, werden alle derzeit installierten Vorlagenpakete und die zugehörigen Vorlagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="5b14f-318">Wenn Sie `NUGET_ID` angeben, schließen Sie die Versionsnummer nicht ein.</span><span class="sxs-lookup"><span data-stu-id="5b14f-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="5b14f-319">Wenn Sie für diese Option keinen Parameter angeben, listet der Befehl die installierten Vorlagen und Details dazu auf.</span><span class="sxs-lookup"><span data-stu-id="5b14f-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5b14f-320">Um eine Vorlage durch einen `PATH` zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="5b14f-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5b14f-321">Beispielsweise funktioniert zwar *C:/Users/\<BENUTZER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *./GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="5b14f-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="5b14f-322">Schließen Sie keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="5b14f-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="5b14f-323">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind, und installiert diese.</span><span class="sxs-lookup"><span data-stu-id="5b14f-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="5b14f-324">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="5b14f-325">Prüft, ob Updates für die zurzeit installierten Vorlagenpakete verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5b14f-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="5b14f-326">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="5b14f-327">Vorlagenoptionen</span><span class="sxs-lookup"><span data-stu-id="5b14f-327">Template options</span></span>

<span data-ttu-id="5b14f-328">Für jede Projektvorlage kann es zusätzliche Optionen geben.</span><span class="sxs-lookup"><span data-stu-id="5b14f-328">Each project template may have additional options available.</span></span> <span data-ttu-id="5b14f-329">Die Core-Vorlagen haben die folgenden zusätzlichen Optionen:</span><span class="sxs-lookup"><span data-stu-id="5b14f-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="5b14f-330">Konsole</span><span class="sxs-lookup"><span data-stu-id="5b14f-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-331">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-332">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="5b14f-333">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-334">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-334">SDK version</span></span> | <span data-ttu-id="5b14f-335">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-336">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-337">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5b14f-338">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5b14f-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5b14f-339">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="5b14f-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="5b14f-340">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-340">Not supported for F#.</span></span> <span data-ttu-id="5b14f-341">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5b14f-342">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="5b14f-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-343">Falls angegeben, erfolgt während der Projekterstellung keine implizite Wiederherstellung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="5b14f-344">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="5b14f-345">classlib</span><span class="sxs-lookup"><span data-stu-id="5b14f-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-346">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-347">Werte: `netcoreapp<version>`, um eine .NET Core-Klassenbibliothek zu erstellen, oder `netstandard<version>`, um eine .NET Standard-Klassenbibliothek zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5b14f-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5b14f-348">Der Standardwert ist `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5b14f-349">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5b14f-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5b14f-350">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="5b14f-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="5b14f-351">Wird für F# nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-351">Not supported for F#.</span></span> <span data-ttu-id="5b14f-352">Verfügbar ab .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5b14f-353">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="5b14f-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-354">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="5b14f-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="5b14f-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-356">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-357">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="5b14f-358">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5b14f-359">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5b14f-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5b14f-360">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="5b14f-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="5b14f-361">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="5b14f-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-362">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="5b14f-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="5b14f-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="5b14f-364">Legt in der erstellten Projektdatei die `LangVersion`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="5b14f-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="5b14f-365">Verwenden Sie beispielsweise `--langVersion 7.3` für C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="5b14f-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="5b14f-366">Eine Liste der C#-Standardversionen finden Sie unter [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="5b14f-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-367">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="5b14f-368">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="5b14f-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-369">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-370">Der Standardwert ist `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="5b14f-371">Verfügbar seit .NET Core 3.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-372">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-373">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a> <span data-ttu-id="5b14f-374">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="5b14f-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-375">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-376">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="5b14f-377">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-378">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-378">SDK version</span></span> | <span data-ttu-id="5b14f-379">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-380">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-381">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="5b14f-382">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5b14f-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-383">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="5b14f-384">nunit</span><span class="sxs-lookup"><span data-stu-id="5b14f-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-385">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="5b14f-386">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-387">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-387">SDK version</span></span> | <span data-ttu-id="5b14f-388">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-389">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-390">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5b14f-391">2.2</span><span class="sxs-lookup"><span data-stu-id="5b14f-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="5b14f-392">2.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="5b14f-393">Ermöglicht das Packen des Projekts mit [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5b14f-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-394">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="5b14f-395">Seite (page)</span><span class="sxs-lookup"><span data-stu-id="5b14f-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="5b14f-396">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="5b14f-396">Namespace for the generated code.</span></span> <span data-ttu-id="5b14f-397">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="5b14f-398">Erstellt die Seite ohne PageModel.</span><span class="sxs-lookup"><span data-stu-id="5b14f-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="5b14f-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="5b14f-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="5b14f-400">Namespace für den generierten Code.</span><span class="sxs-lookup"><span data-stu-id="5b14f-400">Namespace for the generated code.</span></span> <span data-ttu-id="5b14f-401">Der Standardwert ist `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="5b14f-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="5b14f-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5b14f-403">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5b14f-403">The type of authentication to use.</span></span> <span data-ttu-id="5b14f-404">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5b14f-404">The possible values are:</span></span>

  - <span data-ttu-id="5b14f-405">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b14f-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5b14f-406">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5b14f-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="5b14f-407">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5b14f-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="5b14f-408">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5b14f-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="5b14f-409">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="5b14f-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="5b14f-410">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5b14f-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="5b14f-411">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b14f-412">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-413">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="5b14f-414">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b14f-415">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="5b14f-416">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="5b14f-417">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="5b14f-418">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="5b14f-419">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="5b14f-420">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b14f-421">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b14f-422">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="5b14f-423">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-423">The Client ID for this project.</span></span> <span data-ttu-id="5b14f-424">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b14f-425">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="5b14f-426">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="5b14f-426">The domain for the directory tenant.</span></span> <span data-ttu-id="5b14f-427">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-428">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="5b14f-429">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b14f-430">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b14f-431">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="5b14f-432">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5b14f-433">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-434">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="5b14f-435">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5b14f-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b14f-436">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-437">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="5b14f-438">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b14f-438">Turns off HTTPS.</span></span> <span data-ttu-id="5b14f-439">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht für `--auth` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b14f-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5b14f-440">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b14f-441">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-442">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="5b14f-443">Web</span><span class="sxs-lookup"><span data-stu-id="5b14f-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-444">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-445">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-446">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5b14f-447">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-448">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-448">SDK version</span></span> | <span data-ttu-id="5b14f-449">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-450">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-451">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5b14f-452">2.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="5b14f-453">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="5b14f-454">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b14f-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="5b14f-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="5b14f-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5b14f-456">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5b14f-456">The type of authentication to use.</span></span> <span data-ttu-id="5b14f-457">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5b14f-457">The possible values are:</span></span>

  - <span data-ttu-id="5b14f-458">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b14f-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5b14f-459">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5b14f-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="5b14f-460">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5b14f-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="5b14f-461">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5b14f-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="5b14f-462">`MultiOrg`: Organisationauthentifizierung für mehrere Mandanten</span><span class="sxs-lookup"><span data-stu-id="5b14f-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="5b14f-463">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5b14f-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="5b14f-464">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b14f-465">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-466">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="5b14f-467">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b14f-468">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="5b14f-469">Die Richtlinien-ID zum Zurücksetzen des Kennworts für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="5b14f-470">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="5b14f-471">Die Richtlinien-ID zum Bearbeiten des Profils für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="5b14f-472">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="5b14f-473">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b14f-474">Mit der `SingleOrg`- oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b14f-475">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="5b14f-476">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-476">The Client ID for this project.</span></span> <span data-ttu-id="5b14f-477">Mit der `IndividualB2C`-, `SingleOrg`-oder `MultiOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b14f-478">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="5b14f-479">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="5b14f-479">The domain for the directory tenant.</span></span> <span data-ttu-id="5b14f-480">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-481">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="5b14f-482">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b14f-483">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b14f-484">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="5b14f-485">Der Anforderungspfad innerhalb des Basispfads des Umleitungs-URIs der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5b14f-486">Mit der `SingleOrg`- oder `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-487">Der Standardwert ist `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="5b14f-488">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5b14f-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b14f-489">Gilt nur für die `SingleOrg`- oder `MultiOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-490">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="5b14f-491">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b14f-491">Turns off HTTPS.</span></span> <span data-ttu-id="5b14f-492">Diese Option gilt nur, wenn `Individual`, `IndividualB2C`, `SingleOrg` oder `MultiOrg` nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b14f-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5b14f-493">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b14f-494">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-495">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-496">Die Option ist ab .NET Core 3.0 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="5b14f-497">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-498">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-498">SDK version</span></span> | <span data-ttu-id="5b14f-499">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-500">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-501">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="5b14f-502">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="5b14f-503">Schließt BrowserLink in das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="5b14f-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="5b14f-504">Die Option ist nicht in .NET Core 2.2 und 3.1 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="5b14f-505">angular, react</span><span class="sxs-lookup"><span data-stu-id="5b14f-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5b14f-506">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5b14f-506">The type of authentication to use.</span></span> <span data-ttu-id="5b14f-507">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="5b14f-508">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5b14f-508">The possible values are:</span></span>

  - <span data-ttu-id="5b14f-509">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b14f-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5b14f-510">`Individual`: einzelne Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5b14f-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-511">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-512">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="5b14f-513">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b14f-513">Turns off HTTPS.</span></span> <span data-ttu-id="5b14f-514">Diese Option gilt nur, wenn die Authentifizierung `None` ist.</span><span class="sxs-lookup"><span data-stu-id="5b14f-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5b14f-515">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b14f-516">Gilt nur für die `Individual`- oder `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-517">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-518">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-519">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5b14f-520">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-521">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-521">SDK version</span></span> | <span data-ttu-id="5b14f-522">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-523">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-524">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5b14f-525">2.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="5b14f-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="5b14f-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-527">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-528">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-529">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5b14f-530">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-531">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-531">SDK version</span></span> | <span data-ttu-id="5b14f-532">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-533">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-534">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5b14f-535">2.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="5b14f-536">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="5b14f-537">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b14f-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="5b14f-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="5b14f-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="5b14f-539">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="5b14f-540">Unterstützt das Hinzufügen von herkömmlichen Razor-Seiten und -Ansichten sowie von Komponenten zu dieser Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="5b14f-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="5b14f-541">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="5b14f-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="5b14f-542">Web-API</span><span class="sxs-lookup"><span data-stu-id="5b14f-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="5b14f-543">Der zu verwendende Authentifizierungstyp.</span><span class="sxs-lookup"><span data-stu-id="5b14f-543">The type of authentication to use.</span></span> <span data-ttu-id="5b14f-544">Mögliche Werte sind:</span><span class="sxs-lookup"><span data-stu-id="5b14f-544">The possible values are:</span></span>

  - <span data-ttu-id="5b14f-545">`None`: keine Authentifizierung (Standard)</span><span class="sxs-lookup"><span data-stu-id="5b14f-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="5b14f-546">`IndividualB2C`: einzelne Authentifizierung mit Azur AD B2C</span><span class="sxs-lookup"><span data-stu-id="5b14f-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="5b14f-547">`SingleOrg`: Organisationauthentifizierung für einzelne Mandanten</span><span class="sxs-lookup"><span data-stu-id="5b14f-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="5b14f-548">`Windows`: Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5b14f-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="5b14f-549">Die Azure Active Directory B2C-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b14f-550">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b14f-551">Der Standardwert ist `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="5b14f-552">Die ID der Anmelde- und Registrierungsrichtlinie für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b14f-553">Mit der `IndividualB2C`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="5b14f-554">Die Azure Active Directory-Instanz, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b14f-555">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b14f-556">Der Standardwert ist `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="5b14f-557">Die Client-ID für dieses Projekt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-557">The Client ID for this project.</span></span> <span data-ttu-id="5b14f-558">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5b14f-559">Der Standardwert ist `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="5b14f-560">Die Domäne für den Verzeichnismandanten.</span><span class="sxs-lookup"><span data-stu-id="5b14f-560">The domain for the directory tenant.</span></span> <span data-ttu-id="5b14f-561">Mit der `IndividualB2C`- oder `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5b14f-562">Der Standardwert ist `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="5b14f-563">Die Mandanten-ID des Verzeichnisses, mit dem eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b14f-564">Mit der `SingleOrg`-Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="5b14f-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b14f-565">Der Standardwert ist `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b14f-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="5b14f-566">Erteilt der Anwendung Lesezugriff auf das Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5b14f-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b14f-567">Gilt nur für die `SingleOrg`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="5b14f-568">Schließt *launchSettings.json* aus der generierten Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="5b14f-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="5b14f-569">Deaktiviert HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b14f-569">Turns off HTTPS.</span></span> <span data-ttu-id="5b14f-570">`app.UseHsts` und `app.UseHttpsRedirection` werden nicht in `Startup.Configure` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5b14f-571">Diese Option gilt nur, wenn `IndividualB2C` oder `SingleOrg` nicht für die Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5b14f-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="5b14f-572">Gibt an, dass LocalDB statt SQLite verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b14f-573">Gilt nur für die `IndividualB2C`-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b14f-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="5b14f-574">Gibt das [Zielframework](../../standard/frameworks.md) an.</span><span class="sxs-lookup"><span data-stu-id="5b14f-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b14f-575">Die Option ist nicht in .NET Core 2.2 SDK verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b14f-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="5b14f-576">In der folgenden Tabelle sind die Standardwerte entsprechend der von Ihnen verwendeten SDK-Versionsnummer aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="5b14f-577">SDK-Version</span><span class="sxs-lookup"><span data-stu-id="5b14f-577">SDK version</span></span> | <span data-ttu-id="5b14f-578">Standardwert</span><span class="sxs-lookup"><span data-stu-id="5b14f-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="5b14f-579">3.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="5b14f-580">3.0</span><span class="sxs-lookup"><span data-stu-id="5b14f-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="5b14f-581">2.1</span><span class="sxs-lookup"><span data-stu-id="5b14f-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="5b14f-582">Führt während der Projekterstellung keine implizite Wiederherstellung durch.</span><span class="sxs-lookup"><span data-stu-id="5b14f-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="5b14f-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="5b14f-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="5b14f-584">Gibt die .NET Core SDK-Version an, die in der Datei *global.json* verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b14f-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="5b14f-585">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5b14f-585">Examples</span></span>

- <span data-ttu-id="5b14f-586">Erstellen Sie ein C#-Konsolenanwendungsprojekt, indem Sie den Vorlagennamen angeben:</span><span class="sxs-lookup"><span data-stu-id="5b14f-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="5b14f-587">Erstellen Sie ein F#-Konsolenanwendungsprojekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="5b14f-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="5b14f-588">Erstellen Sie im angegebenen Verzeichnis ein .NET Standard-Klassenbibliotheksprojekt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="5b14f-589">Erstellen Sie ein neues ASP.NET Core C# MVC-Projekt im aktuellen Verzeichnis ohne Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="5b14f-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="5b14f-590">Erstellen Sie ein neues xUnit-Projekt:</span><span class="sxs-lookup"><span data-stu-id="5b14f-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="5b14f-591">Listen Sie alle für Single-Page-Webanwendungen (SPA) verfügbaren Vorlagen auf:</span><span class="sxs-lookup"><span data-stu-id="5b14f-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="5b14f-592">Listen Sie alle Vorlagen auf, für die sich eine Übereinstimmung mit der Teilzeichenfolge *we* ergibt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="5b14f-593">Da keine genaue Übereinstimmung gefunden wird, wird ein Teilzeichenfolgen-Abgleich für die Spalten mit dem Kurznamen und dem Namen durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="5b14f-594">Es wird versucht, die Vorlage aufzurufen, für die sich eine Übereinstimmung mit *ng* ergibt.</span><span class="sxs-lookup"><span data-stu-id="5b14f-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="5b14f-595">Wenn keine Einzelübereinstimmung ermittelt werden kann, werden die Vorlagen mit Teilübereinstimmungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="5b14f-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="5b14f-596">Installieren Sie Version 2.0 der SPA-Vorlagen für ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="5b14f-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="5b14f-597">Listen Sie die installierten Vorlagen und Details zu diesen Vorlagen auf, einschließlich Angaben zur Deinstallation:</span><span class="sxs-lookup"><span data-stu-id="5b14f-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="5b14f-598">Erstellen Sie im aktuellen Verzeichnis die Datei *global.json*, und legen Sie die SDK-Version auf 3.1.101 fest:</span><span class="sxs-lookup"><span data-stu-id="5b14f-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="5b14f-599">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b14f-599">See also</span></span>

- [<span data-ttu-id="5b14f-600">Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="5b14f-600">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="5b14f-601">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="5b14f-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="5b14f-602">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="5b14f-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="5b14f-603">Verfügbare Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="5b14f-603">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
