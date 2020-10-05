---
title: Analysetool für die Plattformkompatibilität
description: Ein Roslyn-Analysetool, das helfen kann, in plattformübergreifenden Apps und Bibliotheken Probleme mit der Plattformkompatibilität zu erkennen
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 4e842e5bbe90dd5006d9b27d0365f908b6441997
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406586"
---
# <a name="platform-compatibility-analyzer"></a><span data-ttu-id="cafad-103">Analysetool für die Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="cafad-103">Platform compatibility analyzer</span></span>

<span data-ttu-id="cafad-104">Sie haben wahrscheinlich bereits von .NET als einer einzigen, einheitlichen Plattform für die Entwicklung beliebiger Anwendungstypen gehört.</span><span class="sxs-lookup"><span data-stu-id="cafad-104">You've probably heard the motto of "One .NET": a single, unified platform for building any type of application.</span></span> <span data-ttu-id="cafad-105">Das .NET 5.0 SDK enthält ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin und ML.NET, und Unterstützung für weitere Plattformen wird im Laufe der Zeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cafad-105">The .NET 5.0 SDK includes ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin, and ML.NET, and will add support for more platforms over time.</span></span> <span data-ttu-id="cafad-106">Es ist das Ziel von .NET 5.0, dass Sie sich keine Gedanken um die verschiedenen .NET-Varianten machen müssen, ohne dass das zugrunde liegende Betriebssystem zu diesem Zweck vollständig abstrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="cafad-106">.NET 5.0 strives to provide an experience where you don't have to reason about the different flavors of .NET, but doesn't attempt to fully abstract away the underlying operating system (OS).</span></span> <span data-ttu-id="cafad-107">Sie sind weiterhin in der Lage, plattformspezifische APIs (z. B. P/Invokes, WinRT oder die Xamarin-Bindungen für iOS und Android) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="cafad-107">You'll continue to be able to call platform-specific APIs, for example, P/Invokes, WinRT, or the Xamarin bindings for iOS and Android.</span></span>

<span data-ttu-id="cafad-108">Durch die Verwendung plattformspezifischer APIs für eine Komponente funktioniert der Code jedoch nicht mehr auf allen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="cafad-108">But using platform-specific APIs on a component means the code no longer works across all platforms.</span></span> <span data-ttu-id="cafad-109">Es fehlte eine Methode, die dies zur Entwurfszeit erkennt, damit Entwickler eine Diagnose erhalten, wenn sie versehentlich plattformspezifische APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="cafad-109">We needed a way to detect this at design time so developers get diagnostics when they inadvertently use platform-specific APIs.</span></span> <span data-ttu-id="cafad-110">Aus diesem Grund führt .NET 5.0 das [Analysetool für die Plattformkompatibilität](/visualstudio/code-quality/ca1416) sowie ergänzende APIs ein, damit Entwickler ggf. plattformspezifische APIs erkennen und verwenden können, wenn es sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="cafad-110">To achieve this goal, .NET 5.0 introduces the [platform compatibility analyzer](/visualstudio/code-quality/ca1416) and complementary APIs to help developers identify and use platform-specific APIs where appropriate.</span></span>
<span data-ttu-id="cafad-111">Zu den neuen APIs zählen:</span><span class="sxs-lookup"><span data-stu-id="cafad-111">The new APIs include:</span></span>

- <span data-ttu-id="cafad-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> zum Kommentieren von APIs als plattformspezifisch und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, um APIs als für ein bestimmtes Betriebssystem nicht unterstützt zu annotieren.</span><span class="sxs-lookup"><span data-stu-id="cafad-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> to annotate APIs as being platform-specific and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> to annotate APIs as being unsupported on a particular OS.</span></span> <span data-ttu-id="cafad-113">Diese Attribute können optional die Versionsnummer enthalten und wurden bereits auf einige plattformspezifische APIs in den .NET-Kernbibliotheken angewendet.</span><span class="sxs-lookup"><span data-stu-id="cafad-113">These attributes can optionally include the version number, and have already been applied to some platform-specific APIs in the core .NET libraries.</span></span>
- <span data-ttu-id="cafad-114">Die statischen Methoden `Is<Platform>()` und `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` in der Klasse <xref:System.OperatingSystem?displayProperty=nameWithType> zum sicheren Aufrufen von plattformspezifischen APIs.</span><span class="sxs-lookup"><span data-stu-id="cafad-114">`Is<Platform>()` and `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` static methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class for safely calling platform-specific APIs.</span></span> <span data-ttu-id="cafad-115">Mit <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> kann beispielsweise ein Aufruf einer Windows-spezifischen API und mit <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() ein versionierter Windows-spezifischer API-Aufruf geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-115">For example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> can be used to guard a call to a Windows-specific API, and <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() can be used to guard a versioned Windows-specific API call.</span></span> <span data-ttu-id="cafad-116">In diesen [Beispielen](#guard-platform-specific-apis-with-guard-methods) wird veranschaulicht, wie mithilfe dieser Methoden plattformspezifische API-Verweise geschützt werden können.</span><span class="sxs-lookup"><span data-stu-id="cafad-116">See these [examples](#guard-platform-specific-apis-with-guard-methods) of how these methods can be used as guards of platform-specific API references.</span></span>

> [!TIP]
> <span data-ttu-id="cafad-117">Das Analysetool für die Plattformkompatibilität aktualisiert und ersetzt das Feature für die [Ermittlung plattformübergreifender Probleme](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) des [.NET-API-Analysetools](../../standard/analyzers/api-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="cafad-117">The platform compatibility analyzer upgrades and replaces the [Discovering cross-platform issues](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) feature of the [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cafad-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="cafad-118">Prerequisites</span></span>

<span data-ttu-id="cafad-119">Bei dem Analysetool für die Plattformkompatibilität handelt es sich um eines der Codequalitätsanalysetools von Roslyn.</span><span class="sxs-lookup"><span data-stu-id="cafad-119">The platform compatibility analyzer is one of the Roslyn code quality analyzers.</span></span> <span data-ttu-id="cafad-120">Ab .NET 5.0 sind diese Analysetools im [.NET SDK](../../fundamentals/productivity/code-analysis.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="cafad-120">Starting in .NET 5.0, these analyzers are [included with the .NET SDK](../../fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="cafad-121">Das Analysetool für die Plattformkompatibilität ist standardmäßig nur für Projekte aktiviert, die für `net5.0` oder höher entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-121">The platform compatibility analyzer is enabled by default only for projects that target `net5.0` or a later version.</span></span> <span data-ttu-id="cafad-122">Sie können es jedoch auch für Projekte [aktivieren](/visualstudio/code-quality/ca1416.md#configurability), die auf andere Frameworks abzielen.</span><span class="sxs-lookup"><span data-stu-id="cafad-122">However, you can [enable](/visualstudio/code-quality/ca1416.md#configurability) it for projects that target other frameworks.</span></span>

## <a name="how-the-analyzer-determines-platform-dependency"></a><span data-ttu-id="cafad-123">Bestimmen der Plattformabhängigkeit mithilfe des Analysetools</span><span class="sxs-lookup"><span data-stu-id="cafad-123">How the analyzer determines platform dependency</span></span>

- <span data-ttu-id="cafad-124">Bei einer **nicht attributierten API** wird davon ausgegangen, dass sie auf **allen Betriebssystemplattformen** funktioniert.</span><span class="sxs-lookup"><span data-stu-id="cafad-124">An **unattributed API** is considered to work on **all OS platforms**.</span></span>
- <span data-ttu-id="cafad-125">Eine API, die mit `[SupportedOSPlatform("platform")]` gekennzeichnet ist, gilt als nur für das angegebene Betriebssystem (`platform`) portierbar.</span><span class="sxs-lookup"><span data-stu-id="cafad-125">An API marked with `[SupportedOSPlatform("platform")]` is considered only portable to the specified OS `platform`.</span></span>
  - <span data-ttu-id="cafad-126">Das Attribut kann mehrmals angewendet werden, um **Unterstützung für mehrere Plattformen** anzugeben (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span><span class="sxs-lookup"><span data-stu-id="cafad-126">The attribute can be applied multiple times to indicate **multiple platform support** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span></span>
  - <span data-ttu-id="cafad-127">Das Analysetool generiert eine **Warnung**, wenn ohne einen ordnungsgemäßen **Plattformkontext** auf plattformspezifische APIs verwiesen wird:</span><span class="sxs-lookup"><span data-stu-id="cafad-127">The analyzer will produce a **warning** if platform-specific APIs are referenced without a proper **platform context**:</span></span>
    - <span data-ttu-id="cafad-128">**Warnung**, wenn das Projekt nicht auf die unterstützte Plattform ausgerichtet ist (z. B. bei einem Windows-spezifischen API-Aufruf, wenn das Projekt auf `<TargetFramework>net5.0-ios14.0</TargetFramework>` abzielt)</span><span class="sxs-lookup"><span data-stu-id="cafad-128">**Warns** if the project doesn't target the supported platform (for example, a Windows-specific API call and the project targets `<TargetFramework>net5.0-ios14.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="cafad-129">**Warnung**, wenn das Projekt auf mehrere Zielanwendungen ausgerichtet ist (`<TargetFramework>net5.0</TargetFramework>`)</span><span class="sxs-lookup"><span data-stu-id="cafad-129">**Warns** if the project is multi-targeted (`<TargetFramework>net5.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="cafad-130">**Keine Warnung**, wenn innerhalb eines Projekts auf die plattformspezifische API verwiesen wird, das auf eine der **angegebenen Plattformen** ausgerichtet ist (z. B. bei einem Windows-spezifischen API-Aufruf, wenn das Projekt auf `<TargetFramework>net5.0-windows</TargetFramework>` abzielt)</span><span class="sxs-lookup"><span data-stu-id="cafad-130">**Doesn't warn** if the platform-specific API is referenced within a project that targets any of the **specified platforms** (for example, for a Windows-specific API call and the project targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="cafad-131">**Keine Warnung**, wenn der plattformspezifische API-Aufruf durch entsprechende Plattformprüfmethoden geschützt wird (z. B. `if(OperatingSystem.IsWindows())`)</span><span class="sxs-lookup"><span data-stu-id="cafad-131">**Doesn't warn** if the platform-specific API call is guarded by corresponding platform-check methods (for example, `if(OperatingSystem.IsWindows())`).</span></span>
    - <span data-ttu-id="cafad-132">**Keine Warnung**, wenn aus dem gleichen plattformspezifischen Kontext auf die plattformspezifische API verwiesen wird (**Aufrufort auch attributiert** mit `[SupportedOSPlatform("platform")`)</span><span class="sxs-lookup"><span data-stu-id="cafad-132">**Doesn't warn** if the platform-specific API is referenced from the same platform-specific context (**call site also attributed** with `[SupportedOSPlatform("platform")`).</span></span>
- <span data-ttu-id="cafad-133">Eine API, die mit `[UnsupportedOSPlatform("platform")]` gekennzeichnet ist, gilt nur unter dem angegebenen Betriebssystem (`platform`) als nicht unterstützt, unter allen anderen Plattformen als unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cafad-133">An API marked with `[UnsupportedOSPlatform("platform")]` is considered unsupported only on the specified OS `platform` but supported for all other platforms.</span></span>
  - <span data-ttu-id="cafad-134">Das Attribut kann mehrmals für verschiedene Plattformen angewendet werden, z. B. `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span><span class="sxs-lookup"><span data-stu-id="cafad-134">The attribute can be applied multiple times with different platforms, for example, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span></span>
  - <span data-ttu-id="cafad-135">Das Analysetool generiert nur dann eine **Warnung**, wenn `platform` für den gesamten Aufrufort gilt:</span><span class="sxs-lookup"><span data-stu-id="cafad-135">The analyzer produces a **warning** only if the `platform` is effective for the call site:</span></span>
    - <span data-ttu-id="cafad-136">**Warnung**, wenn das Projekt auf die Plattform ausgerichtet ist, die laut Attribut nicht unterstützt wird (z. B. bei einer mit `[UnsupportedOSPlatform("windows")]` attributierten API, wenn der Aufrufort auf `<TargetFramework>net5.0-windows</TargetFramework>` abzielt)</span><span class="sxs-lookup"><span data-stu-id="cafad-136">**Warns** if the project targets the platform that's attributed as unsupported (for example, if the API is attributed with `[UnsupportedOSPlatform("windows")]` and the call site targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="cafad-137">**Warnung**, wenn das Projekt auf mehrere Frameworks abzielt und `platform` in der Standardelementgruppe [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) enthalten ist oder manuell in die Elementgruppe `MSBuild` \<SupportedPlatform> eingefügt wird:</span><span class="sxs-lookup"><span data-stu-id="cafad-137">**Warns** if the project is multi-targeted and the `platform` is included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group, or the `platform` is manually included within the `MSBuild` \<SupportedPlatform> items group:</span></span>

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - <span data-ttu-id="cafad-138">**Keine Warnung**, wenn Sie eine App erstellen, die nicht auf die nicht unterstützte Plattform oder mehrere Zielplattform ausgerichtet ist, und die Plattform nicht in der Standardelementgruppe [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) enthalten ist</span><span class="sxs-lookup"><span data-stu-id="cafad-138">**Doesn't warn** if you're building an app that doesn't target the unsupported platform or is multi-targeted and the platform is not included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group.</span></span>
- <span data-ttu-id="cafad-139">Beide Attribute können mit oder ohne Versionsnummern als Teil des Plattformnamens instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-139">Both attributes can be instantiated with or without version numbers as part of the platform name.</span></span>
  - <span data-ttu-id="cafad-140">Versionsnummern weisen das Format `major.minor[.build[.revision]]` auf. `major.minor` ist erforderlich, die Teile `build` und `revision` sind optional.</span><span class="sxs-lookup"><span data-stu-id="cafad-140">Version numbers are in the format of `major.minor[.build[.revision]]`; `major.minor` is required and the `build` and `revision` parts are optional.</span></span> <span data-ttu-id="cafad-141">„Windows7.0“ gibt z. B. die Windows-Version 7.0 an, „Windows“ wird jedoch wie „Windows 0.0“ interpretiert.</span><span class="sxs-lookup"><span data-stu-id="cafad-141">For example, "Windows7.0" indicates Windows version 7.0, but "Windows" is interpreted as Windows 0.0.</span></span>

<span data-ttu-id="cafad-142">Weitere Informationen finden Sie unter [Beispiele für die Funktionsweise von Attributen und ihre Diagnosen](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span><span class="sxs-lookup"><span data-stu-id="cafad-142">For more information, see [examples of how the attributes work and what diagnostics they cause](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span></span>

### <a name="advanced-scenarios-for-combining-attributes"></a><span data-ttu-id="cafad-143">Erweiterte Szenarios für die Kombination von Attributen</span><span class="sxs-lookup"><span data-stu-id="cafad-143">Advanced scenarios for combining attributes</span></span>

- <span data-ttu-id="cafad-144">Wenn eine Kombination der Attribute `[SupportedOSPlatform]` und `[UnsupportedOSPlatform]` vorliegt, werden alle Attribute nach dem Bezeichner der Betriebssystemplattform gruppiert:</span><span class="sxs-lookup"><span data-stu-id="cafad-144">If a combination of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are present, all attributes are grouped by OS platform identifier:</span></span>
  - <span data-ttu-id="cafad-145">**Liste mit ausschließlich unterstützten Plattformen:**</span><span class="sxs-lookup"><span data-stu-id="cafad-145">**Supported only list**.</span></span> <span data-ttu-id="cafad-146">Wenn die niedrigste Version jeder Betriebssystemplattform das Attribut `[SupportedOSPlatform]` aufweist, gilt die API als nur von den aufgelisteten Plattformen unterstützt und für alle anderen Plattformen als nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cafad-146">If the lowest version for each OS platform is a `[SupportedOSPlatform]` attribute, the API is considered to only be supported by the listed platforms and unsupported by all other platforms.</span></span> <span data-ttu-id="cafad-147">Die optionalen `[UnsupportedOSPlatform]`-Attribute für die einzelnen Plattform können nur eine höhere Version der unterstützten Mindestversion aufweisen, was bedeutet, dass die API-Unterstützung ab der angegebenen Version entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="cafad-147">The optional `[UnsupportedOSPlatform]` attributes for each platform can only have higher version of the minimum supported version, which denotes that the API is removed starting from the specified version.</span></span>

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - <span data-ttu-id="cafad-148">**Liste mit ausschließlich nicht unterstützten Plattformen:**</span><span class="sxs-lookup"><span data-stu-id="cafad-148">**Unsupported only list**.</span></span> <span data-ttu-id="cafad-149">Wenn die niedrigste Version jeder Betriebssystemplattform das Attribut `[UnsupportedOSPlatform]` aufweist, gilt die API als nur von den aufgelisteten Plattformen nicht unterstützt und für alle anderen Plattformen als unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cafad-149">If the lowest version for each OS platform is an `[UnsupportedOSPlatform]` attribute, then the API is considered to only be unsupported by the listed platforms and supported by all other platforms.</span></span> <span data-ttu-id="cafad-150">Die Liste kann das Attribut `[SupportedOSPlatform]` für die gleiche Plattform, aber eine höhere Version aufweisen, was bedeutet, dass die API ab dieser Version unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="cafad-150">The list could have `[SupportedOSPlatform]` attribute with the same platform but a higher version, which denotes that the API is supported starting from that version.</span></span>
  
    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - <span data-ttu-id="cafad-151">**Inkonsistente Liste:**</span><span class="sxs-lookup"><span data-stu-id="cafad-151">**Inconsistent list**.</span></span> <span data-ttu-id="cafad-152">Wenn die niedrigste Version für einige Plattformen das Attribut `[SupportedOSPlatform]`, für andere Plattformen jedoch das Attribut `[UnsupportedOSPlatform]` aufweist, wird die Liste als inkonsistent eingestuft. Dies wird vom Analysetool nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cafad-152">If the lowest version for some platforms is `[SupportedOSPlatform]` while it is `[UnsupportedOSPlatform]` for other platforms, is considered inconsistent, which is not supported for the analyzer.</span></span>
  - <span data-ttu-id="cafad-153">Wenn die niedrigsten Versionen der Attribute `[SupportedOSPlatform]` und `[UnsupportedOSPlatform]` gleich sind, gilt die Plattform für das Analysetool als Teil der **Liste mit ausschließlich unterstützten Plattformen**.</span><span class="sxs-lookup"><span data-stu-id="cafad-153">If the lowest versions of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are equal, the analyzer considers the platform as part of the **Supported only list**.</span></span>
- <span data-ttu-id="cafad-154">Plattformattribute können auf Typen, Member (Methoden, Felder, Eigenschaften und Ereignisse) und Assemblys mit einem anderen Plattformnamen und/oder einer anderen Version angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-154">Platform attributes can be applied to types, members (methods, fields, properties, and events) and assemblies with different platform name and / or version.</span></span>
  - <span data-ttu-id="cafad-155">Attribute, die auf das oberste Ziel (`target`) angewendet werden, gelten infolge auch für alle Member und Typen.</span><span class="sxs-lookup"><span data-stu-id="cafad-155">Attributes applied at the top level `target` affect all of its members and types.</span></span>
  - <span data-ttu-id="cafad-156">Untergeordnete Attribute gelten nur, wenn sie die Regel „Untergeordnete Attribute können die Plattformunterstützung nur einschränken, nicht erweitern“ befolgen.</span><span class="sxs-lookup"><span data-stu-id="cafad-156">Child level attributes only apply if they adhere to the rule "child annotations can narrow the platforms support, but they cannot widen it".</span></span>
    - <span data-ttu-id="cafad-157">Wenn das übergeordnete Element eine **Liste mit ausschließlich unterstützten Plattformen** aufweist, können die untergeordneten Memberattribute keine neue Plattformunterstützung hinzufügen, da dies die Unterstützung für das übergeordnete Element erweitern würde. Neue Plattformunterstützung kann jedoch nur dem übergeordneten Element selbst hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-157">When parent has **Supported only** list, then child member attributes could not add a new platform support as that would be extending parent support, a new platform support can only added to the parent itself.</span></span> <span data-ttu-id="cafad-158">Die Memberattribute können jedoch das Attribut `Supported` für dieselbe Plattform mit höheren Versionen aufweisen, da dies die Unterstützung einschränken würde.</span><span class="sxs-lookup"><span data-stu-id="cafad-158">But it can have `Supported` attribute for same platform with later versions as that will narrow the support.</span></span> <span data-ttu-id="cafad-159">Sie können außerdem das Attribut `Unsupported` für dieselbe Plattform aufweisen, das auch dies die übergeordnete Unterstützung eingrenzen würde.</span><span class="sxs-lookup"><span data-stu-id="cafad-159">Also it can have `Unsupported` attribute with same platform as that will also narrow parent support.</span></span>
    - <span data-ttu-id="cafad-160">Wenn das übergeordnete Element eine **Liste mit ausschließlich nicht unterstützten Plattformen** aufweist, können die untergeordneten Memberattribute neue Plattformunterstützung hinzufügen, da die übergeordnete Unterstützung eingeschränkt werden würde. Die Memberattribute können jedoch nicht das Attribut `Supported` für dieselbe Plattform wie im übergeordneten Element aufweisen, da dies die übergeordnete Unterstützung erweitern würde.</span><span class="sxs-lookup"><span data-stu-id="cafad-160">When parent has **Unsupported only** list, then child member attributes could add a new platform support as that would be narrowing parent support, but it cannot have `Supported` attribute for same platform as in the parent, that would extend parent support.</span></span> <span data-ttu-id="cafad-161">Unterstützung für dieselbe Plattform kann nur auf übergeordneter Ebene hinzugefügt werden, auf der das ursprüngliche `Unsupported`-Attribut angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="cafad-161">Support for the same platform can be added only to parent level where the original `Unsupported` attribute applied.</span></span>
  - <span data-ttu-id="cafad-162">Wenn `[SupportedOSPlatform("platformVersion")]` mehr als einmal auf eine API mit demselben `platform`-Namen angewendet wird, wird nur diejenige mit der Mindestversion vom Analysetool berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="cafad-162">If `[SupportedOSPlatform("platformVersion")]` is applied more than once for an API with the same `platform` name only the one with minimum version is considered by the analyzer.</span></span>
  - <span data-ttu-id="cafad-163">Wenn `[UnsupportedOSPlatform("platformVersion")]` mehr als zweimal auf eine API mit demselben `platform`-Namen angewendet wird, werden nur die beiden mit der frühesten Version vom Analysetool berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="cafad-163">If `[UnsupportedOSPlatform("platformVersion")]` is applied more than twice for an API with the same `platform` name, only the two with earliest versions are considered by the analyzer.</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="cafad-164">Wenn die Unterstützung für eine API zunächst vorhanden war und in einer höheren Version abgeschafft wurde, wird sie erwartungsgemäß in einer noch höheren Version nicht wieder eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cafad-164">An API that was supported initially but unsupported (removed) in a later version is not expected to get resupported in an even later version.</span></span>

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a><span data-ttu-id="cafad-165">Beispiele für die Funktionsweise von Attributen und ihre Diagnosen</span><span class="sxs-lookup"><span data-stu-id="cafad-165">Examples of how the attributes work and what diagnostics they produce</span></span>

  ```csharp
  // An API supported only on Windows.
  [SupportedOSPlatform("Windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  public void Caller()
  {
      WindowsOnlyApi(); // warns: 'WindowsOnlyApi' is supported on 'windows'

      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Windows'
      // warns: 'SupportedOnWindowsAndLinuxOnly' is supported on 'Linux'
      SupportedOnWindowsAndLinuxOnly();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 8.0 and later  
      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // for same platform analyzer only warn for the latest version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  public void Caller2()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'android'

      // warns:'StartedWindowsSupportFromVersion8' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFromVersion8' is supported on 'windows' 8.0 and later
      StartedWindowsSupportFromVersion8();

      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is unsupported on 'windows'  
      // warns:'StartedWindowsSupportFrom8UnsupportedFrom10' is supported on 'windows' 8.0 and later
      // even there were 3 diagnostics found analyzer warn only for the first 2.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

## <a name="handle-reported-warnings"></a><span data-ttu-id="cafad-166">Verarbeiten gemeldeter Warnungen</span><span class="sxs-lookup"><span data-stu-id="cafad-166">Handle reported warnings</span></span>

<span data-ttu-id="cafad-167">Die empfohlene Umgangsweise mit diesen Diagnosen besteht darin, sicherzustellen, dass plattformspezifische APIs nur auf der passenden Plattform aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-167">The recommended way to deal with these diagnostics is to make sure you only call platform-specific APIs when running on an appropriate platform.</span></span> <span data-ttu-id="cafad-168">Nachstehend sind Ihre Optionen für die Behebung dieser Warnungen aufgeführt. Wählen Sie die Vorgehensweise aus, die sich am besten für Ihre Situation eignet:</span><span class="sxs-lookup"><span data-stu-id="cafad-168">Following are the options you can use to address the warnings; choose whichever is most appropriate for your situation:</span></span>

- <span data-ttu-id="cafad-169">**Schützen des Aufrufs:**</span><span class="sxs-lookup"><span data-stu-id="cafad-169">**Guard the call**.</span></span> <span data-ttu-id="cafad-170">Zu diesem Zweck können Sie den Code bedingt zur Laufzeit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cafad-170">You can achieve this by conditionally calling the code at run time.</span></span> <span data-ttu-id="cafad-171">Überprüfen Sie, ob die Ausführung unter einem gewünschten Betriebssystem (`Platform`) erfolgt, indem Sie eine der Plattformprüfmethoden verwenden, z. B. `OperatingSystem.Is<Platform>()` oder `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span><span class="sxs-lookup"><span data-stu-id="cafad-171">Check whether you’re running on a desired `Platform` by using one of platform-check methods, for example, `OperatingSystem.Is<Platform>()` or `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span></span>

- <span data-ttu-id="cafad-172">**Markieren des Aufruforts als plattformspezifisch:**</span><span class="sxs-lookup"><span data-stu-id="cafad-172">**Mark the call site as platform-specific**.</span></span> <span data-ttu-id="cafad-173">Sie können auch Ihre eigenen APIs als plattformspezifisch kennzeichnen und die Anforderungen so effektiv an Ihre Aufrufer weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="cafad-173">You can also choose to mark your own APIs as being platform-specific, thus effectively just forwarding the requirements to your callers.</span></span> <span data-ttu-id="cafad-174">Kennzeichnen Sie die enthaltende Methode, den enthaltenden Typ oder die gesamte Assembly mit denselben Attributen wie den referenzierten plattformabhängigen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="cafad-174">Mark the containing method or type or the entire assembly with the same attributes as the referenced platform-dependent call.</span></span> <span data-ttu-id="cafad-175">[Beispiele](#mark-call-site-as-platform-specific).</span><span class="sxs-lookup"><span data-stu-id="cafad-175">[Examples](#mark-call-site-as-platform-specific).</span></span>

- <span data-ttu-id="cafad-176">**Bestätigen des Aufruforts mit einer Plattformüberprüfung:**</span><span class="sxs-lookup"><span data-stu-id="cafad-176">**Assert the call site with platform check**.</span></span> <span data-ttu-id="cafad-177">Wenn Sie den Mehraufwand einer zusätzlichen `if`-Anweisung zur Laufzeit vermeiden möchten, verwenden Sie <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cafad-177">If you don't want the overhead of an additional `if` statement at run time, use <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cafad-178">[Beispiel](#assert-the-call-site-with-platform-check).</span><span class="sxs-lookup"><span data-stu-id="cafad-178">[Example](#assert-the-call-site-with-platform-check).</span></span>

- <span data-ttu-id="cafad-179">**Löschen des Codes:**</span><span class="sxs-lookup"><span data-stu-id="cafad-179">**Delete the code**.</span></span> <span data-ttu-id="cafad-180">Dies ist üblicherweise nicht die gewünschte Vorgehensweise, da Sie möglicherweise Kunden verlieren, wenn Ihr Code von Windows-Benutzern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cafad-180">Generally not what you want because it means you lose fidelity when your code is used by Windows users.</span></span> <span data-ttu-id="cafad-181">Falls eine plattformübergreifende Alternative vorhanden ist, sollten Sie lieber diese anstelle der plattformspezifischen APIs wählen.</span><span class="sxs-lookup"><span data-stu-id="cafad-181">For cases where a cross-platform alternative exists, you’re likely better off using that over platform-specific APIs.</span></span>

- <span data-ttu-id="cafad-182">**Unterdrücken der Warnung:**</span><span class="sxs-lookup"><span data-stu-id="cafad-182">**Suppress the warning**.</span></span> <span data-ttu-id="cafad-183">Sie können die Warnung auch einfach unterdrücken, entweder über „editor.config“ oder `#pragma warning disable ca1416`.</span><span class="sxs-lookup"><span data-stu-id="cafad-183">You can also simply suppress the warning, either via editor.config or `#pragma warning disable ca1416`.</span></span> <span data-ttu-id="cafad-184">Diese Option sollte jedoch bei der Verwendung von plattformspezifischen APIs als allerletzte Maßnahme eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-184">However, this option should be a last resort when using platform-specific APIs.</span></span>

### <a name="guard-platform-specific-apis-with-guard-methods"></a><span data-ttu-id="cafad-185">Schützen von plattformspezifischen APIs mit Schutzmethoden</span><span class="sxs-lookup"><span data-stu-id="cafad-185">Guard platform-specific APIs with guard methods</span></span>

<span data-ttu-id="cafad-186">Der Plattformname der Schutzmethode muss mit dem aufrufenden plattformabhängigen API-Plattformnamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cafad-186">The guard method's platform name should match with the calling platform-dependent API platform name.</span></span> <span data-ttu-id="cafad-187">Wenn die Plattformzeichenfolge der aufrufenden API die Version enthält:</span><span class="sxs-lookup"><span data-stu-id="cafad-187">If the platform string of the calling API includes the version:</span></span>

- <span data-ttu-id="cafad-188">muss die Plattformversion (`version`) der Schutzmethode für das Attribut `[SupportedOSPlatform("platformVersion")]` größer oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="cafad-188">For the `[SupportedOSPlatform("platformVersion")]` attribute, the guard method platform `version` should be greater than or equal to the calling platform's `Version`.</span></span>
- <span data-ttu-id="cafad-189">muss die Plattformversion (`version`) der Schutzmethode für das Attribut `[UnsupportedOSPlatform("platformVersion")]` kleiner oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="cafad-189">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the guard method's platform `version` should be less than or equal to the calling platform's `Version`.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis() // Allow list calls
  {
      if (OperatingSystem.IsWindows())
      {
          WindowsOnlyApi(); // will not warn
      }

      if (OperatingSystem.IsLinux())
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn, within one of the supported context
      }

      // Can use &&, || logical operators to guard combined attributes
      if (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10.0.19041)))
      {
          ApiSupportedFromWindows8UnsupportFromWindows10();
      }

      if (OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903))
      {
          AssemblySupportedOnWindowsApiSupportedFromWindows10(); // Only need to check latest supported version
      }
  }

  public void CallingUnsupportedApis()
  {
      if (!OperatingSystem.IsAndroid())
      {
          DoesNotWorkOnAndroid(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || OperatingSystem.IsWindowsVersionAtLeast(8))
      {
          StartedWindowsSupportFromVersion8(); // will not warn
      }

      if (!OperatingSystem.IsWindows() || // supported all other platforms
         (OperatingSystem.IsWindowsVersionAtLeast(8) && !OperatingSystem.IsWindowsVersionAtLeast(10, 0, 1903)))
      {
          StartedWindowsSupportFrom8UnsupportedFrom10(); // will not warn
      }
  }
  ```

- <span data-ttu-id="cafad-190">und Code geschützt werden muss, der auf netstandard oder netcoreapp ausgerichtet ist, wo keine neuen <xref:System.OperatingSystem>-APIs verfügbar sind, kann die API <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> verwendet werden. Diese wird auch vom Analysetool berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="cafad-190">if you need to guard a code that targets netstandard or netcoreapp where new <xref:System.OperatingSystem> APIs are not available <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API can be used and will be respected by the analyzer.</span></span> <span data-ttu-id="cafad-191">Sie ist jedoch nicht so optimiert, wie die neuen APIs, die über <xref:System.OperatingSystem> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-191">But it's not as optimized as the new APIs added in <xref:System.OperatingSystem>.</span></span> <span data-ttu-id="cafad-192">Falls die Plattform in der Struktur <xref:System.Runtime.InteropServices.OSPlatform> nicht unterstützt wird, können Sie die Methode <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform") verwenden, die auch vom Analysetool berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="cafad-192">In case the platform is not supported in <xref:System.Runtime.InteropServices.OSPlatform> struct, you can use <xref:System.Runtime.InteropServices.OSPlatform.Create%2A?displayProperty=nameWithType>("platform") which is also respected by the analyzer.</span></span>

  ```csharp
  public void CallingSupportedOnlyApis()
  {
      if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
      {
          SupportedOnWindowsAndLinuxOnly(); // will not warn
      }

      if (RuntimeInformation.IsOSPlatform(OSPlatform.Create("browser")))
      {
          ApiOnlySupportedOnBrowser(); // call of browser specific API
      }
  }
  ```

### <a name="mark-call-site-as-platform-specific"></a><span data-ttu-id="cafad-193">Markieren des Aufruforts als plattformspezifisch</span><span class="sxs-lookup"><span data-stu-id="cafad-193">Mark call site as platform-specific</span></span>

<span data-ttu-id="cafad-194">Plattformnamen sollten mit der aufrufenden plattformabhängigen API übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cafad-194">Platform names should match the calling platform-dependent API.</span></span> <span data-ttu-id="cafad-195">Wenn die Plattformzeichenfolge eine Version enthält:</span><span class="sxs-lookup"><span data-stu-id="cafad-195">If the platform string includes a version:</span></span>

- <span data-ttu-id="cafad-196">muss die Plattformversion (`version`) des Aufruforts für das Attribut `[SupportedOSPlatform("platformVersion")]` größer oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="cafad-196">For the `[SupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be greater than or equal to the calling platform's `Version`</span></span>
- <span data-ttu-id="cafad-197">muss die Plattformversion (`version`) des Aufruforts für das Attribut `[UnsupportedOSPlatform("platformVersion")]` kleiner oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="cafad-197">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be less than or equal to the calling platform's `Version`</span></span>

  ```csharp
  // an API supported only on Windows.
  [SupportedOSPlatform("windows")]
  public void WindowsOnlyApi() { }

  // an API supported on Windows and Linux.
  [SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("Linux")]
  public void SupportedOnWindowsAndLinuxOnly() { }

  // an API only supported on Windows 8.0 and later, not supported for all other.
  // an API is removed/unsupported from version 10.0.19041.0.
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void ApiSupportedFromWindows8UnsupportFromWindows10() { }

  // an Assembly supported on Windows, the API added from version 10.0.19041.0.
  [assembly: SupportedOSPlatform("Windows")]
  [SupportedOSPlatform("windows10.0.19041.0")]
  public void AssemblySupportedOnWindowsApiSupportedFromWindows10() { }

  [SupportedOSPlatform("windows8.0")] // call site attributed Windows 8.0 or above.
  public void Caller()
  {
      WindowsOnlyApi(); // will not warn as call site is for Windows.

      // will not warn as call site is for Windows.
      SupportedOnWindowsAndLinuxOnly();

      // will not warn for the API's [SupportedOSPlatform("windows8.0")] attribute.
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // as the call site version is lower than calling version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows11.0")] // call site attributed with windows 11.0 or above.
  public void Caller2()
  {
      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is unsupported on 'windows' 10.0.19041.0 and later
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // will not warn as call site version higher than calling API.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")] // call site supports Windows from version 8.0 to 10.0.19041.0.
  public void Caller3()
  {
      // will not warn as caller has exact same attributes.
      ApiSupportedFromWindows8UnsupportFromWindows10();

      // Warns: 'ApiSupportedFromWindows8UnsupportFromWindows10' is supported on 'windows' 10.0.19041.0 and later
      // As call site stopped support from that version.
      AssemblySupportedOnWindowsApiSupportedFromWindows10();
  }

  // an API not supported on Android but supported on all other.
  [UnsupportedOSPlatform("android")]  
  public void DoesNotWorkOnAndroid() { }

  // an API was unsupported on Windows until version 8.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  public void StartedWindowsSupportFromVersion8() { }

  // an API was unsupported on Windows until version8.0.
  // Then the API is removed (unsupported) from version 10.0.19041.0.
  // The API is considered supported everywhere else without constraints.
  [UnsupportedOSPlatform("windows")]
  [SupportedOSPlatform("windows8.0")]
  [UnsupportedOSPlatform("windows10.0.19041.0")]
  public void StartedWindowsSupportFrom8UnsupportedFrom10() { }

  [UnsupportedOSPlatform("windows")] // Caller no support Windows for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // warns 'DoesNotWorkOnAndroid' is unsupported on 'Android'.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }

  [UnsupportedOSPlatform("windows")]
  [UnsupportedOSPlatform("android")] // Caller not support Windows and Android for any version.
  public void Caller4()
  {
      DoesNotWorkOnAndroid(); // will not warn as call site not supports Android.

      // will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFromVersion8();

      // same, will not warns as the call site not support Windows at all, but supports all other.
      StartedWindowsSupportFrom8UnsupportedFrom10();
  }
  ```

### <a name="assert-the-call-site-with-platform-check"></a><span data-ttu-id="cafad-198">Bestätigen des Aufruforts mit einer Plattformüberprüfung</span><span class="sxs-lookup"><span data-stu-id="cafad-198">Assert the call-site with platform check</span></span>

<span data-ttu-id="cafad-199">Alle in den [Beispielen für den Plattformschutz](#guard-platform-specific-apis-with-guard-methods) verwendeten bedingten Überprüfungen können auch als Bedingung in <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cafad-199">All the conditional checks used in the [platform guard examples](#guard-platform-specific-apis-with-guard-methods) can also be used as the condition for <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span>

  ```csharp
  // An API supported only on Linux.
  [SupportedOSPlatform("linux")]
  public void LinuxOnlyApi() { }

  public void Caller()
  {
      Debug.Assert(OperatingSystem.IsLinux());

      LinuxOnlyApi(); // will not warn
  }
  ```

## <a name="see-also"></a><span data-ttu-id="cafad-200">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cafad-200">See also</span></span>

- [<span data-ttu-id="cafad-201">Namen von Zielframeworks in .NET 5</span><span class="sxs-lookup"><span data-stu-id="cafad-201">Target Framework Names in .NET 5</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [<span data-ttu-id="cafad-202">Kommentieren von plattformspezifischen APIs und Erkennen der Verwendung</span><span class="sxs-lookup"><span data-stu-id="cafad-202">Annotating platform-specific APIs and detecting its use</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [<span data-ttu-id="cafad-203">Annotieren von APIs als nicht unterstützt auf bestimmten Plattformen</span><span class="sxs-lookup"><span data-stu-id="cafad-203">Annotating APIs as unsupported on specific platforms</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [<span data-ttu-id="cafad-204">CA1416: Analysetool für die Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="cafad-204">CA1416 Platform compatibility analyzer</span></span>](/visualstudio/code-quality/ca1416)
- [<span data-ttu-id="cafad-205">.NET API-Analysetool</span><span class="sxs-lookup"><span data-stu-id="cafad-205">.NET API analyzer</span></span>](../../standard/analyzers/api-analyzer.md)
