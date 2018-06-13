---
title: Erstellen eines benutzerdefinierten Vorlagen-Assistenten
description: In diesem interessanten Tutorial erfahren Sie, wie Sie eine benutzerdefinierte Vorlage für den dotnet new-Befehl erstellen.
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.openlocfilehash: fee2709f54395b9926dae904a448cb92aafb5172
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218081"
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="2bb82-103">Erstellen eines benutzerdefinierten Vorlagen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="2bb82-103">Create a custom template for dotnet new</span></span>

<span data-ttu-id="2bb82-104">In diesem Tutorial lernen Sie:</span><span class="sxs-lookup"><span data-stu-id="2bb82-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="2bb82-105">das Erstellen einer einfachen Vorlage aus einem vorhandenen Projekt oder einem neuen Konsolenanwendungsprojekt</span><span class="sxs-lookup"><span data-stu-id="2bb82-105">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="2bb82-106">das Verpacken der Vorlage zur Verteilung auf nuget.org oder aus einer lokalen *NUPKG*-Datei</span><span class="sxs-lookup"><span data-stu-id="2bb82-106">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="2bb82-107">das Installieren der Vorlage von nuget.org, aus einer lokalen *NUPKG*-Datei oder einem lokalen Dateisystem</span><span class="sxs-lookup"><span data-stu-id="2bb82-107">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="2bb82-108">Deinstallieren Sie die Vorlage</span><span class="sxs-lookup"><span data-stu-id="2bb82-108">Uninstall the template.</span></span>

<span data-ttu-id="2bb82-109">Wenn Sie das Tutorial lieber mit einem vollständigen Beispiel durchlaufen möchten, laden Sie die [Beispielprojektvorlage](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package) herunter.</span><span class="sxs-lookup"><span data-stu-id="2bb82-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="2bb82-110">Die Beispielvorlage ist für die NuGet-Verteilung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2bb82-110">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="2bb82-111">Wenn Sie das heruntergeladenen Beispiel mit einer Dateisystemverteilung verwenden möchten, führen Sie Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="2bb82-111">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="2bb82-112">Verschieben Sie den Inhalt des Ordners *content* des Beispiels um eine Ebene nach oben in den Ordner *GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="2bb82-112">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="2bb82-113">Löschen Sie den leeren *content*-Ordner.</span><span class="sxs-lookup"><span data-stu-id="2bb82-113">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="2bb82-114">Löschen Sie die *NUSPEC*-Datei.</span><span class="sxs-lookup"><span data-stu-id="2bb82-114">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bb82-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="2bb82-115">Prerequisites</span></span>

- <span data-ttu-id="2bb82-116">Installieren Sie das [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="2bb82-116">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="2bb82-117">Lesen Sie den Referenzartikel [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="2bb82-117">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="2bb82-118">Erstellen einer Vorlage aus einem Projekt</span><span class="sxs-lookup"><span data-stu-id="2bb82-118">Create a template from a project</span></span>

<span data-ttu-id="2bb82-119">Verwenden Sie ein vorhandenes Projekt, von dem Sie wissen, dass es ordnungsgemäß kompiliert und ausgeführt wird, oder erstellen Sie ein neues Konsolen-App-Projekt in einem Ordner auf Ihrer Festplatte.</span><span class="sxs-lookup"><span data-stu-id="2bb82-119">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="2bb82-120">In diesem Tutorial wird davon ausgegangen, dass der Name des Projektordners *GarciaSoftware.ConsoleTemplate.CSharp* ist und dieser unter *Documents\Templates* im Benutzerprofil gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2bb82-120">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="2bb82-121">Der Projektvorlagenname im Tutorial folgt dem Format *\<Unternehmensname>.\<Vorlagentyp>.\<Programmiersprache>*, aber Sie können Ihrem Projekt und Ihrer Vorlage einen beliebigen anderen Namen geben.</span><span class="sxs-lookup"><span data-stu-id="2bb82-121">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="2bb82-122">Fügen Sie dem Stamm des Projekts einen Ordner mit dem Namen *.template.config* hinzu.</span><span class="sxs-lookup"><span data-stu-id="2bb82-122">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="2bb82-123">Erstellen Sie im Ordner *.template.config* eine *template.json*-Datei, um Ihre Vorlage zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2bb82-123">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="2bb82-124">Weitere Informationen und Memberdefinitionen für die *template.json*-Datei finden Sie unter [Custom templates for dotnet new (Benutzerdefinierte Vorlagen für dotnet new)](../tools/custom-templates.md#templatejson) und im [*template.json*-Schema im JSON-Schemaspeicher](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="2bb82-124">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

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

<span data-ttu-id="2bb82-125">Die Vorlage ist fertig.</span><span class="sxs-lookup"><span data-stu-id="2bb82-125">The template is finished.</span></span> <span data-ttu-id="2bb82-126">Jetzt haben Sie zwei Optionen zum Verteilen der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="2bb82-126">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="2bb82-127">Um mit diesem Tutorial fortzufahren, wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="2bb82-127">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="2bb82-128">[NuGet-Verteilung](#use-nuget-distribution): Installieren Sie die Vorlage aus NuGet oder aus der lokalen *NUPKG*-Datei, und verwenden Sie die installierte Vorlage.</span><span class="sxs-lookup"><span data-stu-id="2bb82-128">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="2bb82-129">[Dateisystemverteilung](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="2bb82-129">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="2bb82-130">Verwenden der NuGet-Verteilung</span><span class="sxs-lookup"><span data-stu-id="2bb82-130">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="2bb82-131">Verpacken der Vorlage in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="2bb82-131">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="2bb82-132">Erstellen Sie einen Ordner für das NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="2bb82-132">Create a folder for the NuGet package.</span></span> <span data-ttu-id="2bb82-133">Im Tutorial ist der Name des Ordners *GarciaSoftware.ConsoleTemplate.CSharp*, und der Ordner wird im Ordner *Documents\NuGetTemplates* des Benutzerprofils erstellt.</span><span class="sxs-lookup"><span data-stu-id="2bb82-133">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="2bb82-134">Erstellen Sie im neuen Vorlagenordner einen Ordner mit dem Namen *content* für die Projektdateien.</span><span class="sxs-lookup"><span data-stu-id="2bb82-134">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="2bb82-135">Kopieren Sie den Inhalt des Projektordners gemeinsam mit seiner Datei *.template.config/template.json* in den Ordner *content*, den Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="2bb82-135">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="2bb82-136">Fügen Sie neben dem *content*-Ordner eine [*NUSPEC*-Datei](/nuget/create-packages/creating-a-package) ein.</span><span class="sxs-lookup"><span data-stu-id="2bb82-136">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="2bb82-137">Die NUSPEC-Datei ist eine XML-Manifestdatei, die den Inhalt eines Paktes beschreibt und den Erstellungsprozess des NuGet-Pakets vorantreibt.</span><span class="sxs-lookup"><span data-stu-id="2bb82-137">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>
   
   ![Verzeichnisstruktur mit dem Layout des NuGet-Pakets](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="2bb82-139">Fügen Sie im **\<packageTypes>**-Element einer *NUSPEC*-Datei ein **\<packageType>** mit einem `name`-Attributwert von `Template` ein.</span><span class="sxs-lookup"><span data-stu-id="2bb82-139">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="2bb82-140">Der Ordner *content* und die Datei *NUSPEC* sollten sich im gleichen Verzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="2bb82-140">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="2bb82-141">In der Tabelle werden die *NUSPEC*-Dateielemente gezeigt, die mindestens erforderlich sind, um eine Vorlage als NuGet-Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2bb82-141">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="2bb82-142">Element</span><span class="sxs-lookup"><span data-stu-id="2bb82-142">Element</span></span>            | <span data-ttu-id="2bb82-143">Typ</span><span class="sxs-lookup"><span data-stu-id="2bb82-143">Type</span></span>   | <span data-ttu-id="2bb82-144">description</span><span class="sxs-lookup"><span data-stu-id="2bb82-144">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="2bb82-145">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="2bb82-145">**\<authors>**</span></span>     | <span data-ttu-id="2bb82-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2bb82-146">string</span></span> | <span data-ttu-id="2bb82-147">Eine durch Kommas getrennte Liste der Paketautoren, die mit Profilnamen unter nuget.org übereinstimmen. Autoren werden im NuGet-Katalog unter nuget.org angezeigt und werden verwendet, um Querverweise auf Pakete der gleichen Autoren zu geben.</span><span class="sxs-lookup"><span data-stu-id="2bb82-147">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="2bb82-148">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="2bb82-148">**\<description>**</span></span> | <span data-ttu-id="2bb82-149">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2bb82-149">string</span></span> | <span data-ttu-id="2bb82-150">Eine ausführliche Beschreibung des Pakets für die Anzeige der Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="2bb82-150">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="2bb82-151">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="2bb82-151">**\<id>**</span></span>          | <span data-ttu-id="2bb82-152">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2bb82-152">string</span></span> | <span data-ttu-id="2bb82-153">Der Paketbezeichner, der die Groß- und Kleinschreibung nicht beachtet, der auf nuget.org oder im für das Paket verwendeten Katalog eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="2bb82-153">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="2bb82-154">IDs dürfen keine Leerzeichen oder für eine URL unzulässige Zeichen enthalten. Sie müssen den Regeln für .NET Namespaces entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2bb82-154">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="2bb82-155">Informationen finden Sie im Abschnitt [Wählen eines eindeutigen Paketbezeichners und Festlegen der Versionsnummer](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number).</span><span class="sxs-lookup"><span data-stu-id="2bb82-155">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="2bb82-156">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="2bb82-156">**\<packageType>**</span></span> | <span data-ttu-id="2bb82-157">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2bb82-157">string</span></span> | <span data-ttu-id="2bb82-158">Fügen Sie dieses Element in ein **\<packageTypes>**-Element bei den **\<metadata>**-Elementen ein.</span><span class="sxs-lookup"><span data-stu-id="2bb82-158">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="2bb82-159">Legen Sie das `name`-Attribut des **\<packageType>**-Elements auf `Template` fest.</span><span class="sxs-lookup"><span data-stu-id="2bb82-159">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="2bb82-160">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="2bb82-160">**\<version>**</span></span>     | <span data-ttu-id="2bb82-161">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2bb82-161">string</span></span> | <span data-ttu-id="2bb82-162">Die Version des Pakets, die dem Format „hauptversion.nebenversion.patch“ folgt.</span><span class="sxs-lookup"><span data-stu-id="2bb82-162">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="2bb82-163">Versionsnummern enthalten möglicherweise ein Suffix der Vorabversion, wie im Artikel zu [Vorabversionen](/nuget/create-packages/prerelease-packages#semantic-versioning) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2bb82-163">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="2bb82-164">Das vollständige *NUSPEC*-Dateischema finden Sie in der [.nuspec-Referenz](/nuget/schema/nuspec).</span><span class="sxs-lookup"><span data-stu-id="2bb82-164">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="2bb82-165">Die *NUSPEC*-Datei im Tutorial heißt *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* und enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2bb82-165">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

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

1. <span data-ttu-id="2bb82-166">[Erstellen Sie das Paket](/nuget/create-packages/creating-a-package#creating-the-package) mit dem Befehl `nuget pack <PATH_TO_NUSPEC_FILE>`.</span><span class="sxs-lookup"><span data-stu-id="2bb82-166">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="2bb82-167">Der folgende Befehl geht davon aus, dass sich der Ordner, der die NuGet-Objekte enthält, unter *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* befindet.</span><span class="sxs-lookup"><span data-stu-id="2bb82-167">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="2bb82-168">Egal wo Sie den Ordner auf Ihrem System platzieren, der `nuget pack`-Befehl nimmt den Pfad der *NUSPEC*-Datei an:</span><span class="sxs-lookup"><span data-stu-id="2bb82-168">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="2bb82-169">Veröffentlichen des Pakets auf nuget.org</span><span class="sxs-lookup"><span data-stu-id="2bb82-169">Publishing the package to nuget.org</span></span>

<span data-ttu-id="2bb82-170">Um Ihr NuGet-Paket zu veröffentlichen, befolgen Sie die Anweisungen unter [Create and publish a package (Erstellen und Veröffentlichen eines Pakets)](/nuget/quickstart/create-and-publish-a-package#publish-the-package).</span><span class="sxs-lookup"><span data-stu-id="2bb82-170">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="2bb82-171">Es wird allerdings empfohlen, dass Sie nicht die Vorlage aus dem Tutorial auf NuGet veröffentlichen, da Sie die Vorlage nicht mehr löschen können, wenn Sie einmal veröffentlicht wurde, sondern Sie können Sie nur aus der Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="2bb82-171">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="2bb82-172">Jetzt wo Sie ein NuGet-Paket in Form einer *NUPKG*-Datei haben, wird empfohlen, dass Sie die unten stehenden Anweisungen befolgen, um die Vorlage direkt aus der lokalen *NUPKG*-Datei zu installieren.</span><span class="sxs-lookup"><span data-stu-id="2bb82-172">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="2bb82-173">Installieren der Vorlage aus einem NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="2bb82-173">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="2bb82-174">Installieren der Vorlage aus einer lokalen *NUPKG*-Datei</span><span class="sxs-lookup"><span data-stu-id="2bb82-174">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="2bb82-175">Um die Vorlage auf der *NUPKG*-Datei, die Sie erstellt haben, zu installieren, verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option,und stellen Sie den Pfad zur *NUPKG*-Datei bereit:</span><span class="sxs-lookup"><span data-stu-id="2bb82-175">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="2bb82-176">Installieren einer Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="2bb82-176">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="2bb82-177">Wenn Sie eine Vorlage aus einem NuGet-Paket installieren möchten, das auf nuget.org gespeichert ist, verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option, und geben Sie den Namen des NuGet-Pakets an:</span><span class="sxs-lookup"><span data-stu-id="2bb82-177">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="2bb82-178">Das Beispiel dient nur der Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="2bb82-178">The example is for demonstration purposes only.</span></span> <span data-ttu-id="2bb82-179">Auf nuget.org gibt es nur ein `GarciaSoftware.ConsoleTemplate.CSharp`-NuGet-Paket, und es wird empfohlen, dass Sie die Testvorlage von NuGet veröffentlichen und nutzen.</span><span class="sxs-lookup"><span data-stu-id="2bb82-179">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="2bb82-180">Wenn Sie den Befehl ausführen, wird keine Vorlage installiert.</span><span class="sxs-lookup"><span data-stu-id="2bb82-180">If you run the command, no template is installed.</span></span> <span data-ttu-id="2bb82-181">Sie können allerdings eine Vorlage installieren, die noch nicht auf nuget.org veröffentlicht wurde, indem Sie direkt in Ihrem lokalen Dateisystem auf eine *NUPKG*-Datei verweisen, wie im vorherigen Abschnitt [Installieren der Vorlage aus einer lokalen NUPKG-Datei](#install-the-template-from-the-local-nupkg-file) gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bb82-181">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="2bb82-182">Ein Livebeispiel für die Installation eines Pakets von nuget.org finden Sie unter [NUnit 3 Template](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span><span class="sxs-lookup"><span data-stu-id="2bb82-182">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="2bb82-183">Diese Vorlage richtet ein Projekt für NUnit-Komponententests ein.</span><span class="sxs-lookup"><span data-stu-id="2bb82-183">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="2bb82-184">Verwenden Sie folgenden Befehl, um sie zu installieren:</span><span class="sxs-lookup"><span data-stu-id="2bb82-184">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="2bb82-185">Wenn Sie die Vorlagen mit `dotnet new -l` auflisten, sehen Sie *NUnit 3-Testprojekt* mit dem Kurznamen *nunit* in der Vorlagenliste.</span><span class="sxs-lookup"><span data-stu-id="2bb82-185">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="2bb82-186">Im nächsten Abschnitt können Sie die Vorlage verwenden.</span><span class="sxs-lookup"><span data-stu-id="2bb82-186">You're ready to use the template in the next section.</span></span>

![Konsolenfenster, das die NUnit-Vorlage mit anderen installierten Vorlagen zeigt](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="2bb82-188">Erstellen eines neuen Projekts aus der Vorlage</span><span class="sxs-lookup"><span data-stu-id="2bb82-188">Create a project from the template</span></span>

<span data-ttu-id="2bb82-189">Nachdem die Vorlage aus NuGet installiert wurde, verwenden Sie sie, indem Sie den `dotnet new <TEMPLATE>`-Befehl aus dem Verzeichnis ausführen, in das die Ausgabe der Vorlagen-Engine eingefügt werden soll (es sei denn, Sie verwenden die `-o|--output`-Option, um ein spezifisches Verzeichnis anzugeben).</span><span class="sxs-lookup"><span data-stu-id="2bb82-189">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="2bb82-190">Weitere Informationen finden Sie unter [`dotnet new`-Optionen](~/docs/core/tools/dotnet-new.md#options):</span><span class="sxs-lookup"><span data-stu-id="2bb82-190">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="2bb82-191">Geben Sie die Kurzform des Namens der Vorlage für den `dotnet new`-Befehl an.</span><span class="sxs-lookup"><span data-stu-id="2bb82-191">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="2bb82-192">Um ein Projekt aus der NUnit-Vorlage zu erstellen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="2bb82-192">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="2bb82-193">Die Konsole zeigt an, dass das Projekt erstellt wurde und dass die Pakete des Projekts wiederhergestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2bb82-193">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="2bb82-194">Nachdem der Befehl ausgeführt wurde, ist das Projekt einsatzbereit.</span><span class="sxs-lookup"><span data-stu-id="2bb82-194">After the command is run, the project is ready for use.</span></span>

![Konsolenfenster mit der Ausgabe des dotnet new-Befehls, während er das NUnit-Projekt erstellt und die Projektabhängigkeiten wiederherstellt.](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="2bb82-196">So deinstallieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="2bb82-196">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="2bb82-197">Das Beispiel dient nur der Veranschaulichung.</span><span class="sxs-lookup"><span data-stu-id="2bb82-197">The example is for demonstration purposes only.</span></span> <span data-ttu-id="2bb82-198">Es gibt kein `GarciaSoftware.ConsoleTemplate.CSharp`-NuGet-Paket auf nuget.org und auch keines, das mit dem .NET Core SDK installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2bb82-198">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="2bb82-199">Wenn Sie den Befehl ausführen, werden keine Pakete bzw. Vorlagen deinstalliert, und Sie erhalten die folgende Ausnahme:</span><span class="sxs-lookup"><span data-stu-id="2bb82-199">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
> 
> > <span data-ttu-id="2bb82-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'. (Das zu deinstallierende Objekt „GarciaSoftware.ConsoleTemplate.CSharp“ konnte nicht gefunden werden.)</span><span class="sxs-lookup"><span data-stu-id="2bb82-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="2bb82-201">Wenn Sie die [NUnit 3-Vorlage für dotnet new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) installiert haben und diese deinstallieren möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="2bb82-201">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="2bb82-202">So deinstallieren Sie eine Vorlage aus einer lokalen NUPKG-Datei</span><span class="sxs-lookup"><span data-stu-id="2bb82-202">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="2bb82-203">Wenn Sie eine Vorlage deinstallieren möchten, versuchen Sie dies nicht mit dem Pfad der *NUPKG*-Datei.</span><span class="sxs-lookup"><span data-stu-id="2bb82-203">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="2bb82-204">*Die Deinstallation der Vorlage mit `dotnet new -u <PATH_TO_NUPKG_FILE>` schlägt fehl.*</span><span class="sxs-lookup"><span data-stu-id="2bb82-204">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="2bb82-205">Verweisen Sie mit der entsprechenden `id` auf das Paket:</span><span class="sxs-lookup"><span data-stu-id="2bb82-205">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="2bb82-206">Verwenden der Dateisystemverteilung</span><span class="sxs-lookup"><span data-stu-id="2bb82-206">Use file system distribution</span></span>

<span data-ttu-id="2bb82-207">Um eine Vorlage zu verteilen, speichern Sie den Projektvorlagenordner auf Ihrem Netzwerk an einer Stelle, auf die Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2bb82-207">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="2bb82-208">Verwenden Sie den `dotnet new`-Befehl mit der `-i|--install`-Option, geben Sie den Pfad des Vorlagenordners an (der Projektordner, der das Projekt und den Ordner *.template.config* enthält).</span><span class="sxs-lookup"><span data-stu-id="2bb82-208">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="2bb82-209">Im Tutorial wird davon ausgegangen, dass die Projektvorlage im Ordner *Documents/Templates* des Benutzerprofils gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="2bb82-209">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="2bb82-210">Installieren Sie von diesem Speicherort aus die Vorlage mit dem folgenden Befehl, wobei Sie \<BENUTZER> durch den Namen des Benutzerprofils ersetzen.</span><span class="sxs-lookup"><span data-stu-id="2bb82-210">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="2bb82-211">Erstellen eines neuen Projekts aus der Vorlage</span><span class="sxs-lookup"><span data-stu-id="2bb82-211">Create a project from the template</span></span>

<span data-ttu-id="2bb82-212">Nachdem die Vorlage aus dem Dateisystem installiert wurde, verwenden Sie sie, indem Sie den `dotnet new <TEMPLATE>`-Befehl aus dem Verzeichnis ausführen, in das die Ausgabe der Vorlagen-Engine eingefügt werden soll (es sei denn, Sie verwenden die `-o|--output`-Option, um ein spezifisches Verzeichnis anzugeben).</span><span class="sxs-lookup"><span data-stu-id="2bb82-212">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="2bb82-213">Weitere Informationen finden Sie unter [`dotnet new`-Optionen](~/docs/core/tools/dotnet-new.md#options):</span><span class="sxs-lookup"><span data-stu-id="2bb82-213">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="2bb82-214">Geben Sie die Kurzform des Namens der Vorlage für den `dotnet new`-Befehl an.</span><span class="sxs-lookup"><span data-stu-id="2bb82-214">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="2bb82-215">Erstellen Sie aus einem neuen Projektordner, der unter *C:\Benutzer\\\<BENUTZER>\Dokumente\Projekte\MeineKonsolenanwendung* erstellt wurde, ein Projekt aus der `garciaconsole`-Vorlage:</span><span class="sxs-lookup"><span data-stu-id="2bb82-215">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="2bb82-216">Deinstallieren der Vorlage</span><span class="sxs-lookup"><span data-stu-id="2bb82-216">Uninstall the template</span></span>

<span data-ttu-id="2bb82-217">Wenn Sie die Vorlage in Ihrem Dateisystem unter *C:\Benutzer\\\<BENUTZER>\Dokumente\Vorlagen\GarciaSoftware.ConsoleTemplate.CSharp* erstellt haben, deinstallieren Sie sie mit `-u|--uninstall` und dem Pfad des Vorlagenordners:</span><span class="sxs-lookup"><span data-stu-id="2bb82-217">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="2bb82-218">Um die Vorlage aus Ihrem lokalen Dateisystem zu deinstallieren, müssen Sie den Pfad vollständig qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="2bb82-218">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="2bb82-219">Beispielsweise funktioniert zwar *C:\Benutzer\\\<BENUTZER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, jedoch nicht *.\GarciaSoftware.ConsoleTemplate.CSharp* aus dem übergeordneten Ordner.</span><span class="sxs-lookup"><span data-stu-id="2bb82-219">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="2bb82-220">Schließen Sie darüber hinaus keinen letzten abschließenden Schrägstrich in den Vorlagenpfad Ihres Verzeichnisses ein.</span><span class="sxs-lookup"><span data-stu-id="2bb82-220">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bb82-221">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bb82-221">See also</span></span>

[<span data-ttu-id="2bb82-222">dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)</span><span class="sxs-lookup"><span data-stu-id="2bb82-222">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)  
[<span data-ttu-id="2bb82-223">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="2bb82-223">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="2bb82-224">How to create your own templates for dotnet new (So erstellen Sie Ihre eigenen Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="2bb82-224">How to create your own templates for dotnet new</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)  
[<span data-ttu-id="2bb82-225">*template.json*-Schema im JSON-Schemaspeicher</span><span class="sxs-lookup"><span data-stu-id="2bb82-225">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  
