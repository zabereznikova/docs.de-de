---
title: Erstellen einer Elementvorlage für „dotnet new“ – .NET Core-CLI
description: Hier erfahren Sie, wie Sie eine Elementvorlage für den Befehl „dotnet new“ erstellen. Elementvorlagen können beliebig viele Dateien enthalten.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5f4038e863d9bb59df470d3516c08fd2ad29c078
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503554"
---
# <a name="tutorial-create-an-item-template"></a><span data-ttu-id="7dfb5-104">Tutorial: Erstellen einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-104">Tutorial: Create an item template</span></span>

<span data-ttu-id="7dfb5-105">Mit .NET Core können Sie Vorlagen erstellen und bereitstellen, die Projekte, Dateien und sogar Ressourcen generieren.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-105">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="7dfb5-106">Dieses Tutorial ist der erste Teil einer Reihe, die zeigt, wie Sie Vorlagen für die Verwendung mit dem Befehl `dotnet new` erstellen, installieren und deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-106">This tutorial is part one of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="7dfb5-107">In diesem Teil der Reihe wird Folgendes vermittelt:</span><span class="sxs-lookup"><span data-stu-id="7dfb5-107">In this part of the series, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="7dfb5-108">Erstellen einer Klasse für eine Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-108">Create a class for an item template</span></span>
> * <span data-ttu-id="7dfb5-109">Erstellen des Konfigurationsordners und der Konfigurationsdatei der Vorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-109">Create the template config folder and file</span></span>
> * <span data-ttu-id="7dfb5-110">Installieren einer Vorlage unter Verwendung eines Dateipfads</span><span class="sxs-lookup"><span data-stu-id="7dfb5-110">Install a template from a file path</span></span>
> * <span data-ttu-id="7dfb5-111">Testen einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-111">Test an item template</span></span>
> * <span data-ttu-id="7dfb5-112">Deinstallieren einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-112">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7dfb5-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7dfb5-113">Prerequisites</span></span>

* <span data-ttu-id="7dfb5-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) oder eine höhere Version</span><span class="sxs-lookup"><span data-stu-id="7dfb5-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
* <span data-ttu-id="7dfb5-115">Lesen Sie den Referenzartikel [Benutzerdefinierte Vorlagen für dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="7dfb5-115">Read the reference article [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

  <span data-ttu-id="7dfb5-116">Der Referenzartikel enthält grundlegende Informationen zu Vorlagen und zu deren Erstellung.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-116">The reference article explains the basics about templates and how they're put together.</span></span> <span data-ttu-id="7dfb5-117">Einige dieser Informationen werden hier wiederholt.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-117">Some of this information will be reiterated here.</span></span>

* <span data-ttu-id="7dfb5-118">Öffnen Sie ein Terminal, und navigieren Sie zum Ordner _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-118">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-the-required-folders"></a><span data-ttu-id="7dfb5-119">Erstellen der erforderlichen Ordner</span><span class="sxs-lookup"><span data-stu-id="7dfb5-119">Create the required folders</span></span>

<span data-ttu-id="7dfb5-120">In dieser Reihe werden ein Arbeitsordner als Vorlagenquelle und ein Testordner zum Testen Ihrer Vorlagen verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-120">This series uses a "working folder" where your template source is contained and a "testing folder" used to test your templates.</span></span> <span data-ttu-id="7dfb5-121">Der Arbeitsordner und der Testordner müssen sich im gleichen übergeordneten Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-121">The working folder and testing folder should be under the same parent folder.</span></span>

<span data-ttu-id="7dfb5-122">Erstellen Sie zunächst den übergeordneten Ordner. Dieser kann einen beliebigen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-122">First, create the parent folder, the name does not matter.</span></span> <span data-ttu-id="7dfb5-123">Erstellen Sie anschließend einen Unterordner mit dem Namen _working_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-123">Then, create a subfolder named _working_.</span></span> <span data-ttu-id="7dfb5-124">Erstellen Sie im Ordner _working_ einen Unterordner mit dem Namen _templates_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-124">Inside of the _working_ folder, create a subfolder named _templates_.</span></span>

<span data-ttu-id="7dfb5-125">Erstellen Sie als Nächstes unter dem übergeordneten Ordner einen Ordner mit dem Namen _test_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-125">Next, create a folder under the parent folder named _test_.</span></span> <span data-ttu-id="7dfb5-126">Die Ordnerstruktur sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-126">The folder structure should look like the following.</span></span>

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a><span data-ttu-id="7dfb5-127">Erstellen einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-127">Create an item template</span></span>

<span data-ttu-id="7dfb5-128">Eine Elementvorlage ist eine spezielle Art von Vorlage, die eine oder mehrere Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-128">An item template is a specific type of template that contains one or more files.</span></span> <span data-ttu-id="7dfb5-129">Diese Art von Vorlage ist hilfreich, wenn Sie beispielsweise eine Konfigurations-, Code- oder Projektmappendatei generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-129">These types of templates are useful when you want to generate something like a config, code, or solution file.</span></span> <span data-ttu-id="7dfb5-130">In diesem Beispiel wird eine Klasse erstellt, die dem Zeichenfolgentyp eine Erweiterungsmethode hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-130">In this example, you'll create a class that adds an extension method to the string type.</span></span>

<span data-ttu-id="7dfb5-131">Navigieren Sie in Ihrem Terminal zum Ordner _working\templates_, und erstellen Sie einen neuen Unterordner mit dem Namen _extensions_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-131">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _extensions_.</span></span> <span data-ttu-id="7dfb5-132">Öffnen Sie den Ordner.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-132">Enter the folder.</span></span>

```console
working
└───templates
    └───extensions
```

<span data-ttu-id="7dfb5-133">Erstellen Sie eine neue Datei namens _CommonExtensions.cs_, und öffnen Sie sie mit Ihrem bevorzugten Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-133">Create a new file named _CommonExtensions.cs_ and open it with your favorite text editor.</span></span> <span data-ttu-id="7dfb5-134">Diese Klasse stellt eine Erweiterungsmethode namens `Reverse` bereit, die den Inhalt einer Zeichenfolge umkehrt.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-134">This class will provide an extension method named `Reverse` that reverses the contents of a string.</span></span> <span data-ttu-id="7dfb5-135">Fügen Sie den folgenden Code ein, und speichern Sie die Datei:</span><span class="sxs-lookup"><span data-stu-id="7dfb5-135">Paste in the following code and save the file:</span></span>

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

<span data-ttu-id="7dfb5-136">Nachdem Sie den Inhalt der Vorlage erstellt haben, müssen Sie als Nächstes im Stammordner der Vorlage die Vorlagenkonfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-136">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="7dfb5-137">Erstellen der Vorlagenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="7dfb5-137">Create the template config</span></span>

<span data-ttu-id="7dfb5-138">Vorlagen werden in .NET Core anhand eines speziellen Ordners und einer Konfigurationsdatei am Stamm Ihrer Vorlage erkannt.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-138">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="7dfb5-139">In diesem Tutorial befindet sich Ihr Vorlagenordner unter _working\templates\extensions_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-139">In this tutorial, your template folder is located at _working\templates\extensions_.</span></span>

<span data-ttu-id="7dfb5-140">Bei der Vorlagenerstellung werden mit Ausnahme des speziellen Konfigurationsordners alle Dateien und Ordner aus dem Vorlagenordner in die Vorlage eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-140">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="7dfb5-141">Dieser Konfigurationsordner heißt _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-141">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="7dfb5-142">Erstellen Sie zunächst einen neuen Unterordner namens _.template.config_, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-142">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="7dfb5-143">Erstellen Sie anschließend eine neue Datei namens _template.json_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-143">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="7dfb5-144">Ihre Ordnerstruktur sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="7dfb5-144">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

<span data-ttu-id="7dfb5-145">Öffnen Sie die Datei _template.json_ mit Ihrem bevorzugten Text-Editor, fügen Sie den folgenden JSON-Code ein, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-145">Open the _template.json_ with your favorite text editor and paste in the following JSON code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

<span data-ttu-id="7dfb5-146">Diese Konfigurationsdatei enthält alle Einstellungen für Ihre Vorlage.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-146">This config file contains all the settings for your template.</span></span> <span data-ttu-id="7dfb5-147">Neben Grundeinstellungen wie `name` und `shortName` enthält die Datei auch einen auf `item` festgelegten Wert vom Typ `tags/type`.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-147">You can see the basic settings, such as `name` and `shortName`, but there's also a `tags/type` value that is set to `item`.</span></span> <span data-ttu-id="7dfb5-148">Dadurch wird die Vorlage als Elementvorlage kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-148">This categorizes your template as an item template.</span></span> <span data-ttu-id="7dfb5-149">Sie können eine beliebige Art von Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-149">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="7dfb5-150">Die Werte `item` und `project` sind allgemeine Namen, die von .NET Core empfohlen werden, damit Benutzer mühelos nach der Art der gesuchten Vorlage filtern können.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-150">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="7dfb5-151">Das Element `classifications` stellt die Spalte **Tags** dar, die angezeigt wird, wenn Sie `dotnet new` ausführen und eine Vorlagenliste abrufen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-151">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="7dfb5-152">Benutzer können auch anhand von Klassifizierungstags suchen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-152">Users can also search based on classification tags.</span></span> <span data-ttu-id="7dfb5-153">Die Eigenschaft `tags` in der JSON-Datei darf nicht mit der Tagliste `classifications` verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-153">Don't confuse the `tags` property in the \*.json file with the `classifications` tags list.</span></span> <span data-ttu-id="7dfb5-154">Hierbei handelt es sich um zwei unterschiedliche Dinge, die leider ähnlich heißen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-154">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="7dfb5-155">Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="7dfb5-155">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="7dfb5-156">Weitere Informationen zur Datei *template.json* finden Sie im [Wiki zur Erstellung von .NET-Vorlagen](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="7dfb5-156">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="7dfb5-157">Nachdem Sie nun über eine gültige Datei vom Typ _.template.config/template.json_ verfügen, ist die Vorlage installationsbereit.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-157">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="7dfb5-158">Navigieren Sie in Ihrem Terminal zum Ordner _extensions_, und führen Sie den folgenden Befehl aus, um die Vorlage aus dem aktuellen Ordner zu installieren:</span><span class="sxs-lookup"><span data-stu-id="7dfb5-158">In your terminal, navigate to the  _extensions_ folder and run the following command to install the template located at the current folder:</span></span>

* <span data-ttu-id="7dfb5-159">**Unter Windows:** `dotnet new -i .\`</span><span class="sxs-lookup"><span data-stu-id="7dfb5-159">**On Windows**: `dotnet new -i .\`</span></span>
* <span data-ttu-id="7dfb5-160">**Unter Linux oder macOS:** `dotnet new -i ./`</span><span class="sxs-lookup"><span data-stu-id="7dfb5-160">**On Linux or macOS**: `dotnet new -i ./`</span></span>

<span data-ttu-id="7dfb5-161">Dieser Befehl gibt eine Liste mit den installierten Vorlagen aus. Darin sollte nun auch Ihre Vorlage enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-161">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a><span data-ttu-id="7dfb5-162">Testen der Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-162">Test the item template</span></span>

<span data-ttu-id="7dfb5-163">Testen Sie als Nächstes Ihre installierte Elementvorlage.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-163">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="7dfb5-164">Navigieren Sie zum Ordner _test/_ , und erstellen Sie mithilfe des Befehls `dotnet new console` eine neue Konsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-164">Navigate to the _test/_ folder and create a new console application with `dotnet new console`.</span></span> <span data-ttu-id="7dfb5-165">Dadurch wird ein funktionierendes Projekt generiert, das Sie mühelos mit dem Befehl `dotnet run` testen können.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-165">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="7dfb5-166">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-166">You get output similar to the following.</span></span>

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

<span data-ttu-id="7dfb5-167">Führen Sie das Projekt mit Folgendem aus.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-167">Run the project with.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="7dfb5-168">Sie erhalten die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-168">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="7dfb5-169">Führen Sie `dotnet new stringext` aus, um _CommonExtensions.cs_ auf der Grundlage der Vorlage zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-169">Next, run `dotnet new stringext` to generate the _CommonExtensions.cs_ from the template.</span></span>

```dotnetcli
dotnet new stringext
```

<span data-ttu-id="7dfb5-170">Sie erhalten die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-170">You get the following output.</span></span>

```console
The template "Example templates: string extensions" was created successfully.
```

<span data-ttu-id="7dfb5-171">Ändern Sie den Code in _Program.cs_, um die Zeichenfolge `"Hello World"` mit der von der Vorlage bereitgestellten Erweiterungsmethode umzukehren.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-171">Change the code in _Program.cs_ to reverse the `"Hello World"` string with the extension method provided by the template.</span></span>

```csharp
Console.WriteLine("Hello World!".Reverse());
```

<span data-ttu-id="7dfb5-172">Führen Sie das Programm erneut aus. Das Ergebnis ist nun umgekehrt:</span><span class="sxs-lookup"><span data-stu-id="7dfb5-172">Run the program again and you'll see that the result is reversed.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="7dfb5-173">Sie erhalten die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-173">You get the following output.</span></span>

```console
!dlroW olleH
```

<span data-ttu-id="7dfb5-174">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="7dfb5-174">Congratulations!</span></span> <span data-ttu-id="7dfb5-175">Sie haben eine Elementvorlage mit .NET Core erstellt und bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-175">You created and deployed an item template with .NET Core.</span></span> <span data-ttu-id="7dfb5-176">Zur Vorbereitung auf den nächsten Teil der Tutorialreihe muss die von Ihnen erstellte Vorlage deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-176">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="7dfb5-177">Löschen Sie außerdem auch alle Dateien aus dem Ordner _test_.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-177">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="7dfb5-178">Dadurch erhalten Sie eine bereinigte Umgebung, die für den nächsten Hauptabschnitt dieses Tutorials bereit ist.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-178">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

## <a name="uninstall-the-template"></a><span data-ttu-id="7dfb5-179">Deinstallieren der Vorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-179">Uninstall the template</span></span>

<span data-ttu-id="7dfb5-180">Da Sie die Vorlage unter Verwendung eines Dateipfads installiert haben, muss sie mit dem **absoluten** Dateipfad deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-180">Because you installed the template by file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="7dfb5-181">Mithilfe des Befehls `dotnet new -u` können Sie eine Liste der installierten Vorlagen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-181">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="7dfb5-182">Ihre Vorlage sollte am Ende der Liste aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-182">Your template should be listed last.</span></span> <span data-ttu-id="7dfb5-183">Führen Sie den Befehl `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` mit dem angegebenen Pfad aus, um Ihre Vorlage zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-183">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="7dfb5-184">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-184">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="7dfb5-185">Führen Sie den folgenden Befehl aus, um die Vorlage zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-185">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a><span data-ttu-id="7dfb5-186">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7dfb5-186">Next steps</span></span>

<span data-ttu-id="7dfb5-187">In diesem Tutorial haben Sie eine Elementvorlage erstellt.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-187">In this tutorial, you created an item template.</span></span> <span data-ttu-id="7dfb5-188">Im nächsten Teil dieser Tutorialreihe erfahren Sie, wie Sie eine Projektvorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="7dfb5-188">To learn how to create a project template, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7dfb5-189">Tutorial: Erstellen einer Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="7dfb5-189">Create a project template</span></span>](cli-templates-create-project-template.md)
