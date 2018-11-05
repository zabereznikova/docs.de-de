---
title: NuGet für .NET-Bibliotheken
description: Best Practices für die Paketerstellung mit NuGet für .NET-Bibliotheken
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185619"
---
# <a name="nuget"></a><span data-ttu-id="87a2e-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="87a2e-103">NuGet</span></span>

<span data-ttu-id="87a2e-104">NuGet ist ein Paket-Manager für das .NET-Ökosystem und das primäre System, mit dem Entwickler Open Source-Bibliotheken von .NET untersuchen und abrufen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="87a2e-105">[NuGet.org](https://www.nuget.org/) ist ein kostenloser Dienst von Microsoft zum Hosten von NuGet-Paketen und der primäre Host für öffentliche NuGet-Pakete. Sie können damit auch Veröffentlichungen in benutzerdefinierten NuGet-Diensten wie [MyGet](https://www.myget.org/) und [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/) ausführen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="87a2e-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="87a2e-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="87a2e-107">Erstellen eines NuGet-Pakets</span><span class="sxs-lookup"><span data-stu-id="87a2e-107">Create a NuGet package</span></span>

<span data-ttu-id="87a2e-108">Ein NuGet-Paket (`*.nupkg`) ist eine ZIP-Datei, die .NET-Assemblys und zugehörige Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="87a2e-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="87a2e-109">Sie haben im Wesentlichen zwei Optionen, ein NuGet-Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="87a2e-110">Der neuere und empfohlene Ansatz ist die Paketerstellung aus einem Projekt im SDK-Stil (Projektdatei, deren Inhalt mit `<Project Sdk="Microsoft.NET.Sdk">` beginnt).</span><span class="sxs-lookup"><span data-stu-id="87a2e-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="87a2e-111">Assemblys und Ziele werden dem Paket automatisch hinzugefügt und die restlichen Metadaten werden der MSBuild-Datei hinzugefügt, z.B. Paketname und Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="87a2e-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="87a2e-112">Die Kompilierung mit dem Befehl [`dotnet pack`](../../core/tools/dotnet-pack.md) gibt anstelle von Assemblys eine `*.nupkg`-Datei aus.</span><span class="sxs-lookup"><span data-stu-id="87a2e-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="87a2e-113">Der ältere Ansatz zum Erstellen eines NuGet-Pakets erfordert eine `*.nuspec`-Datei und das Befehlszeilentool `nuget.exe`.</span><span class="sxs-lookup"><span data-stu-id="87a2e-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="87a2e-114">Mit einer NUSPEC-Datei haben Sie umfangreiche Kontrolle, doch Sie müssen sorgfältig angeben, welche Assemblys und Ziele in das endgültige NuGet-Paket aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="87a2e-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="87a2e-115">Achten Sie darauf, dass Ihnen keine Fehler unterlaufen, und dass Sie nicht vergessen, die NUSPEC-Datei zu aktualisieren, nachdem Sie Änderungen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="87a2e-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="87a2e-116">Der Vorteil einer NUSPEC-Datei ist, dass Sie mit ihr NuGet-Pakete für Frameworks erstellen können, die noch keine im SDK-Projektdatei unterstützen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="87a2e-117">**✔️ Verwenden** Sie eine SDK-Projektdatei zum Erstellen des NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="87a2e-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="87a2e-118">**✔️ Richten** Sie SourceLink ein, um Ihren Assemblys und dem NuGet-Paket Metadaten der Quellcodeverwaltung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="87a2e-119">Paketabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="87a2e-119">Package dependencies</span></span>

<span data-ttu-id="87a2e-120">Abhängigkeiten von NuGet-Paketen werden im Artikel [Abhängigkeiten](./dependencies.md) ausführlich erläutert.</span><span class="sxs-lookup"><span data-stu-id="87a2e-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="87a2e-121">Wichtige Metadaten von NuGet-Paketen</span><span class="sxs-lookup"><span data-stu-id="87a2e-121">Important NuGet package metadata</span></span>

<span data-ttu-id="87a2e-122">Ein NuGet-Paket unterstützt viele [Metadateneigenschaften](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="87a2e-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="87a2e-123">Die folgende Tabelle enthält die wichtigsten Metadaten, die jedes Open Source-Projekt bereitstellen sollte:</span><span class="sxs-lookup"><span data-stu-id="87a2e-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="87a2e-124">MSBuild-Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="87a2e-124">MSBuild Property name</span></span>              | <span data-ttu-id="87a2e-125">NUSPEC-Name</span><span class="sxs-lookup"><span data-stu-id="87a2e-125">Nuspec name</span></span>              | <span data-ttu-id="87a2e-126">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="87a2e-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="87a2e-127">Der Paketbezeichner.</span><span class="sxs-lookup"><span data-stu-id="87a2e-127">The package identifier.</span></span> <span data-ttu-id="87a2e-128">Ein Präfix aus dem Bezeichner kann reserviert werden, wenn es die [Kriterien](/nuget/reference/id-prefix-reservation) erfüllt.</span><span class="sxs-lookup"><span data-stu-id="87a2e-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="87a2e-129">Die NuGet-Paketversion.</span><span class="sxs-lookup"><span data-stu-id="87a2e-129">NuGet package version.</span></span> <span data-ttu-id="87a2e-130">Weitere Informationen finden Sie unter [NuGet-Paketversion](./versioning.md#nuget-package-version).</span><span class="sxs-lookup"><span data-stu-id="87a2e-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="87a2e-131">Ein benutzerfreundlicher Pakettitel.</span><span class="sxs-lookup"><span data-stu-id="87a2e-131">A human-friendly title of the package.</span></span> <span data-ttu-id="87a2e-132">Er entspricht standardmäßig `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="87a2e-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="87a2e-133">Eine ausführliche Beschreibung des Pakets, die in der Benutzeroberfläche angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="87a2e-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="87a2e-134">Eine durch Trennzeichen getrennte Liste von Paketerstellern, die den Profilnamen auf nuget.org entspricht.</span><span class="sxs-lookup"><span data-stu-id="87a2e-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="87a2e-135">Eine durch Leerzeichen getrennte Liste von Tags und Schlüsselwörtern, die das Paket beschreiben.</span><span class="sxs-lookup"><span data-stu-id="87a2e-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="87a2e-136">Tags werden bei der Suche nach Paketen verwendet.</span><span class="sxs-lookup"><span data-stu-id="87a2e-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="87a2e-137">Eine URL für ein Bild, das als Symbol für das Paket verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87a2e-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="87a2e-138">Es muss sich um eine HTTPS-URL handeln, und das Bild muss die Maße 64x64 sowie einen transparenten Hintergrund haben.</span><span class="sxs-lookup"><span data-stu-id="87a2e-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="87a2e-139">Eine URL für die Projekthomepage oder das Quellrepository.</span><span class="sxs-lookup"><span data-stu-id="87a2e-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="87a2e-140">Eine URL für die Projektlizenz.</span><span class="sxs-lookup"><span data-stu-id="87a2e-140">A URL to the project license.</span></span> <span data-ttu-id="87a2e-141">Es kann die URL zur Datei `LICENSE` in der Quellcodeverwaltung sein.</span><span class="sxs-lookup"><span data-stu-id="87a2e-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="87a2e-142">**✔️ Wählen** Sie einen NuGet-Paketnamen mit einem Präfix aus, das den [Kriterien](/nuget/reference/id-prefix-reservation) der NuGet-Präfixreservierung entspricht.</span><span class="sxs-lookup"><span data-stu-id="87a2e-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="87a2e-143">**✔️ Verwenden** Sie die `LICENSE`-Datei in der Quellcodeverwaltung als `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="87a2e-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="87a2e-144">Beispiel: [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="87a2e-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87a2e-145">Ein Projekt ohne Lizenz unterliegt standardmäßig [exklusivem Copyright](https://choosealicense.com/no-permission/), sodass es nicht von anderen Benutzern verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="87a2e-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="87a2e-146">**✔️ Verwenden** Sie einen HTTPS-Hypertextverweis für Ihr Paketsymbol.</span><span class="sxs-lookup"><span data-stu-id="87a2e-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="87a2e-147">Websites wie NuGet.org werden mit aktiviertem HTTPS ausgeführt, und die Anzeige eines Nicht-HTTPS-Bildes generiert eine Warnung vor gemischten Inhalten.</span><span class="sxs-lookup"><span data-stu-id="87a2e-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="87a2e-148">**✔️ Verwenden** Sie ein Paketsymbolbild, das 64x64 groß ist und einen transparenten Hintergrund für die ideale Darstellung hat.</span><span class="sxs-lookup"><span data-stu-id="87a2e-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="87a2e-149">Vorabversionen von Paketen</span><span class="sxs-lookup"><span data-stu-id="87a2e-149">Pre-release packages</span></span>

<span data-ttu-id="87a2e-150">NuGet-Pakete mit einem Versionssuffix gelten als [Vorabversion](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="87a2e-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="87a2e-151">Standardmäßig zeigt die Benutzeroberfläche des NuGet-Paket-Managers stabile Versionen an, es sei denn, ein Benutzer veröffentlicht Pakete vorab – Vorabversionspakete eignen sich ideal für eingeschränkte Benutzertests.</span><span class="sxs-lookup"><span data-stu-id="87a2e-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="87a2e-152">Ein stabiles Paket kann nicht von einem Vorabversionspaket abhängen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="87a2e-153">Sie müssen entweder Ihr eigenes Paket vorab veröffentlichen oder eine ältere stabile Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="87a2e-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="87a2e-154">![NuGet-Vorabversions-Paketabhängigkeit](./media/nuget/nuget-prerelease-package.png "NuGet-Vorabversions-Paketabhängigkeit")</span><span class="sxs-lookup"><span data-stu-id="87a2e-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="87a2e-155">**✔️ Veröffentlichen** Sie ein Vorabversionspaket für Tests und Vorschauen.</span><span class="sxs-lookup"><span data-stu-id="87a2e-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="87a2e-156">**✔️ Veröffentlichen** Sie ein stabiles Paket, wenn es fertig ist, sodass andere stabile Pakete es referenzieren können.</span><span class="sxs-lookup"><span data-stu-id="87a2e-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="87a2e-157">Symbolpakete</span><span class="sxs-lookup"><span data-stu-id="87a2e-157">Symbol packages</span></span>

<span data-ttu-id="87a2e-158">Symboldateien (`*.pdb`) werden vom .NET-Compiler neben Assemblys erstellt.</span><span class="sxs-lookup"><span data-stu-id="87a2e-158">Symbol files (`*.pdb`) are produced by the .NET compiler alongside assemblies.</span></span> <span data-ttu-id="87a2e-159">Symboldateien ordnen Ausführungsstandorte dem ursprünglichen Quellcode zu, sodass Sie den Quellcode bei der Ausführung mit einem Debugger durchgehen können.</span><span class="sxs-lookup"><span data-stu-id="87a2e-159">Symbol files map execution locations to the original source code so you can step through source code as it is running using a debugger.</span></span> <span data-ttu-id="87a2e-160">NuGet unterstützt das [Generieren eines separaten Symbolpakets](/nuget/create-packages/symbol-packages) mit Symboldateien neben dem Hauptpaket mit .NET-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="87a2e-160">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing symbol files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="87a2e-161">Die Idee von Symbolpaketen ist, dass sie auf einem Symbolserver gehostet und nur bei Bedarf von einem Tool wie Visual Studio heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="87a2e-161">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="87a2e-162">Derzeit unterstützt der öffentliche Haupthost für Symbole – [SymbolSource](http://www.symbolsource.org/) – nicht die neuen [portablen Symboldateien](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`), die von SDK-Projekten erstellt wurden. Das bedeutet, Symbolpakete sind nicht nützlich.</span><span class="sxs-lookup"><span data-stu-id="87a2e-162">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the new [portable symbol files](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span> <span data-ttu-id="87a2e-163">Bis es einen empfohlenen Host für Symbolpakete gibt, können Symboldateien in das Hauptpaket von NuGet eingebettet werden.</span><span class="sxs-lookup"><span data-stu-id="87a2e-163">Until there is a recommended host for symbol packages, symbol files can be embedded in the main NuGet package.</span></span> <span data-ttu-id="87a2e-164">Wenn Sie Ihr NuGet-Paket mit einem SDK-Projekt erstellen, können Sie Symboldateien einbetten, indem Sie die Eigenschaft `AllowedOutputExtensionsInPackageBuildOutputFolder` festlegen:</span><span class="sxs-lookup"><span data-stu-id="87a2e-164">If you are building your NuGet package using an SDK-style project you can embed symbol files by setting the `AllowedOutputExtensionsInPackageBuildOutputFolder` property:</span></span> 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="87a2e-165">**✔️ Betten** Sie Symboldateien in das NuGet-Hauptpaket ein.</span><span class="sxs-lookup"><span data-stu-id="87a2e-165">**✔️ CONSIDER** embedding symbol files in the main NuGet package.</span></span>

<span data-ttu-id="87a2e-166">**❌ Erstellen** Sie kein Symbolpaket mit Symboldateien.</span><span class="sxs-lookup"><span data-stu-id="87a2e-166">**❌ AVOID** creating a symbols package containing symbol files.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="87a2e-167">[Zurück](./strong-naming.md)
[Weiter](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="87a2e-167">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
