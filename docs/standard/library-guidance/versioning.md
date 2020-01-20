---
title: Versionsverwaltung und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden für die Versionsverwaltung für .NET-Bibliotheken.
ms.date: 12/10/2018
ms.openlocfilehash: 8ed3217e39b1fe0f330a650ec72cda224866e207
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706412"
---
# <a name="versioning"></a><span data-ttu-id="ca480-103">Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="ca480-103">Versioning</span></span>

<span data-ttu-id="ca480-104">Eine Softwarebibliothek ist in Version 1.0 nur selten vollständig.</span><span class="sxs-lookup"><span data-stu-id="ca480-104">A software library is rarely complete in version 1.0.</span></span> <span data-ttu-id="ca480-105">Gute Bibliotheken entwickeln sich im Laufe der Zeit weiter, indem Funktionen hinzugefügt, Fehler behoben und die Leistung verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="ca480-105">Good libraries evolve over time, adding features, fixing bugs and improving performance.</span></span> <span data-ttu-id="ca480-106">Es ist wichtig, dass Sie neue Versionen einer .NET-Bibliothek freigeben können, die mit jeder Version einen zusätzlichen Wert bieten, ohne bestehende Benutzer zu beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="ca480-106">It is important that you can release new versions of a .NET library, providing additional value with each version, without breaking existing users.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="ca480-107">Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="ca480-107">Breaking changes</span></span>

<span data-ttu-id="ca480-108">Weitere Informationen zur Verarbeitung von Breaking Changes zwischen den Versionen finden Sie unter [Breaking Changes](./breaking-changes.md).</span><span class="sxs-lookup"><span data-stu-id="ca480-108">For information about handling breaking changes between versions, see [Breaking changes](./breaking-changes.md).</span></span>

## <a name="version-numbers"></a><span data-ttu-id="ca480-109">Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="ca480-109">Version numbers</span></span>

<span data-ttu-id="ca480-110">Bei einer .NET-Bibliothek gibt es viele Möglichkeiten, eine Version angeben.</span><span class="sxs-lookup"><span data-stu-id="ca480-110">A .NET library has many ways to specify a version.</span></span> <span data-ttu-id="ca480-111">Diese Versionen sind die wichtigsten:</span><span class="sxs-lookup"><span data-stu-id="ca480-111">These versions are the most important:</span></span>

### <a name="nuget-package-version"></a><span data-ttu-id="ca480-112">NuGet-Paketversion</span><span class="sxs-lookup"><span data-stu-id="ca480-112">NuGet package version</span></span>

<span data-ttu-id="ca480-113">Die [NuGet-Paketversion](/nuget/reference/package-versioning) wird auf NuGet.org, dem Visual Studio NuGet-Paket-Manager, angezeigt und dem Quellcode hinzugefügt, wenn das Paket verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ca480-113">The [NuGet package version](/nuget/reference/package-versioning) is displayed on NuGet.org, the Visual Studio NuGet package manager, and is added to source code when the package is used.</span></span> <span data-ttu-id="ca480-114">Die NuGet-Paketversion ist die Versionsnummer, die Benutzern häufig angezeigt wird. Außerdem wird darauf verwiesen, wenn sie die von ihnen verwendete Bibliothek angeben.</span><span class="sxs-lookup"><span data-stu-id="ca480-114">The NuGet package version is the version number users will commonly see, and they'll refer to it when they talk about the version of a library they're using.</span></span> <span data-ttu-id="ca480-115">Die NuGet-Paket-Version wird von NuGet verwendet und hat keine Auswirkungen auf das Runtimeverhalten.</span><span class="sxs-lookup"><span data-stu-id="ca480-115">The NuGet package version is used by NuGet and has no effect on runtime behavior.</span></span>

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

<span data-ttu-id="ca480-116">Der NuGet-Paketbezeichner wird in Kombination mit der NuGet-Paket-Version verwendet, um ein Paket in NuGet zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ca480-116">The NuGet package identifier combined with the NuGet package version is used to identify a package in NuGet.</span></span> <span data-ttu-id="ca480-117">Beispiel: `Newtonsoft.Json` + `11.0.2`</span><span class="sxs-lookup"><span data-stu-id="ca480-117">For example, `Newtonsoft.Json` + `11.0.2`.</span></span> <span data-ttu-id="ca480-118">Ein Paket mit einem Suffix ist ein Vorabversionspaket, das ein bestimmtes Verhalten aufweist, wodurch es sich ideal für Tests eignet.</span><span class="sxs-lookup"><span data-stu-id="ca480-118">A package with a suffix is a pre-release package and has special behavior that makes it ideal for testing.</span></span> <span data-ttu-id="ca480-119">Weitere Informationen finden Sie unter [Vorabversionspakete](./nuget.md#pre-release-packages).</span><span class="sxs-lookup"><span data-stu-id="ca480-119">For more information, see [Pre-release packages](./nuget.md#pre-release-packages).</span></span>

<span data-ttu-id="ca480-120">Da die NuGet-Paketversion für Entwickler die sichtbarste Version ist, ist es eine gute Idee, sie mit der [semantischen Versionierung (SemVer)](https://semver.org/) zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ca480-120">Because the NuGet package version is the most visible version to developers, it's a good idea to update it using [Semantic Versioning (SemVer)](https://semver.org/).</span></span> <span data-ttu-id="ca480-121">SemVer zeigt die Bedeutung von Änderungen zwischen den Versionen an und hilft Entwicklern, eine fundierte Entscheidung bei der Auswahl der zu verwendenden Version zu treffen.</span><span class="sxs-lookup"><span data-stu-id="ca480-121">SemVer indicates the significance of changes between release and helps developers make an informed decision when choosing what version to use.</span></span> <span data-ttu-id="ca480-122">Wenn Sie beispielsweise von `1.0` auf `2.0` wechseln, zeigt dies an, dass es möglicherweise Änderungen gibt, die den Prozess unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="ca480-122">For example, going from `1.0` to `2.0` indicates that there are potentially breaking changes.</span></span>

<span data-ttu-id="ca480-123">**✔️ ERWÄGEN** Sie, [SemVer 2.0.0](https://semver.org/) für die Versionskontrolle Ihres NuGet-Pakets zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca480-123">**✔️ CONSIDER** using [SemVer 2.0.0](https://semver.org/) to version your NuGet package.</span></span>

<span data-ttu-id="ca480-124">**✔️ DO** Verwenden Sie die NuGet-Paketversion in der öffentlichen Dokumentation, da es die Versionsnummer ist, die den Benutzern häufig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ca480-124">**✔️ DO** use the NuGet package version in public documentation as it's the version number that users will commonly see.</span></span>

<span data-ttu-id="ca480-125">**✔️ DO** Fügen Sie ein Suffix der Vorabversion hinzu, wenn Sie ein nicht stabiles Paket freigeben.</span><span class="sxs-lookup"><span data-stu-id="ca480-125">**✔️ DO** include a pre-release suffix when releasing a non-stable package.</span></span>

> <span data-ttu-id="ca480-126">Benutzer müssen sich dafür entscheiden, Vorabversionspakete zu erhalten, sodass ihnen bewusst ist, dass das Paket nicht vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="ca480-126">Users must opt in to getting pre-release packages, so they will understand that the package is not complete.</span></span>

### <a name="assembly-version"></a><span data-ttu-id="ca480-127">Assemblyversion</span><span class="sxs-lookup"><span data-stu-id="ca480-127">Assembly version</span></span>

<span data-ttu-id="ca480-128">Die Assemblyversion wird von CLR zur Runtime verwendet, um die zu ladende Version einer Assembly auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ca480-128">The assembly version is what the CLR uses at runtime to select which version of an assembly to load.</span></span> <span data-ttu-id="ca480-129">Die Auswahl einer Assembly über die Versionsverwaltung gilt nur für Assemblys mit einem starken Namen.</span><span class="sxs-lookup"><span data-stu-id="ca480-129">Selecting an assembly using versioning only applies to assemblies with a strong name.</span></span>

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

<span data-ttu-id="ca480-130">Die Windows .NET Framework-CLR verlangt eine genaue Übereinstimmung, um eine Assembly mit einem starken Namen zu laden.</span><span class="sxs-lookup"><span data-stu-id="ca480-130">The Windows .NET Framework CLR demands an exact match to load a strong named assembly.</span></span> <span data-ttu-id="ca480-131">Beispielsweise wurde `Libary1, Version=1.0.0.0` mit einer Referenz auf `Newtonsoft.Json, Version=11.0.0.0` kompiliert.</span><span class="sxs-lookup"><span data-stu-id="ca480-131">For example, `Libary1, Version=1.0.0.0` was compiled with a reference to `Newtonsoft.Json, Version=11.0.0.0`.</span></span> <span data-ttu-id="ca480-132">Das .NET Framework lädt nur die genaue Version `11.0.0.0`.</span><span class="sxs-lookup"><span data-stu-id="ca480-132">The .NET Framework will only load that exact version `11.0.0.0`.</span></span> <span data-ttu-id="ca480-133">Um zur Runtime eine andere Version zu laden, muss der Konfigurationsdatei der .NET-Anwendung eine Bindungsumleitung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ca480-133">To load a different version at runtime, a binding redirect must be added to the .NET application's config file.</span></span>

<span data-ttu-id="ca480-134">Ein starker Name in Kombination mit der Assemblyversion ermöglicht das [strikte Laden der Assemblyversion](../assembly/versioning.md).</span><span class="sxs-lookup"><span data-stu-id="ca480-134">Strong naming combined with assembly version enables [strict assembly version loading](../assembly/versioning.md).</span></span> <span data-ttu-id="ca480-135">Obwohl ein starker Name einer Bibliothek eine Reihe von Vorteilen hat, führt sie oft zu Runtimeausnahmen, dass eine Assembly nicht gefunden werden kann und [Bindungsumleitungen](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` erforderlich sind, um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ca480-135">While strong naming a library has a number of benefits, it often results in runtime exceptions that an assembly can't be found and [requires binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` to be fixed.</span></span> <span data-ttu-id="ca480-136">Das Laden von .NET Core-Assemblys wurde vereinfacht, und die .NET Core-CLR lädt Assemblys zur Runtime automatisch mit einer höheren Version.</span><span class="sxs-lookup"><span data-stu-id="ca480-136">.NET Core assembly loading has been relaxed, and the .NET Core CLR will automatically load assemblies at runtime with a higher version.</span></span>

<span data-ttu-id="ca480-137">**✔️ ERWÄGEN** Sie, nur eine Hauptversion in der Assemblyversion zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="ca480-137">**✔️ CONSIDER** only including a major version in the AssemblyVersion.</span></span>

> <span data-ttu-id="ca480-138">Beispielsweise haben Bibliothek 1.0 und Bibliothek 1.0.1 beide eine Assemblyversion von `1.0.0.0`, während Bibliothek 2.0 eine Assemblyversion von `2.0.0.0` hat.</span><span class="sxs-lookup"><span data-stu-id="ca480-138">e.g. Library 1.0 and Library 1.0.1 both have an AssemblyVersion of `1.0.0.0`, while Library 2.0 has AssemblyVersion of `2.0.0.0`.</span></span> <span data-ttu-id="ca480-139">Wenn die Assemblyversion seltener geändert wird, sind weniger Bindungsumleitungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca480-139">When the assembly version changes less often, it reduces binding redirects.</span></span>

<span data-ttu-id="ca480-140">**✔ ERWÄGEN** Sie, die Hauptversionsnummer der Assemblyversion und die NuGet-Paketversion immer zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="ca480-140">**✔️ CONSIDER** keeping the major version number of the AssemblyVersion and the NuGet package version in sync.</span></span>

> <span data-ttu-id="ca480-141">Die Assemblyversion ist in einigen Informationsmeldungen enthalten, die dem Benutzer angezeigt werden, z.B. der Assemblyname und Typnamen mit Assemblyqualifikation in Ausnahmemeldungen.</span><span class="sxs-lookup"><span data-stu-id="ca480-141">The AssemblyVersion is included in some informational messages displayed to the user, e.g. the assembly name and assembly qualified type names in exception messages.</span></span> <span data-ttu-id="ca480-142">Durch die Beibehaltung einer Beziehung zwischen den Versionen erhalten Entwickler weitere Informationen darüber, welche Version sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca480-142">Maintaining a relationship between the versions provides more information to developers about which version they are using.</span></span>

<span data-ttu-id="ca480-143">**❌ VERWENDEN SIE KEINE** feste Assemblyversion.</span><span class="sxs-lookup"><span data-stu-id="ca480-143">**❌ DO NOT** have a fixed AssemblyVersion.</span></span>

> <span data-ttu-id="ca480-144">Da eine unveränderliche Assemblyversion die Notwendigkeit von Bindungsumleitungen vermeidet, bedeutet dies, dass nur eine einzige Version der Assembly im globalen Assemblycache (GAC) installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca480-144">While an unchanging AssemblyVersion avoids the need for binding redirects, it means that only a single version of the assembly can be installed in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="ca480-145">Außerdem werden die Anwendungen, die auf die Assembly im GAC verweisen, unterbrochen, wenn eine andere Anwendung die GAC-Assembly mit Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="ca480-145">Also, the applications that reference the assembly in the GAC will break if another application updates the GAC assembly with breaking changes.</span></span>

### <a name="assembly-file-version"></a><span data-ttu-id="ca480-146">Assemblydateiversion</span><span class="sxs-lookup"><span data-stu-id="ca480-146">Assembly file version</span></span>

<span data-ttu-id="ca480-147">Die Assemblydateiversion wird verwendet, um eine Dateiversion unter Windows anzuzeigen und hat keinen Einfluss auf das Runtimeverhalten.</span><span class="sxs-lookup"><span data-stu-id="ca480-147">The assembly file version is used to display a file version in Windows and has no effect on runtime behavior.</span></span> <span data-ttu-id="ca480-148">Das Festlegen dieser Version ist optional.</span><span class="sxs-lookup"><span data-stu-id="ca480-148">Setting this version is optional.</span></span> <span data-ttu-id="ca480-149">Sie wird im Dialogfeld „Dateieigenschaften“ im Windows Explorer angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca480-149">It's visible in the File Properties dialog in Windows Explorer:</span></span>

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

<span data-ttu-id="ca480-150">![Windows-Explorer](./media/versioning/win-properties.png "Windows-Explorer")</span><span class="sxs-lookup"><span data-stu-id="ca480-150">![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")</span></span>

<span data-ttu-id="ca480-151">**✔️ ERWÄGEN** Sie, eine fortlaufenden Continuous Integration-Buildnummer als AssemblyFileVersion-Revision hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca480-151">**✔️ CONSIDER** including a continuous integration build number as the AssemblyFileVersion revision.</span></span>

> <span data-ttu-id="ca480-152">Wenn Sie beispielsweise Version 1.0.0 Ihres Projekts erstellen, und die Nummer des Continuous Integration-Builds ist 99, lautet Ihre Assemblydateiversion 1.0.0.99.</span><span class="sxs-lookup"><span data-stu-id="ca480-152">For example, you are building version 1.0.0 of your project, and the continuous integration build number is 99 so your AssemblyFileVersion is 1.0.0.99.</span></span>

<span data-ttu-id="ca480-153">**✔️ VERWENDEN** Sie das Format `Major.Minor.Build.Revision` für die Dateiversion.</span><span class="sxs-lookup"><span data-stu-id="ca480-153">**✔️ DO** use the format `Major.Minor.Build.Revision` for file version.</span></span>

> <span data-ttu-id="ca480-154">Obwohl die Dateiversion von .NET nie verwendet wird, [setzt Windows die Dateiversion](/windows/desktop/menurc/versioninfo-resource) im `Major.Minor.Build.Revision`-Format voraus.</span><span class="sxs-lookup"><span data-stu-id="ca480-154">While the file version is never used by .NET, [Windows expects the file version](/windows/desktop/menurc/versioninfo-resource) to be in the `Major.Minor.Build.Revision` format.</span></span> <span data-ttu-id="ca480-155">Es wird eine Warnung ausgelöst, wenn die Version nicht dieses Format aufweist.</span><span class="sxs-lookup"><span data-stu-id="ca480-155">A warning is raised if the version doesn't follow this format.</span></span>

### <a name="assembly-informational-version"></a><span data-ttu-id="ca480-156">Assemblyinformationsversion</span><span class="sxs-lookup"><span data-stu-id="ca480-156">Assembly informational version</span></span>

<span data-ttu-id="ca480-157">Die Assemblyinformationsversion wird verwendet, um zusätzliche Versionsinformationen zu erfassen und hat keinen Einfluss auf das Runtimeverhalten.</span><span class="sxs-lookup"><span data-stu-id="ca480-157">The assembly informational version is used to record additional version information and has no effect on runtime behavior.</span></span> <span data-ttu-id="ca480-158">Das Festlegen dieser Version ist optional.</span><span class="sxs-lookup"><span data-stu-id="ca480-158">Setting this version is optional.</span></span> <span data-ttu-id="ca480-159">Wenn Sie SourceLink verwenden, wird diese Version für das Build mit der NuGet-Paketversion plus einer Version der Versionsverwaltung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ca480-159">If you're using Source Link, this version will be set on build with the NuGet package version plus a source control version.</span></span> <span data-ttu-id="ca480-160">Zum Beispiel beinhaltet `1.0.0-beta1+204ff0a` den Commithash des Quellcodes, aus dem die Assembly erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ca480-160">For example, `1.0.0-beta1+204ff0a` includes the commit hash of the source code the assembly was built from.</span></span> <span data-ttu-id="ca480-161">Weitere Informationen finden Sie unter [SourceLink](./sourcelink.md).</span><span class="sxs-lookup"><span data-stu-id="ca480-161">For more information, see [Source Link](./sourcelink.md).</span></span>

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

> [!NOTE]
> <span data-ttu-id="ca480-162">Bei älteren Versionen von Visual Studio wird eine Buildwarnung ausgelöst, wenn diese Version nicht das Format `Major.Minor.Build.Revision` aufweist.</span><span class="sxs-lookup"><span data-stu-id="ca480-162">Older versions of Visual Studio raise a build warning if this version doesn't follow the format `Major.Minor.Build.Revision`.</span></span> <span data-ttu-id="ca480-163">Sie können sie ignorieren.</span><span class="sxs-lookup"><span data-stu-id="ca480-163">The warning can be safely ignored.</span></span>

<span data-ttu-id="ca480-164">**❌ VERMEIDEN** Sie, die Assemblyinformationsversion selbst festzulegen.</span><span class="sxs-lookup"><span data-stu-id="ca480-164">**❌ AVOID** setting the assembly informational version yourself.</span></span>

> <span data-ttu-id="ca480-165">Erlauben Sie SourceLink, die Version automatisch zu generieren, die NuGet- und Metadaten der Quellcodeverwaltung enthält.</span><span class="sxs-lookup"><span data-stu-id="ca480-165">Allow SourceLink to automatically generate the version containing NuGet and source control metadata.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ca480-166">[Zurück](publish-nuget-package.md)
>[Weiter](breaking-changes.md)</span><span class="sxs-lookup"><span data-stu-id="ca480-166">[Previous](publish-nuget-package.md)
[Next](breaking-changes.md)</span></span>
