---
title: Versionsverwaltung für die .NET-Runtime und das .NET SDK
description: In diesem Artikel erfahren Sie, wie das .NET SDK und die Runtime versioniert werden (ähnlich der semantischen Versionierung).
ms.date: 12/07/2020
ms.openlocfilehash: 2fbc2775f31b4eab1c9883282c58accd9bb2b9f5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633623"
---
# <a name="overview-of-how-net-is-versioned"></a><span data-ttu-id="4db0d-103">Übersicht über die .NET-Versionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="4db0d-103">Overview of how .NET is versioned</span></span>

<span data-ttu-id="4db0d-104">Mit der [.NET-Runtime und dem .NET SDK](../introduction.md#sdk-and-runtimes) werden neue Features zu unterschiedlichen Frequenzen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-104">The [.NET Runtime and the .NET SDK](../introduction.md#sdk-and-runtimes) add new features at different frequencies.</span></span> <span data-ttu-id="4db0d-105">In der Regel wird das SDK häufiger aktualisiert als die Runtime.</span><span class="sxs-lookup"><span data-stu-id="4db0d-105">In general, the SDK is updated more frequently than the Runtime.</span></span> <span data-ttu-id="4db0d-106">Dieser Artikel beschreibt die Runtime und die SDK-Versionsnummern.</span><span class="sxs-lookup"><span data-stu-id="4db0d-106">This article explains the runtime and the SDK version numbers.</span></span>

## <a name="versioning-details"></a><span data-ttu-id="4db0d-107">Versionsinformationen</span><span class="sxs-lookup"><span data-stu-id="4db0d-107">Versioning details</span></span>

<span data-ttu-id="4db0d-108">Die .NET-Runtime verfolgt einen Hauptversions-/Nebenversions-/Patchansatz für die Versionsverwaltung, der [semantische Versionierung](#semantic-versioning) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4db0d-108">The .NET Runtime has a major/minor/patch approach to versioning that follows [semantic versioning](#semantic-versioning).</span></span>

<span data-ttu-id="4db0d-109">Das .NET SDK folgt keiner semantischen Versionierung.</span><span class="sxs-lookup"><span data-stu-id="4db0d-109">The .NET SDK doesn't follow semantic versioning.</span></span> <span data-ttu-id="4db0d-110">Das .NET SDK wird schneller veröffentlicht, und seine Versionsnummern müssen sowohl die angepasste Runtime als auch die eigenen Nebenversions- und Patchreleases des SDK kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="4db0d-110">The .NET SDK releases faster and its version numbers must communicate both the aligned runtime and the SDK's own minor and patch releases.</span></span>

<span data-ttu-id="4db0d-111">Die ersten beiden Stellen der Versionsnummer des .NET SDK sind für die Version der .NET-Runtime reserviert, mit der es veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="4db0d-111">The first two positions of the .NET SDK version number are locked to the .NET Runtime version it released with.</span></span> <span data-ttu-id="4db0d-112">Jede Version des SDK kann Anwendungen für diese Runtime bzw. niedrigere Versionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="4db0d-112">Each version of the SDK can create applications for this runtime or any lower version.</span></span>

<span data-ttu-id="4db0d-113">Die dritte Stelle der SDK-Versionsnummer gibt sowohl die Nebenversions- als auch die Patchnummer an.</span><span class="sxs-lookup"><span data-stu-id="4db0d-113">The third position of the SDK version number communicates both the minor and patch number.</span></span> <span data-ttu-id="4db0d-114">Die Nebenversion wird mit 100 multipliziert.</span><span class="sxs-lookup"><span data-stu-id="4db0d-114">The minor version is multiplied by 100.</span></span> <span data-ttu-id="4db0d-115">Die letzten zwei Ziffern stehen für die Patchnummer.</span><span class="sxs-lookup"><span data-stu-id="4db0d-115">The final two digits represent the patch number.</span></span> <span data-ttu-id="4db0d-116">Nebenversion 1, Patchversion 2 würde als 102 dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-116">Minor version 1, patch version 2 would be represented as 102.</span></span> <span data-ttu-id="4db0d-117">Im Folgenden ist eine mögliche Sequenz der Runtime- und SDK-Versionsnummern aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="4db0d-117">For example, here's a possible sequence of runtime and SDK version numbers:</span></span>

| <span data-ttu-id="4db0d-118">Change</span><span class="sxs-lookup"><span data-stu-id="4db0d-118">Change</span></span>                | <span data-ttu-id="4db0d-119">.Net-Runtime</span><span class="sxs-lookup"><span data-stu-id="4db0d-119">.NET Runtime</span></span>      | <span data-ttu-id="4db0d-120">.NET SDK (\*)</span><span class="sxs-lookup"><span data-stu-id="4db0d-120">.NET SDK (\*)</span></span>     |
|-----------------------|-------------------|-------------------|
| <span data-ttu-id="4db0d-121">Erstrelease</span><span class="sxs-lookup"><span data-stu-id="4db0d-121">Initial release</span></span>       | <span data-ttu-id="4db0d-122">2.2.0</span><span class="sxs-lookup"><span data-stu-id="4db0d-122">2.2.0</span></span>             | <span data-ttu-id="4db0d-123">2.2.100</span><span class="sxs-lookup"><span data-stu-id="4db0d-123">2.2.100</span></span>           |
| <span data-ttu-id="4db0d-124">SDK-Patch</span><span class="sxs-lookup"><span data-stu-id="4db0d-124">SDK patch</span></span>             | <span data-ttu-id="4db0d-125">2.2.0</span><span class="sxs-lookup"><span data-stu-id="4db0d-125">2.2.0</span></span>             | <span data-ttu-id="4db0d-126">2.2.101</span><span class="sxs-lookup"><span data-stu-id="4db0d-126">2.2.101</span></span>           |
| <span data-ttu-id="4db0d-127">Runtime und SDK-Patch</span><span class="sxs-lookup"><span data-stu-id="4db0d-127">Runtime and SDK patch</span></span> | <span data-ttu-id="4db0d-128">2.2.1</span><span class="sxs-lookup"><span data-stu-id="4db0d-128">2.2.1</span></span>             | <span data-ttu-id="4db0d-129">2.2.102</span><span class="sxs-lookup"><span data-stu-id="4db0d-129">2.2.102</span></span>           |
| <span data-ttu-id="4db0d-130">SDK-Featureänderung</span><span class="sxs-lookup"><span data-stu-id="4db0d-130">SDK feature change</span></span>    | <span data-ttu-id="4db0d-131">2.2.1</span><span class="sxs-lookup"><span data-stu-id="4db0d-131">2.2.1</span></span>             | <span data-ttu-id="4db0d-132">2.2.200</span><span class="sxs-lookup"><span data-stu-id="4db0d-132">2.2.200</span></span>           |

<span data-ttu-id="4db0d-133">HINWEISE:</span><span class="sxs-lookup"><span data-stu-id="4db0d-133">NOTES:</span></span>

- <span data-ttu-id="4db0d-134">Wenn das SDK vor einem Runtimefeatureupdate 10 Featureupdates aufweist, werden die Versionsnummern in die 1000er-Serie mit Nummern wie 2.2.1000 als Featurerelease nach 2.2.900 übernommen.</span><span class="sxs-lookup"><span data-stu-id="4db0d-134">If the SDK has 10 feature updates before a runtime feature update, version numbers roll into the 1000 series with numbers like 2.2.1000 as the feature release following 2.2.900.</span></span> <span data-ttu-id="4db0d-135">Diese Situation wird nicht erwartet.</span><span class="sxs-lookup"><span data-stu-id="4db0d-135">This situation isn't expected to occur.</span></span>
- <span data-ttu-id="4db0d-136">99 Patchreleases ohne Featurerelease treten nicht auf.</span><span class="sxs-lookup"><span data-stu-id="4db0d-136">99 patch releases without a feature release won't occur.</span></span> <span data-ttu-id="4db0d-137">Nähert sich ein Release dieser Version, wird ein Featurerelease erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4db0d-137">If a release approaches this number, it forces a feature release.</span></span>

<span data-ttu-id="4db0d-138">Weitere Details finden Sie im ursprünglichen Vorschlag im Repository [dotnet/designs](https://github.com/dotnet/designs/pull/29).</span><span class="sxs-lookup"><span data-stu-id="4db0d-138">You can see more details in the initial proposal at the [dotnet/designs](https://github.com/dotnet/designs/pull/29) repository.</span></span>

## <a name="semantic-versioning"></a><span data-ttu-id="4db0d-139">Semantische Versionierung</span><span class="sxs-lookup"><span data-stu-id="4db0d-139">Semantic versioning</span></span>

<span data-ttu-id="4db0d-140">Die .NET-*Runtime* verwendet im Großen und Ganzen die [semantische Versionierung (SemVer)](https://semver.org/) und übernimmt die Verwendung der `MAJOR.MINOR.PATCH`-Versionierung mithilfe der verschiedenen Teile der Versionsnummer, um den Grad und den Typ der Änderung zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4db0d-140">The .NET *Runtime* roughly adheres to [Semantic Versioning (SemVer)](https://semver.org/), adopting the use of `MAJOR.MINOR.PATCH` versioning, using the various parts of the version number to describe the degree and type of change.</span></span>

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

<span data-ttu-id="4db0d-141">Die optionalen Teile `PRERELEASE` und `BUILDNUMBER` sind nie Bestandteil von unterstützten Versionen und sind nur in nächtlichen Builds vorhanden, die lokal aus Quellzielen und nicht unterstützten Vorschauversionen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4db0d-141">The optional `PRERELEASE` and `BUILDNUMBER` parts are never part of supported releases and only exist on nightly builds, local builds from source targets, and unsupported preview releases.</span></span>

### <a name="understand-runtime-version-number-changes"></a><span data-ttu-id="4db0d-142">Verstehen von Änderungen der Runtimeversionsnummer</span><span class="sxs-lookup"><span data-stu-id="4db0d-142">Understand runtime version number changes</span></span>

<span data-ttu-id="4db0d-143">`MAJOR` wird inkrementiert, wenn:</span><span class="sxs-lookup"><span data-stu-id="4db0d-143">`MAJOR` is incremented when:</span></span>

- <span data-ttu-id="4db0d-144">Signifikante Änderungen im Produkt oder eine neue Produktausrichtung auftreten.</span><span class="sxs-lookup"><span data-stu-id="4db0d-144">Significant changes occur to the product, or a new product direction.</span></span>
- <span data-ttu-id="4db0d-145">Aktuelle Änderungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="4db0d-145">Breaking changes were taken.</span></span> <span data-ttu-id="4db0d-146">Die Messlatte zum Akzeptieren von aktuellen Änderungen hoch liegt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-146">There's a high bar to accepting breaking changes.</span></span>
- <span data-ttu-id="4db0d-147">eine älter Version nicht mehr unterstützt wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-147">An old version is no longer supported.</span></span>
- <span data-ttu-id="4db0d-148">eine neue `MAJOR`-Version einer vorhandenen Abhängigkeit übernommen wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-148">A newer `MAJOR` version of an existing dependency is adopted.</span></span>

<span data-ttu-id="4db0d-149">`MINOR` wird inkrementiert, wenn:</span><span class="sxs-lookup"><span data-stu-id="4db0d-149">`MINOR` is incremented when:</span></span>

- <span data-ttu-id="4db0d-150">eine öffentliche API-Oberfläche hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-150">Public API surface area is added.</span></span>
- <span data-ttu-id="4db0d-151">ein neues Verhalten hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-151">A new behavior is added.</span></span>
- <span data-ttu-id="4db0d-152">eine neue `MINOR`-Version einer vorhandenen Abhängigkeit übernommen wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-152">A newer `MINOR` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="4db0d-153">eine neue Abhängigkeit eingeführt wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-153">A new dependency is introduced.</span></span>

<span data-ttu-id="4db0d-154">`PATCH` wird inkrementiert, wenn:</span><span class="sxs-lookup"><span data-stu-id="4db0d-154">`PATCH` is incremented when:</span></span>

- <span data-ttu-id="4db0d-155">Fehlerkorrekturen vorgenommen werden</span><span class="sxs-lookup"><span data-stu-id="4db0d-155">Bug fixes are made.</span></span>
- <span data-ttu-id="4db0d-156">Unterstützung für eine neuere Plattform hinzugefügt wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-156">Support for a newer platform is added.</span></span>
- <span data-ttu-id="4db0d-157">eine neue `PATCH`-Version einer vorhandenen Abhängigkeit übernommen wird</span><span class="sxs-lookup"><span data-stu-id="4db0d-157">A newer `PATCH` version of an existing dependency is adopted.</span></span>
- <span data-ttu-id="4db0d-158">eine andere Änderung vorgenommen wurde, die keinem der zuvor beschriebenen Fälle entspricht</span><span class="sxs-lookup"><span data-stu-id="4db0d-158">Any other change doesn't fit one of the previous cases.</span></span>

<span data-ttu-id="4db0d-159">Wenn mehrere Änderungen vorgenommen wurden, wird das höchste Element, was von den einzelnen Änderungen betroffen ist, inkrementierte, und die folgenden werden auf 0 (null) zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-159">When there are multiple changes, the highest element affected by individual changes is incremented, and the following ones are reset to zero.</span></span> <span data-ttu-id="4db0d-160">Wenn z.B. `MAJOR` inkrementiert wird, werden `MINOR` und `PATCH` auf 0 (null) zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-160">For example, when `MAJOR` is incremented, `MINOR` and `PATCH` are reset to zero.</span></span> <span data-ttu-id="4db0d-161">Wenn `MINOR` inkrementiert wird, wird `PATCH` auf 0 (null) zurückgesetzt, während `MAJOR` nicht beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="4db0d-161">When `MINOR` is incremented, `PATCH` is reset to zero while `MAJOR` is left untouched.</span></span>

## <a name="version-numbers-in-file-names"></a><span data-ttu-id="4db0d-162">Versionsnummern in Dateinamen</span><span class="sxs-lookup"><span data-stu-id="4db0d-162">Version numbers in file names</span></span>

<span data-ttu-id="4db0d-163">Die für .NET heruntergeladenen Dateien tragen die Versionsnummer, zum Beispiel `dotnet-sdk-2.1.300-win10-x64.exe`.</span><span class="sxs-lookup"><span data-stu-id="4db0d-163">The files downloaded for .NET carry the version, for example, `dotnet-sdk-2.1.300-win10-x64.exe`.</span></span>

### <a name="preview-versions"></a><span data-ttu-id="4db0d-164">Vorschauversionen</span><span class="sxs-lookup"><span data-stu-id="4db0d-164">Preview versions</span></span>

<span data-ttu-id="4db0d-165">Der Versionsnummer von Vorschauversionen ist ein `-preview[number]-([build]|"final")` angehängt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-165">Preview versions have a `-preview[number]-([build]|"final")` appended to the version number.</span></span> <span data-ttu-id="4db0d-166">Beispielsweise `2.0.0-preview1-final`.</span><span class="sxs-lookup"><span data-stu-id="4db0d-166">For example, `2.0.0-preview1-final`.</span></span>

### <a name="servicing-versions"></a><span data-ttu-id="4db0d-167">Wartung von Versionen</span><span class="sxs-lookup"><span data-stu-id="4db0d-167">Servicing versions</span></span>

<span data-ttu-id="4db0d-168">Nach Erscheinen eines Release produzieren die Releaseabteilungen im Allgemeinen keine täglichen Builds mehr und beginnen stattdessen mit der Produktion von Wartungsbuilds.</span><span class="sxs-lookup"><span data-stu-id="4db0d-168">After a release goes out, the release branches generally stop producing daily builds and instead start producing servicing builds.</span></span> <span data-ttu-id="4db0d-169">Der Versionsangabe von Wartungsversionen ist ein `-servicing-[number]` angehängt.</span><span class="sxs-lookup"><span data-stu-id="4db0d-169">Servicing versions have a `-servicing-[number]` appended to the version.</span></span> <span data-ttu-id="4db0d-170">Beispielsweise `2.0.1-servicing-006924`.</span><span class="sxs-lookup"><span data-stu-id="4db0d-170">For example, `2.0.1-servicing-006924`.</span></span>

## <a name="relationship-to-net-standard-versions"></a><span data-ttu-id="4db0d-171">Beziehung zu .NET Standard-Versionen</span><span class="sxs-lookup"><span data-stu-id="4db0d-171">Relationship to .NET Standard versions</span></span>

<span data-ttu-id="4db0d-172">.NET Standard besteht aus einer .NET-Referenzassembly.</span><span class="sxs-lookup"><span data-stu-id="4db0d-172">.NET Standard consists of a .NET reference assembly.</span></span> <span data-ttu-id="4db0d-173">Es gibt mehrere plattformspezifische Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="4db0d-173">There are multiple implementations specific to each platform.</span></span> <span data-ttu-id="4db0d-174">Die Referenzassembly enthält die Definition von .NET-APIs, die Teil einer angegebenen .NET Standard-Version sind.</span><span class="sxs-lookup"><span data-stu-id="4db0d-174">The reference assembly contains the definition of .NET APIs which are part of a given .NET Standard version.</span></span> <span data-ttu-id="4db0d-175">Jede Implementierung erfüllt den .NET Standard-Vertrag für die jeweilige Plattform.</span><span class="sxs-lookup"><span data-stu-id="4db0d-175">Each implementation fulfills the .NET Standard contract on the specific platform.</span></span>

<span data-ttu-id="4db0d-176">Die .NET Standard-Referenzassembly verwendet ein `MAJOR.MINOR`-Schema für die Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="4db0d-176">The .NET Standard reference assembly uses a `MAJOR.MINOR` versioning scheme.</span></span> <span data-ttu-id="4db0d-177">Die `PATCH`-Ebene ist für .NET Standard nicht sinnvoll, da sie nur eine API-Spezifikation bereitstellt (keine Implementierung) und per Definition jede Änderung an der API eine Änderung im Funktionsumfang und damit eine neue `MINOR`-Version darstellen würde.</span><span class="sxs-lookup"><span data-stu-id="4db0d-177">`PATCH` level isn't useful for .NET Standard because it exposes only an API specification (no implementation) and by definition any change to the API would represent a change in the feature set, and thus a new `MINOR` version.</span></span>

<span data-ttu-id="4db0d-178">Die Implementierungen auf jeder Plattform können aktualisiert werden (in der Regel als Teil des Plattformreleases) und sind daher für die Programmierer, die den .NET Standard auf dieser Plattform verwenden, nicht ersichtlich.</span><span class="sxs-lookup"><span data-stu-id="4db0d-178">The implementations on each platform may be updated, typically as part of the platform release, and thus not evident to the programmers using .NET Standard on that platform.</span></span>

<span data-ttu-id="4db0d-179">Weitere Informationen finden Sie unter [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="4db0d-179">For more information, see [.NET Standard](../../standard/net-standard.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4db0d-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4db0d-180">See also</span></span>

- [<span data-ttu-id="4db0d-181">Zielframeworks</span><span class="sxs-lookup"><span data-stu-id="4db0d-181">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="4db0d-182">Packen einer Verteilung von .NET</span><span class="sxs-lookup"><span data-stu-id="4db0d-182">.NET distribution packaging</span></span>](../distribution-packaging.md)
- [<span data-ttu-id="4db0d-183">Fakten zur Lebensdauer der .NET-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="4db0d-183">.NET Support Lifecycle Fact Sheet</span></span>](https://dotnet.microsoft.com/platform/support/policy)
- [<span data-ttu-id="4db0d-184">Docker-Images für .NET</span><span class="sxs-lookup"><span data-stu-id="4db0d-184">Docker images for .NET</span></span>](https://hub.docker.com/_/microsoft-dotnet/)
