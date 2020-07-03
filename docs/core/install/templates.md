---
title: Installieren und Verwalten von SDK-Vorlagen (.NET Core)
description: Hier erfahren Sie, wie Sie .NET Core-Vorlagen unter Windows, Linux und macOS installieren.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324495"
---
# <a name="manage-net-project-and-item-templates"></a><span data-ttu-id="910bb-103">Verwalten von .NET-Projekt- und -Elementvorlagen</span><span class="sxs-lookup"><span data-stu-id="910bb-103">Manage .NET project and item templates</span></span>

<span data-ttu-id="910bb-104">.NET Core bietet ein Vorlagensystem, das Benutzern die Installation oder Deinstallation von Vorlagen über NuGet, NuGet-Paketdateien oder ein Dateisystemverzeichnis ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="910bb-104">.NET Core provides a template system that enables users to install or uninstall templates from NuGet, a NuGet package file, or a file system directory.</span></span> <span data-ttu-id="910bb-105">In diesem Artikel wird beschrieben, wie Sie .NET Core-Vorlagen über die CLI des .NET Core SDK verwalten.</span><span class="sxs-lookup"><span data-stu-id="910bb-105">This article describes how to manage .NET Core templates through the .NET Core SDK CLI.</span></span>

<span data-ttu-id="910bb-106">Weitere Informationen zum Erstellen von Vorlagen finden Sie unter [Tutorial: Erstellen von Vorlagen](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="910bb-106">For more information about creating templates, see [Tutorial: Create templates](../tutorials/cli-templates-create-item-template.md).</span></span>

## <a name="install-template"></a><span data-ttu-id="910bb-107">Installieren von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="910bb-107">Install template</span></span>

<span data-ttu-id="910bb-108">Vorlagen werden über den SDK-Befehl [dotnet new](../tools/dotnet-new.md) mit dem Parameter `-i` installiert.</span><span class="sxs-lookup"><span data-stu-id="910bb-108">Templates are installed through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-i` parameter.</span></span> <span data-ttu-id="910bb-109">Sie können entweder den NuGet-Paketbezeichner einer Vorlage oder einen Ordner angeben, der die Vorlagendateien enthält.</span><span class="sxs-lookup"><span data-stu-id="910bb-109">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-hosted-package"></a><span data-ttu-id="910bb-110">Gehostetes NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="910bb-110">NuGet hosted package</span></span>

<span data-ttu-id="910bb-111">.NET-CLI-Vorlagen werden auf [NuGet](https://www.nuget.org/) hochgeladen, damit sie breitflächig verteilt und genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="910bb-111">.NET CLI templates are uploaded to [NuGet](https://www.nuget.org/) for wide distribution.</span></span> <span data-ttu-id="910bb-112">Vorlagen können auch über einen privaten Feed installiert werden.</span><span class="sxs-lookup"><span data-stu-id="910bb-112">Templates can also be installed from a private feed.</span></span> <span data-ttu-id="910bb-113">Anstatt eine Vorlage in einen NuGet-Feed hochzuladen, können *NUPKG*-Vorlagendateien verteilt und manuell installiert werden. Weitere Informationen hierzu finden Sie im Abschnitt [Lokales NuGet-Paket](#local-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="910bb-113">Instead of uploading a template to a NuGet feed, *nupkg* template files can be distributed and manually installed, as described in the [Local NuGet package](#local-nuget-package) section.</span></span>

<span data-ttu-id="910bb-114">Weitere Informationen zum Konfigurieren von NuGet-Feeds finden Sie unter [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span><span class="sxs-lookup"><span data-stu-id="910bb-114">For more information about configuring NuGet feeds, see [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="910bb-115">Verwenden Sie zum Installieren eines Vorlagenpakets über den NuGet-Standardfeed den `dotnet new -i {package-id}`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="910bb-115">To install a template pack from the default NuGet feed, use the `dotnet new -i {package-id}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

<span data-ttu-id="910bb-116">Verwenden Sie zum Installieren eines Vorlagenpakets mit einer bestimmten Version über den NuGet-Standardfeed den `dotnet new -i {package-id}::{version}`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="910bb-116">To install a template pack from the default NuGet feed with a specific version, use the `dotnet new -i {package-id}::{version}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a><span data-ttu-id="910bb-117">Lokales NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="910bb-117">Local NuGet package</span></span>

<span data-ttu-id="910bb-118">Wenn ein Vorlagenpaket erstellt wird, wird eine *NUPKG*-Datei generiert.</span><span class="sxs-lookup"><span data-stu-id="910bb-118">When a template pack is created, a *nupkg* file is generated.</span></span> <span data-ttu-id="910bb-119">Wenn Sie eine *NUPKG*-Datei mit Vorlagen besitzen, können Sie diese mit dem Befehl `dotnet new -i {path-to-package}` installieren:</span><span class="sxs-lookup"><span data-stu-id="910bb-119">If you have a *nupkg* file containing templates, you can install it with the `dotnet new -i {path-to-package}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a><span data-ttu-id="910bb-120">Ordner</span><span class="sxs-lookup"><span data-stu-id="910bb-120">Folder</span></span>

<span data-ttu-id="910bb-121">Als Alternative zum Installieren der Vorlage über eine *NUPKG*-Datei können Sie Vorlagen auch direkt mit dem `dotnet new -i {folder-path}`-Befehl aus einem Ordner installieren.</span><span class="sxs-lookup"><span data-stu-id="910bb-121">As an alternative to installing template from a *nupkg* file, you can also install templates from a folder directly with the `dotnet new -i {folder-path}` command.</span></span> <span data-ttu-id="910bb-122">Der angegebene Ordner wird als Vorlagenpaketbezeichner für jede gefundene Vorlage behandelt.</span><span class="sxs-lookup"><span data-stu-id="910bb-122">The folder specified is treated as the template pack identifier for any template found.</span></span> <span data-ttu-id="910bb-123">Alle Vorlagen, die in der Hierarchie des angegebenen Ordners gefunden werden, werden installiert.</span><span class="sxs-lookup"><span data-stu-id="910bb-123">Any template found in the specified folder's hierarchy is installed.</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

<span data-ttu-id="910bb-124">Der `{folder-path}`-Parameter im Befehl wird zum Vorlagenpaketbezeichner für alle gefundenen Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="910bb-124">The `{folder-path}` specified on the command becomes the template pack identifier for all templates found.</span></span> <span data-ttu-id="910bb-125">Wie im Abschnitt [Auflisten von Vorlagen](#list-templates) erläutert wird, können Sie mit dem Befehl `dotnet new -u` eine Liste der installierten Vorlagen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="910bb-125">As specified in the [List templates](#list-templates) section, you can get a list of templates installed with the `dotnet new -u` command.</span></span> <span data-ttu-id="910bb-126">In diesem Beispiel wird der Vorlagenpaketbezeichner als der für die Installation verwendete Ordner angegeben:</span><span class="sxs-lookup"><span data-stu-id="910bb-126">In this example, the template pack identifier is shown as the folder used for install:</span></span>

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a><span data-ttu-id="910bb-127">Deinstallieren von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="910bb-127">Uninstall template</span></span>

<span data-ttu-id="910bb-128">Vorlagen werden über den SDK-Befehl [dotnet new](../tools/dotnet-new.md) mit dem Parameter `-u` deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="910bb-128">Templates are uninstalled through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-u` parameter.</span></span> <span data-ttu-id="910bb-129">Sie können entweder den NuGet-Paketbezeichner einer Vorlage oder einen Ordner angeben, der die Vorlagendateien enthält.</span><span class="sxs-lookup"><span data-stu-id="910bb-129">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-package"></a><span data-ttu-id="910bb-130">NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="910bb-130">NuGet package</span></span>

<span data-ttu-id="910bb-131">Nachdem ein NuGet-Vorlagenpaket entweder über einen NuGet-Feed oder eine *NUPKG*-Datei installiert wurde, können Sie dieses deinstallieren, indem Sie auf den NuGet-Paketbezeichner verweisen.</span><span class="sxs-lookup"><span data-stu-id="910bb-131">After a NuGet template pack is installed, either from a NuGet feed or a *nupkg* file, you can uninstall it by referencing the NuGet package identifier.</span></span>

<span data-ttu-id="910bb-132">Verwenden Sie zum Deinstallieren eines Vorlagenpakets den `dotnet new -u {package-id}`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="910bb-132">To uninstall a template pack, use the `dotnet new -u {package-id}` command:</span></span>

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a><span data-ttu-id="910bb-133">Ordner</span><span class="sxs-lookup"><span data-stu-id="910bb-133">Folder</span></span>

<span data-ttu-id="910bb-134">Wenn Vorlagen über einen [Ordnerpfad](#folder) installiert werden, wird der Ordnerpfad zum Vorlagenpaketbezeichner.</span><span class="sxs-lookup"><span data-stu-id="910bb-134">When templates are installed through a [folder path](#folder), the folder path becomes the template pack identifier.</span></span>

<span data-ttu-id="910bb-135">Verwenden Sie zum Deinstallieren eines Vorlagenpakets den `dotnet new -u {package-folder-path}`-Befehl:</span><span class="sxs-lookup"><span data-stu-id="910bb-135">To uninstall a template pack, use the `dotnet new -u {package-folder-path}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a><span data-ttu-id="910bb-136">Auflisten von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="910bb-136">List templates</span></span>

<span data-ttu-id="910bb-137">Wenn Sie den Standardbefehl zum Deinstallieren ohne Paketbezeichner verwenden, werden eine Liste der installierten Vorlagen und der Befehl angezeigt, mit dem Sie die jeweiligen Vorlagen deinstallieren können.</span><span class="sxs-lookup"><span data-stu-id="910bb-137">By using the standard uninstall command without a package identifier, you can see a list of installed templates along with the command that uninstalls each template.</span></span>

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a><span data-ttu-id="910bb-138">Installieren von Vorlagen über andere SDKs</span><span class="sxs-lookup"><span data-stu-id="910bb-138">Install templates from other SDKs</span></span>

<span data-ttu-id="910bb-139">Wenn Sie jede SDK-Version sequenziell installiert haben, z. B. erst SDK 2.0, dann SDK 2.1 und so weiter, sind auch die Vorlagen aller SDKs installiert.</span><span class="sxs-lookup"><span data-stu-id="910bb-139">If you've installed each version of the SDK sequentially, for example you installed SDK 2.0, then SDK 2.1, and so on, you'll have every SDK's templates installed.</span></span> <span data-ttu-id="910bb-140">Wenn Sie jedoch mit einer höheren SDK-Version wie 3.1 beginnen, sind nur die Vorlagen für [LTS-Releases (Long-Term Support, langfristige unterstützte Releases)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) enthalten, bei denen es sich zum Veröffentlichungszeitpunkt von SDK-Version 3.1 um Version 2.1 und 3.1 handelt.</span><span class="sxs-lookup"><span data-stu-id="910bb-140">However, if you start with a later SDK version, like 3.1, only the templates for [LTS (long term support) releases](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) are included, which at the time of the SDK 3.1 release is SDK 2.1 and SDK 3.1.</span></span> <span data-ttu-id="910bb-141">Vorlagen für ein andere Releases sind nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="910bb-141">Templates for any other release aren't included.</span></span>

<span data-ttu-id="910bb-142">Die .NET Core-Vorlagen sind auf NuGet verfügbar, und Sie können sie wie jede andere Vorlage installieren.</span><span class="sxs-lookup"><span data-stu-id="910bb-142">The .NET Core templates are available on NuGet, and you can install them like any other template.</span></span> <span data-ttu-id="910bb-143">Weitere Informationen finden Sie unter [Installieren von auf NuGet gehosteten Paketen](#nuget-hosted-package).</span><span class="sxs-lookup"><span data-stu-id="910bb-143">For more information, see [Install NuGet hosted package](#nuget-hosted-package).</span></span>

| <span data-ttu-id="910bb-144">SDK</span><span class="sxs-lookup"><span data-stu-id="910bb-144">SDK</span></span>              | <span data-ttu-id="910bb-145">NuGet-Paketbezeichner</span><span class="sxs-lookup"><span data-stu-id="910bb-145">NuGet Package Identifier</span></span>                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="910bb-146">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="910bb-146">.NET Core 2.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| <span data-ttu-id="910bb-147">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="910bb-147">.NET Core 2.2</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| <span data-ttu-id="910bb-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="910bb-148">.NET Core 3.0</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| <span data-ttu-id="910bb-149">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="910bb-149">.NET Core 3.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| <span data-ttu-id="910bb-150">ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="910bb-150">ASP.NET Core 2.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| <span data-ttu-id="910bb-151">ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="910bb-151">ASP.NET Core 2.2</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| <span data-ttu-id="910bb-152">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="910bb-152">ASP.NET Core 3.0</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| <span data-ttu-id="910bb-153">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="910bb-153">ASP.NET Core 3.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

<span data-ttu-id="910bb-154">Das .NET Core SDK enthält beispielsweise Vorlagen für eine Konsolen-App für .NET Core 2.1 und .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="910bb-154">For example, the .NET Core SDK includes templates for a console app targeting .NET Core 2.1 and .NET Core 3.1.</span></span> <span data-ttu-id="910bb-155">Wenn Sie die App für .NET Core 3.0 erstellen möchten, müssen Sie die Vorlagen für Version 3.0 installieren.</span><span class="sxs-lookup"><span data-stu-id="910bb-155">If you wanted to target .NET Core 3.0, you would need to install the 3.0 templates.</span></span>

01. <span data-ttu-id="910bb-156">Versuchen Sie, eine App für .NET Core 3.0 zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="910bb-156">Try creating an app that targets .NET Core 3.0.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="910bb-157">Wenn folgende Fehlermeldung angezeigt wird, müssen Sie die Vorlagen installieren.</span><span class="sxs-lookup"><span data-stu-id="910bb-157">If you see an error message, you need to install the templates.</span></span>

    > <span data-ttu-id="910bb-158">Couldn't find an installed template that matches the input, searching online for one that does... (Es wurde keine Vorlage gefunden, die mit der Eingabe übereinstimmt. Passende Vorlage wird gesucht...)</span><span class="sxs-lookup"><span data-stu-id="910bb-158">Couldn't find an installed template that matches the input, searching online for one that does...</span></span>

01. <span data-ttu-id="910bb-159">Installieren Sie die .NET Core 3.0-Projektvorlagen.</span><span class="sxs-lookup"><span data-stu-id="910bb-159">Install the .NET Core 3.0 project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. <span data-ttu-id="910bb-160">Erstellen Sie die App ein zweites Mal.</span><span class="sxs-lookup"><span data-stu-id="910bb-160">Try creating the app a second time.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="910bb-161">Jetzt sollte eine Meldung angezeigt werden, die besagt, dass das Projekt erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="910bb-161">And you should see a message indicating the project was created.</span></span>

    > <span data-ttu-id="910bb-162">The template "Console Application" was created successfully. (Die Vorlage „Konsolenanwendung“ wurde erfolgreich erstellt.)</span><span class="sxs-lookup"><span data-stu-id="910bb-162">The template "Console Application" was created successfully.</span></span>
    >
    > <span data-ttu-id="910bb-163">Processing post-creation actions... (Aktionen nach der Erstellung werden verarbeitet...) Running 'dotnet restore' on path-to-project-file.csproj... (dotnet restore wird für „Pfad_der_Projektdatei.csproj“ ausgeführt...) Determining projects to restore... (Wiederherzustellende Projekte werden ermittelt...) Restore completed in 1.05 sec for path-to-project-file.csproj. (Die Wiederherstellung von „Pfad_zur_Projektdatei.csproj“ wurde in 1,05 Sekunden abgeschlossen.)</span><span class="sxs-lookup"><span data-stu-id="910bb-163">Processing post-creation actions... Running 'dotnet restore' on path-to-project-file.csproj... Determining projects to restore... Restore completed in 1.05 sec for path-to-project-file.csproj.</span></span>
    >
    > <span data-ttu-id="910bb-164">Restore succeeded. (Wiederherstellung erfolgreich.)</span><span class="sxs-lookup"><span data-stu-id="910bb-164">Restore succeeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="910bb-165">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="910bb-165">See also</span></span>

- [<span data-ttu-id="910bb-166">Tutorial: Erstellen einer Elementvorlage</span><span class="sxs-lookup"><span data-stu-id="910bb-166">Tutorial: Create an item template</span></span>](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
