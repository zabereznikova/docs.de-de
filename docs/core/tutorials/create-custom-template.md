---
title: Erstellen eines benutzerdefinierten Vorlagen-Assistenten
description: In diesem interessanten Tutorial erfahren Sie, wie Sie eine benutzerdefinierte Vorlage für den dotnet new-Befehl erstellen.
keywords: .NET, .NET Core, vorlage, vorlagen, tutorial, dotnet new
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 519b910a-6efe-4394-9b81-0546aa3e7462
ms.workload:
- dotnetcore
ms.openlocfilehash: 7830a437b46d2080efc65f43f9112503add4c305
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2018
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="0bd6b-104">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="0bd6b-104">Create a custom template for dotnet new</span></span>

<span data-ttu-id="0bd6b-105">In diesem Tutorial lernen Sie:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="0bd6b-106">das Erstellen einer einfachen Vorlage aus einem vorhandenen Projekt oder einem neuen Konsolenanwendungsprojekt</span><span class="sxs-lookup"><span data-stu-id="0bd6b-106">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="0bd6b-107">das Verpacken der Vorlage zur Verteilung auf nuget.org oder aus einer lokalen *NUPKG*-Datei</span><span class="sxs-lookup"><span data-stu-id="0bd6b-107">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="0bd6b-108">das Installieren der Vorlage von nuget.org, aus einer lokalen *NUPKG*-Datei oder einem lokalen Dateisystem</span><span class="sxs-lookup"><span data-stu-id="0bd6b-108">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="0bd6b-109">Deinstallieren Sie die Vorlage</span><span class="sxs-lookup"><span data-stu-id="0bd6b-109">Uninstall the template.</span></span>

<span data-ttu-id="0bd6b-110">Wenn Sie das Tutorial lieber mit einem vollständigen Beispiel durchlaufen möchten, laden Sie die [Beispielprojektvorlage](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package) herunter.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-110">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="0bd6b-111">Die Beispielvorlage ist für die NuGet-Verteilung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-111">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="0bd6b-112">Wenn Sie das heruntergeladenen Beispiel mit einer Dateisystemverteilung verwenden möchten, führen Sie Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-112">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="0bd6b-113">Verschieben Sie den Inhalt des Ordners *content* des Beispiels um eine Ebene nach oben in den Ordner *GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-113">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="0bd6b-114">Löschen Sie den leeren *content*-Ordner.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-114">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="0bd6b-115">Löschen Sie die *NUSPEC*-Datei.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-115">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0bd6b-116">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="0bd6b-116">Prerequisites</span></span>

- <span data-ttu-id="0bd6b-117">Installieren Sie das [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-117">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="0bd6b-118">Lesen Sie den Referenzartikel [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-118">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="0bd6b-119">Erstellen einer Vorlage aus einem Projekt</span><span class="sxs-lookup"><span data-stu-id="0bd6b-119">Create a template from a project</span></span>

<span data-ttu-id="0bd6b-120">Verwenden Sie ein vorhandenes Projekt, von dem Sie wissen, dass es ordnungsgemäß kompiliert und ausgeführt wird, oder erstellen Sie ein neues Konsolen-App-Projekt in einem Ordner auf Ihrer Festplatte.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-120">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="0bd6b-121">In diesem Tutorial wird davon ausgegangen, dass der Name des Projektordners *GarciaSoftware.ConsoleTemplate.CSharp* ist und dieser unter *Documents\Templates* im Benutzerprofil gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-121">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="0bd6b-122">Der Projektvorlagenname im Tutorial folgt dem Format *\<Unternehmensname>.\<Vorlagentyp>.\<Programmiersprache>*, aber Sie können Ihrem Projekt und Ihrer Vorlage einen beliebigen anderen Namen geben.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-122">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="0bd6b-123">Fügen Sie dem Stamm des Projekts einen Ordner mit dem Namen *.template.config* hinzu.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-123">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="0bd6b-124">Erstellen Sie im Ordner *.template.config* eine *template.json*-Datei, um Ihre Vorlage zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-124">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="0bd6b-125">Weitere Informationen und Memberdefinitionen für die *template.json*-Datei finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](../tools/custom-templates.md#templatejson) und im [*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-125">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

```json
{
    "$schema": "http://json.schemastore.org/template",
    "author": "Catalina Garcia",
    "classifications": [ "Common", "Console" ],
    "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
    "name": "Garcia Software Console Application",
    "shortName": "garciaconsole"
}
```

<span data-ttu-id="0bd6b-126">Die Vorlage ist fertig.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-126">The template is finished.</span></span> <span data-ttu-id="0bd6b-127">Jetzt haben Sie zwei Optionen zum Verteilen der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-127">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="0bd6b-128">Um mit diesem Tutorial fortzufahren, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-128">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="0bd6b-129">[NuGet-Verteilung](#use-nuget-distribution): Installieren Sie die Vorlage aus NuGet oder aus der lokalen *NUPKG*-Datei, und verwenden Sie die installierte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-129">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="0bd6b-130">[Dateisystemverteilung](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-130">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="0bd6b-131">Verwenden der NuGet-Verteilung</span><span class="sxs-lookup"><span data-stu-id="0bd6b-131">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="0bd6b-132">Verpacken der Vorlage in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="0bd6b-132">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="0bd6b-133">Erstellen Sie einen Ordner für das NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-133">Create a folder for the NuGet package.</span></span> <span data-ttu-id="0bd6b-134">Im Tutorial ist der Name des Ordners *GarciaSoftware.ConsoleTemplate.CSharp*, und der Ordner wird im Ordner *Documents\NuGetTemplates* des Benutzerprofils erstellt.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-134">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="0bd6b-135">Erstellen Sie im neuen Vorlagenordner einen Ordner mit dem Namen *content* für die Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-135">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="0bd6b-136">Kopieren Sie den Inhalt des Projektordners gemeinsam mit seiner Datei *.template.config/template.json* in den Ordner *content*, den Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-136">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="0bd6b-137">Fügen Sie neben dem *content*-Ordner eine [*NUSPEC*-Datei](/nuget/create-packages/creating-a-package) ein.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-137">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="0bd6b-138">Die NUSPEC-Datei ist eine XML-Manifestdatei, die den Inhalt eines Paktes beschreibt und den Erstellungsprozess des NuGet-Pakets vorantreibt.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-138">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>
   
   ![Verzeichnisstruktur mit dem Layout des NuGet-Pakets](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="0bd6b-140">Fügen Sie im **\<packageTypes>**-Element einer *NUSPEC*-Datei ein **\<packageType>** mit einem `name`-Attributwert von `Template` ein.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-140">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="0bd6b-141">Der Ordner *content* und die Datei *NUSPEC* sollten sich im gleichen Verzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-141">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="0bd6b-142">In der Tabelle werden die *NUSPEC*-Dateielemente gezeigt, die mindestens erforderlich sind, um eine Vorlage als NuGet-Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-142">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="0bd6b-143">Element</span><span class="sxs-lookup"><span data-stu-id="0bd6b-143">Element</span></span>            | <span data-ttu-id="0bd6b-144">Typ</span><span class="sxs-lookup"><span data-stu-id="0bd6b-144">Type</span></span>   | <span data-ttu-id="0bd6b-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bd6b-145">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="0bd6b-146">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="0bd6b-146">**\<authors>**</span></span>     | <span data-ttu-id="0bd6b-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0bd6b-147">string</span></span> | <span data-ttu-id="0bd6b-148">Eine durch Kommas getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Autoren werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete der gleichen Autoren zu geben.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-148">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="0bd6b-149">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="0bd6b-149">**\<description>**</span></span> | <span data-ttu-id="0bd6b-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0bd6b-150">string</span></span> | <span data-ttu-id="0bd6b-151">Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-151">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="0bd6b-152">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="0bd6b-152">**\<id>**</span></span>          | <span data-ttu-id="0bd6b-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0bd6b-153">string</span></span> | <span data-ttu-id="0bd6b-154">Der Paketbezeichner, der die Groß- und Kleinschreibung nicht beachtet, der auf nuget.org oder im für das Paket verwendeten Katalog eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-154">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="0bd6b-155">IDs dürfen keine Leerzeichen oder für eine URL unzulässige Zeichen enthalten. Sie müssen den Regeln für .NET Namespaces entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-155">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="0bd6b-156">Informationen finden Sie im Abschnitt [Wählen eines eindeutigen Paketbezeichners und Festlegen der Versionsnummer](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-156">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="0bd6b-157">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="0bd6b-157">**\<packageType>**</span></span> | <span data-ttu-id="0bd6b-158">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0bd6b-158">string</span></span> | <span data-ttu-id="0bd6b-159">Fügen Sie dieses Element in ein **\<packageTypes>**-Element bei den **\<metadata>**-Elementen ein.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-159">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="0bd6b-160">Legen Sie das `name`-Attribut des **\<packageType>**-Elements auf `Template` fest.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-160">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="0bd6b-161">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="0bd6b-161">**\<version>**</span></span>     | <span data-ttu-id="0bd6b-162">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="0bd6b-162">string</span></span> | <span data-ttu-id="0bd6b-163">Die Version des Pakets, die dem Format „hauptversion.nebenversion.patch“ folgt.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-163">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="0bd6b-164">Versionsnummern enthalten möglicherweise ein Suffix der Vorabversion, wie im Artikel zu [Vorabversionen](/nuget/create-packages/prerelease-packages#semantic-versioning) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-164">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="0bd6b-165">Das vollständige *NUSPEC*-Dateischema finden Sie in der [.nuspec-Referenz](/nuget/schema/nuspec).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-165">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="0bd6b-166">Die *NUSPEC*-Datei im Tutorial heißt *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* und enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-166">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. <span data-ttu-id="0bd6b-167">[Erstellen Sie das Paket](/nuget/create-packages/creating-a-package#creating-the-package) mit dem Befehl `nuget pack <PATH_TO_NUSPEC_FILE>`.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-167">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="0bd6b-168">Der folgende Befehl geht davon aus, dass sich der Ordner, der die NuGet-Objekte enthält, unter *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* befindet.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-168">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="0bd6b-169">Egal wo Sie den Ordner auf Ihrem System platzieren, der `nuget pack`-Befehl nimmt den Pfad der *NUSPEC*-Datei an:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-169">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="0bd6b-170">Veröffentlichen des Pakets auf nuget.org</span><span class="sxs-lookup"><span data-stu-id="0bd6b-170">Publishing the package to nuget.org</span></span>

<span data-ttu-id="0bd6b-171">Um Ihr NuGet-Paket zu veröffentlichen, befolgen Sie die Anweisungen unter [Create and publish a package (Erstellen und Veröffentlichen eines Pakets)](/nuget/quickstart/create-and-publish-a-package#publish-the-package).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-171">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="0bd6b-172">Es wird allerdings empfohlen, dass Sie nicht die Vorlage aus dem Tutorial auf NuGet veröffentlichen, da Sie die Vorlage nicht mehr löschen können, wenn Sie einmal veröffentlicht wurde, sondern Sie können Sie nur aus der Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-172">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="0bd6b-173">Jetzt wo Sie ein NuGet-Paket in Form einer *NUPKG*-Datei haben, wird empfohlen, dass Sie die unten stehenden Anweisungen befolgen, um die Vorlage direkt aus der lokalen *NUPKG*-Datei zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-173">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="0bd6b-174">Installieren der Vorlage aus einem NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="0bd6b-174">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="0bd6b-175">Installieren der Vorlage aus einer lokalen *NUPKG*-Datei</span><span class="sxs-lookup"><span data-stu-id="0bd6b-175">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="0bd6b-176">Um die Vorlage auf der *NUPKG*-Datei, die Sie erstellt haben, zu installieren, verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option,und stellen Sie den Pfad zur *NUPKG*-Datei bereit:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-176">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="0bd6b-177">Installieren einer Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="0bd6b-177">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="0bd6b-178">Wenn Sie eine Vorlage aus einem NuGet-Paket installieren möchten, das auf nuget.org gespeichert ist, verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option, und geben Sie den Namen des NuGet-Pakets an:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-178">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="0bd6b-179">Das Beispiel dient nur der Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-179">The example is for demonstration purposes only.</span></span> <span data-ttu-id="0bd6b-180">Auf nuget.org gibt es nur ein `GarciaSoftware.ConsoleTemplate.CSharp`-NuGet-Paket, und es wird empfohlen, dass Sie die Testvorlage von NuGet veröffentlichen und nutzen.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-180">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="0bd6b-181">Wenn Sie den Befehl ausführen, wird keine Vorlage installiert.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-181">If you run the command, no template is installed.</span></span> <span data-ttu-id="0bd6b-182">Sie können allerdings eine Vorlage installieren, die noch nicht auf nuget.org veröffentlicht wurde, indem Sie direkt in Ihrem lokalen Dateisystem auf eine *NUPKG*-Datei verweisen, wie im vorherigen Abschnitt [Installieren der Vorlage aus einer lokalen NUPKG-Datei](#install-the-template-from-the-local-nupkg-file) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-182">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="0bd6b-183">Ein Livebeispiel für die Installation eines Pakets von nuget.org finden Sie unter [NUnit 3 Template](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-183">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="0bd6b-184">Diese Vorlage richtet ein Projekt für NUnit-Komponententests ein.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-184">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="0bd6b-185">Verwenden Sie folgenden Befehl, um sie zu installieren:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-185">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="0bd6b-186">Wenn Sie die Vorlagen mit `dotnet new -l` auflisten, sehen Sie *NUnit 3-Testprojekt* mit dem Kurznamen *nunit* in der Vorlagenliste.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-186">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="0bd6b-187">Im nächsten Abschnitt können Sie die Vorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-187">You're ready to use the template in the next section.</span></span>

![Konsolenfenster, das die NUnit-Vorlage mit anderen installierten Vorlagen zeigt](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="0bd6b-189">Erstellen eines neuen Projekts aus der Vorlage</span><span class="sxs-lookup"><span data-stu-id="0bd6b-189">Create a project from the template</span></span>

<span data-ttu-id="0bd6b-190">Nachdem die Vorlage aus NuGet installiert wurde, verwenden Sie sie, indem Sie den `dotnet new <TEMPLATE>`-Befehl aus dem Verzeichnis ausführen, in das die Ausgabe des Vorlagenmoduls eingefügt werden soll (es sei denn, Sie verwenden die `-o|--output`-Option, um ein spezifisches Verzeichnis anzugeben).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-190">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="0bd6b-191">Weitere Informationen finden Sie unter [`dotnet new`-Optionen](~/docs/core/tools/dotnet-new.md#options):</span><span class="sxs-lookup"><span data-stu-id="0bd6b-191">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="0bd6b-192">Geben Sie die Kurzform des Namens der Vorlage für den `dotnet new`-Befehl an.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-192">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="0bd6b-193">Um ein Projekt aus der NUnit-Vorlage zu erstellen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-193">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="0bd6b-194">Die Konsole zeigt an, dass das Projekt erstellt wurde und dass die Pakete des Projekts wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-194">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="0bd6b-195">Nachdem der Befehl ausgeführt wurde, ist das Projekt einsatzbereit.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-195">After the command is run, the project is ready for use.</span></span>

![Konsolenfenster mit der Ausgabe des dotnet new-Befehls, während er das NUnit-Projekt erstellt und die Projektabhängigkeiten wiederherstellt.](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="0bd6b-197">So deinstallieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="0bd6b-197">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="0bd6b-198">Das Beispiel dient nur der Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-198">The example is for demonstration purposes only.</span></span> <span data-ttu-id="0bd6b-199">Es gibt kein `GarciaSoftware.ConsoleTemplate.CSharp`-NuGet-Paket auf nuget.org und auch keines, das mit dem .NET Core SDK installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-199">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="0bd6b-200">Wenn Sie den Befehl ausführen, werden keine Pakete bzw. Vorlagen deinstalliert, und Sie erhalten die folgende Ausnahme:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-200">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
> 
> > <span data-ttu-id="0bd6b-201">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'. (Das zu deinstallierende Objekt „GarciaSoftware.ConsoleTemplate.CSharp“ konnte nicht gefunden werden.)</span><span class="sxs-lookup"><span data-stu-id="0bd6b-201">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="0bd6b-202">Wenn Sie die [NUnit 3-Vorlage für dotnet new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) installiert haben und diese deinstallieren möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-202">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="0bd6b-203">So deinstallieren Sie eine Vorlage aus einer lokalen NUPKG-Datei</span><span class="sxs-lookup"><span data-stu-id="0bd6b-203">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="0bd6b-204">Wenn Sie eine Vorlage deinstallieren möchten, versuchen Sie dies nicht mit dem Pfad der *NUPKG*-Datei.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-204">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="0bd6b-205">*Die Deinstallation der Vorlage mit `dotnet new -u <PATH_TO_NUPKG_FILE>` schlägt fehl.*</span><span class="sxs-lookup"><span data-stu-id="0bd6b-205">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="0bd6b-206">Verweisen Sie mit der entsprechenden `id` auf das Paket:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-206">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="0bd6b-207">Verwenden der Dateisystemverteilung</span><span class="sxs-lookup"><span data-stu-id="0bd6b-207">Use file system distribution</span></span>

<span data-ttu-id="0bd6b-208">Um eine Vorlage zu verteilen, speichern Sie den Projektvorlagenordner auf Ihrem Netzwerk an einer Stelle, auf die Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-208">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="0bd6b-209">Verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option, geben Sie den Pfad des Vorlagenordners an (der Projektordner, der das Projekt und den Ordner *.template.config* enthält).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-209">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="0bd6b-210">Im Tutorial wird davon ausgegangen, dass die Projektvorlage im Ordner *Documents/Templates* des Benutzerprofils gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-210">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="0bd6b-211">Installieren Sie von diesem Speicherort aus die Vorlage mit dem folgenden Befehl, wobei Sie \<BENUTZER> durch den Namen des Benutzerprofils ersetzen.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-211">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="0bd6b-212">Erstellen eines neuen Projekts aus der Vorlage</span><span class="sxs-lookup"><span data-stu-id="0bd6b-212">Create a project from the template</span></span>

<span data-ttu-id="0bd6b-213">Nachdem die Vorlage aus dem Dateisystem installiert wurde, verwenden Sie sie, indem Sie den `dotnet new <TEMPLATE>`-Befehl aus dem Verzeichnis ausführen, in das die Ausgabe des Vorlagenmoduls eingefügt werden soll (es sei denn, Sie verwenden die `-o|--output`-Option, um ein spezifisches Verzeichnis anzugeben).</span><span class="sxs-lookup"><span data-stu-id="0bd6b-213">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="0bd6b-214">Weitere Informationen finden Sie unter [`dotnet new`-Optionen](~/docs/core/tools/dotnet-new.md#options):</span><span class="sxs-lookup"><span data-stu-id="0bd6b-214">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="0bd6b-215">Geben Sie die Kurzform des Namens der Vorlage für den `dotnet new`-Befehl an.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-215">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="0bd6b-216">Erstellen Sie aus einem neuen Projektordner, der unter *C:\Benutzer\\\<BENUTZER>\Dokumente\Projekte\MeineKonsolenanwendung* erstellt wurde, ein Projekt aus der `garciaconsole`-Vorlage:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-216">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="0bd6b-217">Deinstallieren der Vorlage</span><span class="sxs-lookup"><span data-stu-id="0bd6b-217">Uninstall the template</span></span>

<span data-ttu-id="0bd6b-218">Wenn Sie die Vorlage in Ihrem Dateisystem unter *C:\Benutzer\\\<BENUTZER>\Dokumente\Vorlagen\GarciaSoftware.ConsoleTemplate.CSharp* erstellt haben, deinstallieren Sie sie mit `-u|--uninstall` und dem Pfad des Vorlagenordners:</span><span class="sxs-lookup"><span data-stu-id="0bd6b-218">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="0bd6b-219">Um die Vorlage aus Ihrem lokalen Dateisystem zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-219">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="0bd6b-220">Beispielsweise funktioniert zwar *C:\Benutzer\\\<BENUTZER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *.\GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-220">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="0bd6b-221">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="0bd6b-221">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="0bd6b-222">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bd6b-222">See also</span></span>

[<span data-ttu-id="0bd6b-223">dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)</span><span class="sxs-lookup"><span data-stu-id="0bd6b-223">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)  
[<span data-ttu-id="0bd6b-224">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="0bd6b-224">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="0bd6b-225">How to create your own templates for dotnet new (So erstellen Sie Ihre eigenen Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="0bd6b-225">How to create your own templates for dotnet new</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)  
[<span data-ttu-id="0bd6b-226">*template.json*-Schema im JSON-Schemaspeicher</span><span class="sxs-lookup"><span data-stu-id="0bd6b-226">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  
