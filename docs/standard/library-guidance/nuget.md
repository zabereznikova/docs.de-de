---
title: Bibliotheken von NuGet und .NET
description: Empfehlungen für bewährte Methoden für die paketerstellung mit NuGet Bibliotheken für .NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374492"
---
# <a name="nuget"></a><span data-ttu-id="7b7c0-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="7b7c0-103">NuGet</span></span>

<span data-ttu-id="7b7c0-104">NuGet ist ein Paket-Manager für das Ökosystem von .NET und der primären Entwickler ermitteln und Abrufen von .NET Open Source-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="7b7c0-105">["NuGet.org"](https://www.nuget.org/), ein kostenloser Dienst, der von Microsoft bereitgestellt werden, für das Hosten von NuGet-Pakete, ist der primäre Host für Öffentliche NuGet-Pakete, aber Sie können in benutzerdefinierten NuGet-Dienste wie Veröffentlichen [MyGet](https://www.myget.org/) und [Azure-Artefakte ](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="7b7c0-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="7b7c0-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="7b7c0-107">Erstellen Sie ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="7b7c0-107">Create a NuGet package</span></span>

<span data-ttu-id="7b7c0-108">Ein NuGet-Paket (`*.nupkg`) ist eine Zipdatei, .NET-Assemblys und zugehörige Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="7b7c0-109">Es gibt zwei Hauptmethoden zum Erstellen eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="7b7c0-110">Die neuere und empfohlene Möglichkeit zum Erstellen eines Pakets aus einem Projekt von SDK-Stil ist (die Projektdatei, deren Inhalt beginnt mit `<Project Sdk="Microsoft.NET.Sdk">`).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="7b7c0-111">Assemblys und Ziele werden automatisch auf das Paket hinzugefügt, und verbleibende Metadaten die MSBuild-Datei, z. B. Name und Version Paket hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="7b7c0-112">Beim Kompilieren mit der [ `dotnet pack` ](../../core/tools/dotnet-pack.md) Befehl Ausgaben eine `*.nupkg` Datei statt Assemblys.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

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

<span data-ttu-id="7b7c0-113">Die ältere Möglichkeit zum Erstellen eines NuGet-Pakets ein `*.nuspec` Datei und die `nuget.exe` -Befehlszeilentool.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="7b7c0-114">Eine Nuspec-Datei bietet Ihnen eine bessere Kontrolle, aber Sie müssen sorgfältig angeben, welche Assemblys und die Ziele in das endgültige NuGet-Paket eingeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="7b7c0-115">Es ist einfach, ein Fehler unterläuft oder für eine Person vergessen, die NuSpec-Datei zu aktualisieren, wenn Sie Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="7b7c0-116">Der Vorteil einer NuSpec-Datei ist, können Sie sie NuGet-Pakete für Frameworks, die noch keine SDK-Stil-Projektdatei bieten erstellen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="7b7c0-117">**✔️ GGF.** verwenden eine SDK-Stil-Projektdatei das NuGet-Paket zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="7b7c0-118">**✔️ GGF.** SourceLink einrichten, Datenquellen-Steuerelement-Metadaten für Ihre Assemblys und NuGet-Paket hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="7b7c0-119">Paketabhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="7b7c0-119">Package dependencies</span></span>

<span data-ttu-id="7b7c0-120">NuGet-paketabhängigkeiten werden detailliert in die [Abhängigkeiten](./dependencies.md) Artikel.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="7b7c0-121">Wichtige NuGet-Paketmetadaten</span><span class="sxs-lookup"><span data-stu-id="7b7c0-121">Important NuGet package metadata</span></span>

<span data-ttu-id="7b7c0-122">Ein NuGet-Paket unterstützt viele [Metadateneigenschaften](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="7b7c0-123">Die folgende Tabelle enthält die coremetadaten, die alle Open Source-Projekt bereitgestellt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="7b7c0-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="7b7c0-124">MSBuild-Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="7b7c0-124">MSBuild Property name</span></span>              | <span data-ttu-id="7b7c0-125">NuSpec-name</span><span class="sxs-lookup"><span data-stu-id="7b7c0-125">Nuspec name</span></span>              | <span data-ttu-id="7b7c0-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7b7c0-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="7b7c0-127">Der paketbezeichner.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-127">The package identifier.</span></span> <span data-ttu-id="7b7c0-128">Ein Präfix aus einem Bezeichner reserviert werden kann, wenn er erfüllt die [Kriterien](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="7b7c0-129">NuGet-Paket-Version.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-129">NuGet package version.</span></span> <span data-ttu-id="7b7c0-130">Weitere Informationen finden Sie unter [NuGet-Paketversion](./versioning.md#nuget-package-version).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="7b7c0-131">Ein Benutzerfreundlicher Titel des Pakets.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-131">A human-friendly title of the package.</span></span> <span data-ttu-id="7b7c0-132">Wird standardmäßig die `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="7b7c0-133">Eine lange Beschreibung des Pakets in der Benutzeroberfläche angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="7b7c0-134">Eine durch Trennzeichen getrennte Liste der paketautoren, die mit Profilnamen unter nuget.org.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="7b7c0-135">Eine durch Leerzeichen getrennte Liste von Tags und Schlüsselwörtern, die das Paket beschreiben.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="7b7c0-136">Tags werden verwendet, bei der Suche nach Paketen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="7b7c0-137">Eine URL für ein Bild, das als Symbol für das Paket verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="7b7c0-138">Die URL muss HTTPS sein und das Image 64 x 64 und einen transparenten Hintergrund.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="7b7c0-139">Eine URL für das projektrepository Homepage oder Quelle.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="7b7c0-140">Eine URL mit der Projektlizenz.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-140">A URL to the project license.</span></span> <span data-ttu-id="7b7c0-141">Ist der URL, die `LICENSE` Datei in der quellcodeverwaltung.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="7b7c0-142">**✔️ GGF.** Auswählen eines NuGet-Paket mit einem Präfix, die NuGets-präfixreservierung erfüllt [Kriterien](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="7b7c0-143">**✔️ GGF.** mithilfe der `LICENSE` Datei in der quellcodeverwaltung als die `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="7b7c0-144">Z. B. [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b7c0-145">Ein Projekt, das nicht standardmäßig eine Lizenz [exklusive Copyright](https://choosealicense.com/no-permission/), kann für andere Personen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="7b7c0-146">**Führen Sie ✔️** verwenden eine HTTPS-Href auf Ihr Symbol "Paket".</span><span class="sxs-lookup"><span data-stu-id="7b7c0-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="7b7c0-147">Führen Sie Websites wie "NuGet.org" mit HTTPS-tauglich und Anzeigen eines nicht-HTTPS-Images wird eine Warnung zu gemischte Inhalte erstellt.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="7b7c0-148">**Führen Sie ✔️** verwenden Sie ein Image der Paket-Symbol, das ist 64 x 64 und verfügt über einen transparenten Hintergrund zur besseren Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="7b7c0-149">Vorabversionen von Paketen</span><span class="sxs-lookup"><span data-stu-id="7b7c0-149">Pre-release packages</span></span>

<span data-ttu-id="7b7c0-150">NuGet-Pakete mit einem Versionssuffix gelten [Vorabversion](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="7b7c0-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="7b7c0-151">Standardmäßig zeigt das NuGet-Paket-Manager-UI stabilen Releases, wenn ein Benutzer "OPTS"-in Vorabversionen von Paketen, ausführenden Vorabversionen von Paketen ideal für Benutzer mit beschränkten Rechten zu testen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="7b7c0-152">Stabiles Paket kann nicht für ein vorab veröffentlichtes Paket abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="7b7c0-153">Sie müssen stellen Ihr eigenes Paket Vorabversion oder hängen von einer älteren stabile Version.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="7b7c0-154">![NuGet-Vorabversionen-paketabhängigkeit](./media/nuget/nuget-prerelease-package.png "vorabversionspakets NuGet-Abhängigkeit")</span><span class="sxs-lookup"><span data-stu-id="7b7c0-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="7b7c0-155">**Führen Sie ✔️** veröffentlichen Sie ein vorab veröffentlichtes Paket testen, und beim Testversand, experimentieren.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="7b7c0-156">**Führen Sie ✔️** stabiles Paket veröffentlichen, wenn die kann jetzt also andere stabile Pakete darauf verweisen können.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="7b7c0-157">Symbolpakete</span><span class="sxs-lookup"><span data-stu-id="7b7c0-157">Symbol packages</span></span>

<span data-ttu-id="7b7c0-158">NuGet unterstützt [generieren ein separates Symbolpaket](/nuget/create-packages/symbol-packages) mit PDB-Dateien zusammen mit das Hauptpaket, die mit .NET Assemblys zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-158">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing debug PDB files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="7b7c0-159">Die Idee von Symbolpaketen ist sie auf einem Symbolserver gehostet werden und werden nur von einem Tool wie Visual Studio bei Bedarf heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-159">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="7b7c0-160">Derzeit öffentliche Haupthost für Symbole - [SymbolSource](http://www.symbolsource.org/) -bietet keine Unterstützung der portablen PDB-Dateien erstellt der Formatvorlage für SDK Projekte und Symbolpakete nicht nützlich sind.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-160">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the portable PDBs created by SDK-style projects and symbol packages aren't useful.</span></span>

<span data-ttu-id="7b7c0-161">**✔️ GGF.** Einbetten von PDB-Dateien in das Haupt-NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-161">**✔️ CONSIDER** embedding PDBs in the main NuGet package.</span></span>

<span data-ttu-id="7b7c0-162">**❌ Vermeiden** erstellen ein Symbolpaket, die PDB-Dateien enthält.</span><span class="sxs-lookup"><span data-stu-id="7b7c0-162">**❌ AVOID** creating a symbols package containing PDBs.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="7b7c0-163">[Zurück](./strong-naming.md)
[Weiter](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="7b7c0-163">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
