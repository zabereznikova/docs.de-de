---
title: Erstellen einer Projektvorlage für „dotnet new“
description: Hier erfahren Sie, wie Sie eine Projektvorlage für den Befehl „dotnet new“ erstellen.
author: adegeo
ms.date: 12/11/2020
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: ed40cfd303c70c7b8f198a0f5b593bf1e1ebeaf8
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513132"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="a630b-103">Tutorial: Erstellen einer Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="a630b-104">Mit .NET können Sie Vorlagen erstellen und bereitstellen, die Projekte, Dateien und sogar Ressourcen generieren.</span><span class="sxs-lookup"><span data-stu-id="a630b-104">With .NET, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="a630b-105">Dieses Tutorial ist der zweite Teil einer Reihe, die zeigt, wie Sie Vorlagen für die Verwendung mit dem Befehl `dotnet new` erstellen, installieren und deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a630b-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="a630b-106">In diesem Teil der Reihe wird Folgendes vermittelt:</span><span class="sxs-lookup"><span data-stu-id="a630b-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="a630b-107">Erstellen der Ressourcen einer Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="a630b-108">Erstellen des Konfigurationsordners und der Konfigurationsdatei der Vorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="a630b-109">Installieren einer Vorlage unter Verwendung eines Dateipfads</span><span class="sxs-lookup"><span data-stu-id="a630b-109">Install a template from a file path</span></span>
> * <span data-ttu-id="a630b-110">Testen einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-110">Test an item template</span></span>
> * <span data-ttu-id="a630b-111">Deinstallieren einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a630b-112">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a630b-112">Prerequisites</span></span>

* <span data-ttu-id="a630b-113">Absolvieren Sie [Teil 1](cli-templates-create-item-template.md) dieser Tutorialreihe.</span><span class="sxs-lookup"><span data-stu-id="a630b-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="a630b-114">Öffnen Sie ein Terminal, und navigieren Sie zum Ordner _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="a630b-114">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="a630b-115">Erstellen einer Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-115">Create a project template</span></span>

<span data-ttu-id="a630b-116">Projektvorlagen ermöglichen die Erstellung sofort einsatzbereiter Projekte, sodass Benutzer ganz einfach mit einer funktionierenden Codegrundlage beginnen können.</span><span class="sxs-lookup"><span data-stu-id="a630b-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="a630b-117">.NET umfasst einige Projektvorlagen – beispielsweise eine Konsolenanwendung und eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="a630b-117">.NET includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="a630b-118">In diesem Beispiel erfahren Sie, wie Sie ein neues Konsolenprojekt erstellen, das C# 9.0 aktiviert und einen Einstiegspunkt vom Typ `async main` erzeugt.</span><span class="sxs-lookup"><span data-stu-id="a630b-118">In this example, you'll create a new console project that enables C# 9.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="a630b-119">Navigieren Sie in Ihrem Terminal zum Ordner _working\templates_, und erstellen Sie einen neuen Unterordner mit dem Namen _consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="a630b-119">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="a630b-120">Öffnen Sie den Unterordner, und führen Sie `dotnet new console` aus, um die Standardkonsolenanwendung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a630b-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="a630b-121">Die von dieser Vorlage erstellten Dateien müssen bearbeitet werden, um eine neue Vorlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a630b-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="a630b-122">Ändern von „Program.cs“</span><span class="sxs-lookup"><span data-stu-id="a630b-122">Modify Program.cs</span></span>

<span data-ttu-id="a630b-123">Öffnen Sie die Datei _program.cs_.</span><span class="sxs-lookup"><span data-stu-id="a630b-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="a630b-124">Da das Konsolenprojekt keinen asynchronen Einstiegspunkt verwendet, fügen wir einen hinzu.</span><span class="sxs-lookup"><span data-stu-id="a630b-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="a630b-125">Ändern Sie Ihren Code wie folgt, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="a630b-125">Change your code to the following and save the file.</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 9.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="a630b-126">Ändern von „consoleasync.csproj“</span><span class="sxs-lookup"><span data-stu-id="a630b-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="a630b-127">Als Nächstes aktualisieren wir die C#-Sprachversion des Projekts auf Version 9.0.</span><span class="sxs-lookup"><span data-stu-id="a630b-127">Let's update the C# language version the project uses to version 9.0.</span></span> <span data-ttu-id="a630b-128">Bearbeiten Sie die Datei _consoleasync.csproj_, und fügen Sie einem Knoten vom Typ `<PropertyGroup>` die Einstellung `<LangVersion>` hinzu.</span><span class="sxs-lookup"><span data-stu-id="a630b-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>

    <LangVersion>9.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="a630b-129">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="a630b-129">Build the project</span></span>

<span data-ttu-id="a630b-130">Bevor Sie eine Projektvorlage fertig stellen, sollten Sie sie testen, um sicherzustellen, dass sie ordnungsgemäß kompiliert und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a630b-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span>

<span data-ttu-id="a630b-131">Führen Sie in Ihrem Terminal den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="a630b-131">In your terminal, run the following command.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="a630b-132">Sie erhalten die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a630b-132">You get the following output.</span></span>

```console
Hello World with C# 9.0!
```

<span data-ttu-id="a630b-133">Die erstellten Ordner _obj_ und _bin_ können mithilfe von `dotnet run` gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="a630b-133">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="a630b-134">Wenn Sie diese Dateien löschen, wird sichergestellt, dass Ihre Vorlage nur die Dateien enthält, die mit ihrer Vorlage zusammenhängen (und keine Dateien, die durch einen Buildvorgang entstanden sind).</span><span class="sxs-lookup"><span data-stu-id="a630b-134">Deleting these files ensures your template only includes the files related to your template and not any files that result from a build action.</span></span>

<span data-ttu-id="a630b-135">Nachdem Sie den Inhalt der Vorlage erstellt haben, müssen Sie als Nächstes im Stammordner der Vorlage die Vorlagenkonfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="a630b-135">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="a630b-136">Erstellen der Vorlagenkonfiguration</span><span class="sxs-lookup"><span data-stu-id="a630b-136">Create the template config</span></span>

<span data-ttu-id="a630b-137">Vorlagen werden in .NET anhand eines speziellen Ordners und einer Konfigurationsdatei am Stamm Ihrer Vorlage erkannt.</span><span class="sxs-lookup"><span data-stu-id="a630b-137">Templates are recognized in .NET by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="a630b-138">In diesem Tutorial befindet sich Ihr Vorlagenordner unter _working\templates\consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="a630b-138">In this tutorial, your template folder is located at _working\templates\consoleasync_.</span></span>

<span data-ttu-id="a630b-139">Bei der Vorlagenerstellung werden mit Ausnahme des speziellen Konfigurationsordners alle Dateien und Ordner aus dem Vorlagenordner in die Vorlage eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a630b-139">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="a630b-140">Dieser Konfigurationsordner heißt _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="a630b-140">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="a630b-141">Erstellen Sie zunächst einen neuen Unterordner namens _.template.config_, und öffnen Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="a630b-141">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="a630b-142">Erstellen Sie anschließend eine neue Datei namens _template.json_.</span><span class="sxs-lookup"><span data-stu-id="a630b-142">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="a630b-143">Ihre Ordnerstruktur sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="a630b-143">Your folder structure should look like this.</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="a630b-144">Öffnen Sie die Datei _template.json_ in Ihrem bevorzugten Text-Editor, fügen Sie den folgenden JSON-Code ein, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="a630b-144">Open the _template.json_ with your favorite text editor and paste in the following json code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#9" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="a630b-145">Diese Konfigurationsdatei enthält alle Einstellungen für Ihre Vorlage.</span><span class="sxs-lookup"><span data-stu-id="a630b-145">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="a630b-146">Neben Grundeinstellungen wie `name` und `shortName` enthält die Datei auch einen auf `project` festgelegten Wert vom Typ `tags/type`.</span><span class="sxs-lookup"><span data-stu-id="a630b-146">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="a630b-147">Dadurch wird Ihre Vorlage als Projektvorlage gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="a630b-147">This designates your template as a project template.</span></span> <span data-ttu-id="a630b-148">Sie können eine beliebige Art von Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="a630b-148">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="a630b-149">Die Werte `item` und `project` sind allgemeine Namen, die von .NET empfohlen werden, damit Benutzer problemlos nach der gesuchten Vorlagenart filtern können.</span><span class="sxs-lookup"><span data-stu-id="a630b-149">The `item` and `project` values are common names that .NET recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="a630b-150">Das Element `classifications` stellt die Spalte **Tags** dar, die angezeigt wird, wenn Sie `dotnet new` ausführen und eine Vorlagenliste abrufen.</span><span class="sxs-lookup"><span data-stu-id="a630b-150">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="a630b-151">Benutzer können auch anhand von Klassifizierungstags suchen.</span><span class="sxs-lookup"><span data-stu-id="a630b-151">Users can also search based on classification tags.</span></span> <span data-ttu-id="a630b-152">Die Eigenschaft `tags` in der JSON-Datei darf nicht mit der Tagliste `classifications` verwechselt werden.</span><span class="sxs-lookup"><span data-stu-id="a630b-152">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="a630b-153">Hierbei handelt es sich um zwei unterschiedliche Dinge, die leider ähnlich heißen.</span><span class="sxs-lookup"><span data-stu-id="a630b-153">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="a630b-154">Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="a630b-154">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="a630b-155">Weitere Informationen zur Datei *template.json* finden Sie im [Wiki zur Erstellung von .NET-Vorlagen](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="a630b-155">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="a630b-156">Nachdem Sie nun über eine gültige Datei vom Typ _.template.config/template.json_ verfügen, ist die Vorlage installationsbereit.</span><span class="sxs-lookup"><span data-stu-id="a630b-156">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="a630b-157">Löschen Sie vor der Installation der Vorlage alle zusätzlichen Dateiordner und Dateien, die nicht in Ihre Vorlage eingeschlossen werden sollen (wie etwa die Ordner _bin_ und _obj_).</span><span class="sxs-lookup"><span data-stu-id="a630b-157">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="a630b-158">Navigieren Sie in Ihrem Terminal zum Ordner _consoleasync_, und führen Sie `dotnet new -i .\` aus, um die Vorlage aus dem aktuellen Ordner zu installieren.</span><span class="sxs-lookup"><span data-stu-id="a630b-158">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="a630b-159">Bei Verwenden eines Linux- oder macOS-Betriebssystems muss ein Schrägstrich verwendet werden: `dotnet new -i ./`.</span><span class="sxs-lookup"><span data-stu-id="a630b-159">If you're using a Linux or macOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="a630b-160">Dieser Befehl gibt eine Liste mit den installierten Vorlagen aus. Darin sollte nun auch Ihre Vorlage enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="a630b-160">This command outputs the list of templates installed, which should include yours.</span></span>

```dotnetcli
dotnet new -i .\
```

<span data-ttu-id="a630b-161">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="a630b-161">You get output similar to the following.</span></span>

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name               Language          Tags
--------------------------------------------      -------------------      ------------      ----------------------
Console Application                               console                  [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync             [C#]              Common/Console/C#9
Class library                                     classlib                 [C#], F#, VB      Common/Library
WPF Application                                   wpf                      [C#], VB          Common/WPF
```

### <a name="test-the-project-template"></a><span data-ttu-id="a630b-162">Testen der Projektvorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-162">Test the project template</span></span>

<span data-ttu-id="a630b-163">Testen Sie als Nächstes Ihre installierte Projektvorlage.</span><span class="sxs-lookup"><span data-stu-id="a630b-163">Now that you have a project template installed, test it.</span></span>

1. <span data-ttu-id="a630b-164">Navigieren Sie zum Ordner _test_.</span><span class="sxs-lookup"><span data-stu-id="a630b-164">Navigate to the _test_ folder</span></span>

1. <span data-ttu-id="a630b-165">Erstellen Sie mit dem folgenden Befehl eine neue Konsolenanwendung, die ein funktionierendes Projekt generiert, das Sie mit dem `dotnet run`-Befehl problemlos testen können.</span><span class="sxs-lookup"><span data-stu-id="a630b-165">Create a new console application with the following command which generates a working project you can easily test with the `dotnet run` command.</span></span>

    ```dotnetcli
    dotnet new consoleasync
    ```

    <span data-ttu-id="a630b-166">Sie erhalten die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a630b-166">You get the following output.</span></span>

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. <span data-ttu-id="a630b-167">Führen Sie das Projekt mithilfe des folgenden Befehls aus.</span><span class="sxs-lookup"><span data-stu-id="a630b-167">Run the project using the following command.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="a630b-168">Sie erhalten die folgende Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="a630b-168">You get the following output.</span></span>

    ```console
    Hello World with C# 9.0!
    ```

<span data-ttu-id="a630b-169">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="a630b-169">Congratulations!</span></span> <span data-ttu-id="a630b-170">Sie haben eine Projektvorlage mit .NET erstellt und bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a630b-170">You created and deployed a project template with .NET.</span></span> <span data-ttu-id="a630b-171">Zur Vorbereitung auf den nächsten Teil der Tutorialreihe muss die von Ihnen erstellte Vorlage deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="a630b-171">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="a630b-172">Löschen Sie außerdem auch alle Dateien aus dem Ordner _test_.</span><span class="sxs-lookup"><span data-stu-id="a630b-172">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="a630b-173">Dadurch erhalten Sie eine bereinigte Umgebung, die für den nächsten Hauptabschnitt dieses Tutorials bereit ist.</span><span class="sxs-lookup"><span data-stu-id="a630b-173">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="a630b-174">Deinstallieren der Vorlage</span><span class="sxs-lookup"><span data-stu-id="a630b-174">Uninstall the template</span></span>

<span data-ttu-id="a630b-175">Da Sie die Vorlage unter Verwendung eines Dateipfads installiert haben, muss sie mit dem **absoluten** Dateipfad deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="a630b-175">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="a630b-176">Mithilfe des Befehls `dotnet new -u` können Sie eine Liste der installierten Vorlagen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a630b-176">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="a630b-177">Ihre Vorlage sollte am Ende der Liste aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="a630b-177">Your template should be listed last.</span></span> <span data-ttu-id="a630b-178">Deinstallieren Sie Ihre Vorlage mit dem aufgeführten Deinstallationsbefehl (`Uninstall Command`).</span><span class="sxs-lookup"><span data-stu-id="a630b-178">Use the `Uninstall Command` listed to uninstall your template.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="a630b-179">Sie erhalten eine Ausgabe ähnlich der folgenden.</span><span class="sxs-lookup"><span data-stu-id="a630b-179">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ProjectTemplates.2.2
    Details:
      NuGetPackageId: Microsoft.DotNet.Common.ProjectTemplates.2.2
      Version: 1.0.2-beta4
      Author: Microsoft
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
    Uninstall Command:
      dotnet new -u Microsoft.DotNet.Common.ProjectTemplates.2.2

... cut to save space ...

  C:\Test\templatetutorial\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
    Uninstall Command:
      dotnet new -u C:\working\templates\consoleasync
```

<span data-ttu-id="a630b-180">Führen Sie den in der Ausgabe gezeigten Deinstallationsbefehl (`Uninstall Command`) aus, um die von Ihnen erstellte Vorlage zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a630b-180">To uninstall the template that you created, run the `Uninstall Command` that is shown in the output.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="a630b-181">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a630b-181">Next steps</span></span>

<span data-ttu-id="a630b-182">In diesem Tutorial haben Sie eine Projektvorlage erstellt.</span><span class="sxs-lookup"><span data-stu-id="a630b-182">In this tutorial, you created a project template.</span></span> <span data-ttu-id="a630b-183">Im weiteren Verlauf dieser Tutorialreihe erfahren Sie, wie Sie sowohl die Element- als auch die Projektvorlagen in einer praktischen Datei verpacken.</span><span class="sxs-lookup"><span data-stu-id="a630b-183">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a630b-184">Tutorial: Erstellen eines Vorlagenpakets</span><span class="sxs-lookup"><span data-stu-id="a630b-184">Create a template pack</span></span>](cli-templates-create-template-pack.md)
