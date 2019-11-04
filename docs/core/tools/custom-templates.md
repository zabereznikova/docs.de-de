---
title: Benutzerdefinierte Vorlagen für dotnet new
description: Erfahren Sie mehr zu benutzerdefinierten Vorlagen für alle Arten von .NET-Projekten und -Dateien.
author: thraka
ms.date: 06/14/2019
ms.openlocfilehash: 8e1ac4ca21a8a90ad0f7c9bd3dd11281eb4a6e02
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420882"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="03b8d-103">Benutzerdefinierte Vorlagen für dotnet new</span><span class="sxs-lookup"><span data-stu-id="03b8d-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="03b8d-104">Das [.NET Core SDK](https://dotnet.microsoft.com/download) enthält viele Vorlagen, die bereits installiert und sofort einsatzbereit sind.</span><span class="sxs-lookup"><span data-stu-id="03b8d-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="03b8d-105">Der Befehl [`dotnet new`](dotnet-new.md) bietet nicht nur eine Möglichkeit, eine Vorlage zu verwenden, sondern auch, um Vorlagen zu installieren und zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="03b8d-106">Ab .NET Core 2.0 können Sie Ihre eigenen benutzerdefinierten Vorlagen für jeden Projekttyp (App, Dienst, Tool, Klassenbibliothek usw.) erstellen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="03b8d-107">Sie könne sogar eine Vorlage erstellen, die mindestens eine unabhängige Datei ausgibt, wie z.B. eine Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="03b8d-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="03b8d-108">Sie können benutzerdefinierte Vorlagen aus NuGet-Paketen in jedem NuGet-Feed installieren, indem Sie direkt auf eine NuGet-Datei des Typs *.nupkg* verweisen, oder indem Sie ein Dateisystemverzeichnis angeben, das die Vorlage enthält.</span><span class="sxs-lookup"><span data-stu-id="03b8d-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="03b8d-109">Das Vorlagenmodul bietet Features, mit denen Sie Werte ersetzen, Dateien ein- oder ausschließen und benutzerdefinierte Verarbeitungsvorgänge ausführen können, wenn Ihre Vorlage verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03b8d-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="03b8d-110">Die Vorlagen-Engine ist Open Source, und das Onlinecoderepository befindet sich unter [dotnet/templating](https://github.com/dotnet/templating/) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="03b8d-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="03b8d-111">Navigieren Sie zum Repository [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples), wo sie Beispielvorlagen finden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-111">Visit the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) repo for samples of templates.</span></span> <span data-ttu-id="03b8d-112">Weitere Vorlagen, einschließlich Drittanbietervorlagen, finden Sie auf GitHub unter [Verfügbare Vorlagen für dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new).</span><span class="sxs-lookup"><span data-stu-id="03b8d-112">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="03b8d-113">Weitere Informationen zum Erstellen und Verwenden von benutzerdefinierten Vorlagen finden Sie unter [How to create your own templates for dotnet new (Erstellen Ihrer eigenen Vorlage für dotnet new)](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) und im [GitHub-Repositorywiki dotnet/templating](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="03b8d-113">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="03b8d-114">Eine exemplarische Vorgehensweise zum Erstellen einer Vorlage finden Sie im Tutorial [Create a custom template for dotnet new (in englischer Sprache)](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="03b8d-114">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="03b8d-115">.NET-Standardvorlagen</span><span class="sxs-lookup"><span data-stu-id="03b8d-115">.NET default templates</span></span>

<span data-ttu-id="03b8d-116">Wenn Sie das [.NET Core SDK](https://dotnet.microsoft.com/download) installieren, erhalten Sie mehr als zwölf integrierte Vorlagen zum Erstellen von Projekten und Dateien, einschließlich Konsolenanwendungen, Klassenbibliotheken, Komponententestprojekten, ASP.NET Core-Apps (einschließlich [Angular](https://angular.io/)- und [React](https://facebook.github.io/react/)-Projekten), und von Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="03b8d-116">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="03b8d-117">Um die integrierten Vorlagen aufzulisten, führen Sie den `dotnet new`-Befehl mit der `-l|--list`-Option aus:</span><span class="sxs-lookup"><span data-stu-id="03b8d-117">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="03b8d-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="03b8d-118">Configuration</span></span>

<span data-ttu-id="03b8d-119">Eine Vorlage besteht aus den folgenden Teilen:</span><span class="sxs-lookup"><span data-stu-id="03b8d-119">A template is composed of the following parts:</span></span>

- <span data-ttu-id="03b8d-120">Quelldateien und -ordner</span><span class="sxs-lookup"><span data-stu-id="03b8d-120">Source files and folders.</span></span>
- <span data-ttu-id="03b8d-121">Konfigurationsdatei (*template.json*)</span><span class="sxs-lookup"><span data-stu-id="03b8d-121">A configuration file (*template.json*).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="03b8d-122">Quelldateien und -ordner</span><span class="sxs-lookup"><span data-stu-id="03b8d-122">Source files and folders</span></span>

<span data-ttu-id="03b8d-123">Die Quelldateien und -ordner enthalten die Dateien und Ordner, von denen Sie möchten, dass sie vom Vorlagenmodul verwendet werden, wenn der `dotnet new <TEMPLATE>`-Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="03b8d-123">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="03b8d-124">Die Vorlagen-Engine wurde so entwickelt, dass sie *ausführbare Projekte* als Quellcode verwendet, um Projekte zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-124">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="03b8d-125">Dies hat mehrere Vorteile:</span><span class="sxs-lookup"><span data-stu-id="03b8d-125">This has several benefits:</span></span>

- <span data-ttu-id="03b8d-126">Sie müssen für die Vorlagen-Engine keine besonderen Token in den Quellcode Ihres Projekts einfügen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-126">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="03b8d-127">Die Codedateien sind keine besonderen Dateien. Sie werden auch nicht modifiziert, um mit der Vorlagen-Engine zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-127">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="03b8d-128">Die Tools, die Sie normalerweise mit Projekten verwenden, funktionieren auch mit Vorlageninhalt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-128">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="03b8d-129">Das Erstellen, Ausführen und Debuggen Ihrer Projekte erfolgt wie bei Ihren anderen Projekten.</span><span class="sxs-lookup"><span data-stu-id="03b8d-129">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="03b8d-130">Sie können eine Vorlage schnell anhand eines vorhandenen Projekts erstellen, indem Sie einfach die Konfigurationsdatei *./.template.config/template.json* dem Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-130">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="03b8d-131">In der Vorlage gespeicherte Dateien und Ordner sind nicht auf formelle .NET-Projekttypen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-131">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="03b8d-132">Quelldateien und -ordner können aus jedem beliebigen Inhalt bestehen, den Sie erstellen möchten, wenn die Vorlage verwendet wird, auch wenn das Vorlagenmodul nur eine Datei ausgibt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-132">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="03b8d-133">Dateien, die anhand der Vorlage generiert werden, können basierend auf der Logik und den Einstellungen, die Sie in der Konfigurationsdatei *template.json* angegeben haben, geändert werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-133">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="03b8d-134">Der Benutzer kann diese Einstellungen überschreiben, indem er Optionen an den Befehl `dotnet new <TEMPLATE>` übergibt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-134">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="03b8d-135">Ein häufiges Beispiel für benutzerdefinierte Logik ist die Bereitstellung eines Namens für eine Klasse oder Variable in der Codedatei, die von einer Vorlage bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="03b8d-135">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="03b8d-136">template.json</span><span class="sxs-lookup"><span data-stu-id="03b8d-136">template.json</span></span>

<span data-ttu-id="03b8d-137">Die Datei *template.json* wird in den Ordner *template.config* im Stammverzeichnis der Vorlage platziert.</span><span class="sxs-lookup"><span data-stu-id="03b8d-137">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="03b8d-138">Die Datei bietet der Vorlagen-Engine Konfigurationsinformationen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-138">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="03b8d-139">Die Mindestkonfiguration erfordert die in der folgenden Tabelle aufgelisteten Member, was zum Erstellen einer funktionsfähigen Vorlage ausreicht.</span><span class="sxs-lookup"><span data-stu-id="03b8d-139">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="03b8d-140">Member</span><span class="sxs-lookup"><span data-stu-id="03b8d-140">Member</span></span>            | <span data-ttu-id="03b8d-141">Typ</span><span class="sxs-lookup"><span data-stu-id="03b8d-141">Type</span></span>          | <span data-ttu-id="03b8d-142">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="03b8d-142">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="03b8d-143">URI</span><span class="sxs-lookup"><span data-stu-id="03b8d-143">URI</span></span>           | <span data-ttu-id="03b8d-144">Das JSON-Schema für die Datei *template.json*.</span><span class="sxs-lookup"><span data-stu-id="03b8d-144">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="03b8d-145">Editor, die JSON-Schemas unterstützen, ermöglichen Features zum Bearbeiten von JSON-Dateien, wenn das Schema angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="03b8d-145">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="03b8d-146">[Visual Studio-Code](https://code.visualstudio.com/) erfordert z.B., dass dieser Member IntelliSense aktiviert.</span><span class="sxs-lookup"><span data-stu-id="03b8d-146">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="03b8d-147">Verwenden Sie den Wert `http://json.schemastore.org/template`.</span><span class="sxs-lookup"><span data-stu-id="03b8d-147">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="03b8d-148">string</span><span class="sxs-lookup"><span data-stu-id="03b8d-148">string</span></span>        | <span data-ttu-id="03b8d-149">Der Autor der Vorlage.</span><span class="sxs-lookup"><span data-stu-id="03b8d-149">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="03b8d-150">array(string)</span><span class="sxs-lookup"><span data-stu-id="03b8d-150">array(string)</span></span> | <span data-ttu-id="03b8d-151">Null (0) oder mehr Merkmale der Vorlage, die ein Benutzer verwenden kann, um die Vorlage zu finden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-151">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="03b8d-152">Die Klassifizierungen werden auch in der Spalte *Tags* angezeigt, wenn diese in einer Liste von Vorlagen angezeigt wird, die mit dem `dotnet new -l|--list`-Befehl erzeugt wurden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-152">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="03b8d-153">string</span><span class="sxs-lookup"><span data-stu-id="03b8d-153">string</span></span>        | <span data-ttu-id="03b8d-154">Ein eindeutiger Namen für diese Vorlage</span><span class="sxs-lookup"><span data-stu-id="03b8d-154">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="03b8d-155">string</span><span class="sxs-lookup"><span data-stu-id="03b8d-155">string</span></span>        | <span data-ttu-id="03b8d-156">Der Name der Vorlage, der Benutzern angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="03b8d-156">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="03b8d-157">string</span><span class="sxs-lookup"><span data-stu-id="03b8d-157">string</span></span>        | <span data-ttu-id="03b8d-158">Ein Standardkurzname zum Auswählen der Vorlage, die für Umgebungen gilt, in denen der Vorlagenname vom Benutzer angegeben wird und nicht über eine grafische Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="03b8d-158">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="03b8d-159">Die Kurzform kann z.B. nützlich sein, wenn Sie Vorlagen aus einer Eingabeaufforderung mit CLI-Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-159">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

<span data-ttu-id="03b8d-160">Das vollständige Schema für die Datei *template.json* finden Sie im [JSON-Schemaspeicher](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="03b8d-160">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="03b8d-161">Weitere Informationen zur Datei *template.json* finden Sie im [Wiki zur Erstellung von .NET-Vorlagen](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="03b8d-161">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="03b8d-162">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03b8d-162">Example</span></span>

<span data-ttu-id="03b8d-163">Hier ist zum Beispiel ein Vorlagenordner, der zwei Inhaltsdateien enthält: *console.cs* und *readme.txt*.</span><span class="sxs-lookup"><span data-stu-id="03b8d-163">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt*.</span></span> <span data-ttu-id="03b8d-164">Beachten Sie, dass es den erforderlichen Ordner namens *.template.config* gibt, der die Datei *template.json* enthält.</span><span class="sxs-lookup"><span data-stu-id="03b8d-164">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="03b8d-165">Die Datei *template.json* sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="03b8d-165">The *template.json* file looks like the following:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

<span data-ttu-id="03b8d-166">Der Ordner *mytemplate* ist ein installierbares Vorlagenpaket.</span><span class="sxs-lookup"><span data-stu-id="03b8d-166">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="03b8d-167">Sobald das Paket installiert ist, kann `shortName` mit dem Befehl `dotnet new` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-167">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="03b8d-168">Beispielsweise würde `dotnet new adatumconsole` die Dateien `console.cs` und `readme.txt` im aktuellen Ordner ausgeben.</span><span class="sxs-lookup"><span data-stu-id="03b8d-168">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="03b8d-169">Verpacken einer Vorlage in ein NuGet-Paket (NUPKG-Datei)</span><span class="sxs-lookup"><span data-stu-id="03b8d-169">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="03b8d-170">Eine benutzerdefinierte Vorlage wird mit dem Befehl [dotnet pack](dotnet-pack.md) und *CSPROJ*-Datei gepackt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-170">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="03b8d-171">Alternativ kann [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) mit dem Befehl [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) zusammen mit einer *NUSPEC*-Datei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-171">Alternatively, [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="03b8d-172">NuGet setzt jedoch das .NET Framework unter Windows und [Mono](https://www.mono-project.com/) unter Linux und macOS voraus.</span><span class="sxs-lookup"><span data-stu-id="03b8d-172">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and MacOS.</span></span>

<span data-ttu-id="03b8d-173">Die *CSPROJ*-Datei unterscheidet sich geringfügig von einer herkömmlichen Codeprojektdatei des Typs *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="03b8d-173">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="03b8d-174">Beachten Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="03b8d-174">Note the following settings:</span></span>

01. <span data-ttu-id="03b8d-175">Die Einstellung `<PackageType>` wird hinzugefügt und auf `Template` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-175">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="03b8d-176">Die Einstellung `<PackageVersion>` wird hinzugefügt und auf eine gültige [NuGet-Versionsnummer](/nuget/reference/package-versioning) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-176">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="03b8d-177">Die Einstellung `<PackageId>` wird hinzugefügt und auf einen eindeutigen Bezeichner festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-177">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="03b8d-178">Dieser Bezeichner dient zur Deinstallation des Vorlagenpakets und wird von NuGet-Feeds verwendet, um Ihr Vorlagenpaket zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-178">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="03b8d-179">Allgemeine Metadateneinstellungen müssen festgelegt werden: `<Title>`, `<Authors>`, `<Description>` und `<PackageTags>`.</span><span class="sxs-lookup"><span data-stu-id="03b8d-179">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="03b8d-180">Die Einstellung `<TargetFramework>` muss festgelegt werden, auch wenn die vom Vorlagenprozess generierte Binärdatei nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03b8d-180">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="03b8d-181">Im folgenden Beispiel wird sie auf `netstandard2.0` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-181">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="03b8d-182">Ein Vorlagenpaket in Form eines NuGet-Paket des Typs *.nupkg*. erfordert, dass alle Vorlagen im Ordner *content* innerhalb des Pakets gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-182">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="03b8d-183">Es gibt noch einige weitere Einstellungen, die einer *CSPROJ*-Datei hinzugefügt werden müssen, um sicherzustellen, dass die generierte *NUPKG*-Datei als Vorlagenpaket installiert werden kann:</span><span class="sxs-lookup"><span data-stu-id="03b8d-183">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="03b8d-184">Die Einstellung `<IncludeContentInPack>` wird auf `true` festgelegt, um jede Datei, die das Projekt als **Inhalt** einstuft, in das NuGet-Paket aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-184">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="03b8d-185">Die Einstellung `<IncludeBuildOutput>` wird auf `false` festgelegt, um alle vom Compiler erzeugten Binärdateien aus dem NuGet-Paket auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-185">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="03b8d-186">Die Einstellung `<ContentTargetFolders>` wird auf `content` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-186">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="03b8d-187">Dadurch wird sichergestellt, dass die als **Inhalt** festgelegten Dateien im Ordner *content* im NuGet-Paket gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-187">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="03b8d-188">Dieser Ordner im NuGet-Paket wird vom .NET-Vorlagensystem analysiert.</span><span class="sxs-lookup"><span data-stu-id="03b8d-188">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="03b8d-189">Eine einfache Möglichkeit, alle Codedateien von der Kompilierung durch Ihr Vorlagenprojekt auszuschließen, besteht darin, das Element `<Compile Remove="**\*" />` in Ihrer Projektdatei innerhalb eines Elements des Typs `<ItemGroup>` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-189">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="03b8d-190">Eine einfache Möglichkeit, Ihr Vorlagenpaket zu strukturieren, besteht darin, alle Vorlagen in einzelnen Ordnern und dann jeden Vorlagenordner innerhalb eines Ordners des Typs *templates* abzulegen, der sich im gleichen Verzeichnis wie Ihre *CSPROJ*-Datei befindet.</span><span class="sxs-lookup"><span data-stu-id="03b8d-190">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="03b8d-191">Auf diese Weise können Sie ein einzelnes Projektelement verwenden, um alle Dateien und Ordner als **Inhalt** in die *Vorlagen* aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="03b8d-191">This way, you can use a single project item to include all files and folders in the *templates* as **content**.</span></span> <span data-ttu-id="03b8d-192">Erstellen Sie innerhalb eines `<ItemGroup>`-Elements ein `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`-Element.</span><span class="sxs-lookup"><span data-stu-id="03b8d-192">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="03b8d-193">Hier ein Beispiel einer *CSPROJ*-Datei, die alle obigen Vorgaben erfüllt.</span><span class="sxs-lookup"><span data-stu-id="03b8d-193">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="03b8d-194">Der untergeordnete Ordner *templates* wird im Paketordner *content* gepackt, wobei alle Codedateien von der Kompilierung ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-194">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="03b8d-195">Das folgende Beispiel veranschaulicht die Datei- und Ordnerstruktur bei Verwendung einer *CSPROJ*-Datei zum Erstellen eines Vorlagenpakets.</span><span class="sxs-lookup"><span data-stu-id="03b8d-195">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="03b8d-196">Die Datei *MyDotnetTemplates.csproj* und der Ordner *templates* befinden sich beide im Stammverzeichnis eines Verzeichnisses namens *project_folder*.</span><span class="sxs-lookup"><span data-stu-id="03b8d-196">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder*.</span></span> <span data-ttu-id="03b8d-197">Der Ordner *templates* enthält zwei Vorlagen: *mytemplate1* und *mytemplate2*.</span><span class="sxs-lookup"><span data-stu-id="03b8d-197">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2*.</span></span> <span data-ttu-id="03b8d-198">Jede Vorlage weist Inhaltsdateien und den Ordner *.template.config* mit der Konfigurationsdatei *template.json* auf.</span><span class="sxs-lookup"><span data-stu-id="03b8d-198">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a><span data-ttu-id="03b8d-199">Installieren einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="03b8d-199">Installing a template</span></span>

<span data-ttu-id="03b8d-200">Verwenden Sie den Befehl [dotnet new -i|----install](dotnet-new.md), um ein Paket zu installieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-200">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="03b8d-201">So installieren Sie eine Vorlage aus einem NuGet-Paket, das auf nuget.org gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="03b8d-201">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="03b8d-202">Verwenden Sie die NuGet-Paket-ID, um ein Vorlagenpaket zu installieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-202">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="03b8d-203">So installieren Sie eine Vorlage aus einer lokalen NUPKG-Datei</span><span class="sxs-lookup"><span data-stu-id="03b8d-203">To install a template from a local nupkg file</span></span>

<span data-ttu-id="03b8d-204">Geben Sie den Pfad zu einer NuGet-Paketdatei des Typs *.nupkg* an.</span><span class="sxs-lookup"><span data-stu-id="03b8d-204">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="03b8d-205">So installieren Sie eine Vorlage aus einem Dateisystemverzeichnis</span><span class="sxs-lookup"><span data-stu-id="03b8d-205">To install a template from a file system directory</span></span>

<span data-ttu-id="03b8d-206">Vorlagen können aus einem Vorlagenordner installiert werden, z.B. dem Ordner *mytemplate1* im obigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="03b8d-206">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="03b8d-207">Geben Sie den Ordnerpfad des Ordners *.template.config* an.</span><span class="sxs-lookup"><span data-stu-id="03b8d-207">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="03b8d-208">Der Pfad zum Vorlagenverzeichnis muss nicht absolut sein.</span><span class="sxs-lookup"><span data-stu-id="03b8d-208">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="03b8d-209">Allerdings ist ein absoluter Pfad erforderlich, um eine Vorlage zu deinstallieren, die aus einem Ordner installiert wird.</span><span class="sxs-lookup"><span data-stu-id="03b8d-209">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="03b8d-210">Abrufen einer Liste installierter Vorlagen</span><span class="sxs-lookup"><span data-stu-id="03b8d-210">Get a list of installed templates</span></span>

<span data-ttu-id="03b8d-211">Der Deinstallationsbefehl (ohne weitere Parameter) listet alle installierten Vorlagen auf.</span><span class="sxs-lookup"><span data-stu-id="03b8d-211">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="03b8d-212">Dieser Befehl gibt etwas Ähnliches wie die folgende Ausgabe zurück:</span><span class="sxs-lookup"><span data-stu-id="03b8d-212">That command returns something similar to the following output:</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

<span data-ttu-id="03b8d-213">Die erste Ebene der Elemente nach `Currently installed items:` sind die Bezeichner, die bei der Deinstallation einer Vorlage verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-213">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="03b8d-214">Und im obigen Beispiel sind `Microsoft.DotNet.Common.ItemTemplates` und `Microsoft.DotNet.Common.ProjectTemplates.3.0` aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="03b8d-214">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="03b8d-215">Wenn die Vorlage unter Verwendung eines Dateisystempfads installiert wurde, wird dieser Bezeichner zum Ordnerpfad des Ordners *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="03b8d-215">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="03b8d-216">Deinstallieren einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="03b8d-216">Uninstalling a template</span></span>

<span data-ttu-id="03b8d-217">Verwenden Sie den Befehl [dotnet new -u|--uninstall](dotnet-new.md), um ein Paket zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-217">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="03b8d-218">Wenn das Paket entweder über einen NuGet-Feed oder direkt über eine *NUPKG*-Datei installiert wurde, geben Sie den Bezeichner an.</span><span class="sxs-lookup"><span data-stu-id="03b8d-218">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="03b8d-219">Wenn das Paket durch Angabe eines Pfads zum Ordner *.template.config* installiert wurde, verwenden Sie diesen **absoluten** Pfad, um das Paket zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="03b8d-219">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="03b8d-220">Sie können den absoluten Pfad der Vorlage in der Ausgabe des Befehls `dotnet new -u` finden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-220">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="03b8d-221">Weitere Informationen finden Sie im Abschnitt [Liste installierter Vorlagen](#get-a-list-of-installed-templates) weiter oben.</span><span class="sxs-lookup"><span data-stu-id="03b8d-221">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="03b8d-222">Erstellen einer Projekt mit einer benutzerdefinierten Vorlage</span><span class="sxs-lookup"><span data-stu-id="03b8d-222">Create a project using a custom template</span></span>

<span data-ttu-id="03b8d-223">Nachdem eine Vorlage installiert wurde, verwenden Sie die Vorlage, indem Sie den `dotnet new <TEMPLATE>`-Befehl ausführen, wie Sie es auch mit jeder anderen vorinstallierten Vorlage machen würden.</span><span class="sxs-lookup"><span data-stu-id="03b8d-223">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="03b8d-224">Sie können zudem [Optionen](dotnet-new.md#options) für den `dotnet new`-Befehl festlegen, einschließlich vorlagenspezifischer Optionen, die Sie in den Vorlageneinstellungen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="03b8d-224">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="03b8d-225">Geben Sie die Kurzform des Namens der Vorlage für den Befehl an:</span><span class="sxs-lookup"><span data-stu-id="03b8d-225">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="03b8d-226">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03b8d-226">See also</span></span>

- [<span data-ttu-id="03b8d-227">Create a custom template for dotnet new (tutorial) (Erstellen einer benutzerdefinierten Vorlage für dotnet new (Tutorial))</span><span class="sxs-lookup"><span data-stu-id="03b8d-227">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="03b8d-228">dotnet/templating GitHub repo Wiki (GitHub-Repositorywiki dotnet/templating)</span><span class="sxs-lookup"><span data-stu-id="03b8d-228">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="03b8d-229">dotnet/dotnet-template-samples-GitHub-Repository</span><span class="sxs-lookup"><span data-stu-id="03b8d-229">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="03b8d-230">How to create your own templates for dotnet new (So erstellen Sie Ihre eigenen Vorlagen für dotnet new)</span><span class="sxs-lookup"><span data-stu-id="03b8d-230">How to create your own templates for dotnet new</span></span>](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- [<span data-ttu-id="03b8d-231">*template.json*-Schema im JSON-Schemaspeicher</span><span class="sxs-lookup"><span data-stu-id="03b8d-231">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
