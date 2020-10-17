---
title: Analysetool für die Plattformkompatibilität
description: Ein Roslyn-Analysetool, das helfen kann, in plattformübergreifenden Apps und Bibliotheken Probleme mit der Plattformkompatibilität zu erkennen
author: buyaa-n
ms.date: 09/17/2020
ms.openlocfilehash: 44c2c2d9674b13f314a057f847df2d4d474cc2be
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805297"
---
# <a name="platform-compatibility-analyzer"></a><span data-ttu-id="5477b-103">Analysetool für die Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="5477b-103">Platform compatibility analyzer</span></span>

<span data-ttu-id="5477b-104">Sie haben wahrscheinlich bereits von .NET als einer einzigen, einheitlichen Plattform für die Entwicklung beliebiger Anwendungstypen gehört.</span><span class="sxs-lookup"><span data-stu-id="5477b-104">You've probably heard the motto of "One .NET": a single, unified platform for building any type of application.</span></span> <span data-ttu-id="5477b-105">Das .NET 5.0 SDK enthält ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin und ML.NET, und Unterstützung für weitere Plattformen wird im Laufe der Zeit hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5477b-105">The .NET 5.0 SDK includes ASP.NET Core, Entity Framework Core, WinForms, WPF, Xamarin, and ML.NET, and will add support for more platforms over time.</span></span> <span data-ttu-id="5477b-106">Es ist das Ziel von .NET 5.0, dass Sie sich keine Gedanken um die verschiedenen .NET-Varianten machen müssen, ohne dass das zugrunde liegende Betriebssystem zu diesem Zweck vollständig abstrahiert wird.</span><span class="sxs-lookup"><span data-stu-id="5477b-106">.NET 5.0 strives to provide an experience where you don't have to reason about the different flavors of .NET, but doesn't attempt to fully abstract away the underlying operating system (OS).</span></span> <span data-ttu-id="5477b-107">Sie sind weiterhin in der Lage, plattformspezifische APIs (z. B. P/Invokes, WinRT oder die Xamarin-Bindungen für iOS und Android) aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5477b-107">You'll continue to be able to call platform-specific APIs, for example, P/Invokes, WinRT, or the Xamarin bindings for iOS and Android.</span></span>

<span data-ttu-id="5477b-108">Durch die Verwendung plattformspezifischer APIs für eine Komponente funktioniert der Code jedoch nicht mehr auf allen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5477b-108">But using platform-specific APIs on a component means the code no longer works across all platforms.</span></span> <span data-ttu-id="5477b-109">Es fehlte eine Methode, die dies zur Entwurfszeit erkennt, damit Entwickler eine Diagnose erhalten, wenn sie versehentlich plattformspezifische APIs verwenden.</span><span class="sxs-lookup"><span data-stu-id="5477b-109">We needed a way to detect this at design time so developers get diagnostics when they inadvertently use platform-specific APIs.</span></span> <span data-ttu-id="5477b-110">Aus diesem Grund führt .NET 5.0 das [Analysetool für die Plattformkompatibilität](/visualstudio/code-quality/ca1416) sowie ergänzende APIs ein, damit Entwickler ggf. plattformspezifische APIs erkennen und verwenden können, wenn es sinnvoll ist.</span><span class="sxs-lookup"><span data-stu-id="5477b-110">To achieve this goal, .NET 5.0 introduces the [platform compatibility analyzer](/visualstudio/code-quality/ca1416) and complementary APIs to help developers identify and use platform-specific APIs where appropriate.</span></span>
<span data-ttu-id="5477b-111">Zu den neuen APIs zählen:</span><span class="sxs-lookup"><span data-stu-id="5477b-111">The new APIs include:</span></span>

- <span data-ttu-id="5477b-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> zum Kommentieren von APIs als plattformspezifisch und <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>, um APIs als für ein bestimmtes Betriebssystem nicht unterstützt zu annotieren.</span><span class="sxs-lookup"><span data-stu-id="5477b-112"><xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> to annotate APIs as being platform-specific and <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> to annotate APIs as being unsupported on a particular OS.</span></span> <span data-ttu-id="5477b-113">Diese Attribute können optional die Versionsnummer enthalten und wurden bereits auf einige plattformspezifische APIs in den .NET-Kernbibliotheken angewendet.</span><span class="sxs-lookup"><span data-stu-id="5477b-113">These attributes can optionally include the version number, and have already been applied to some platform-specific APIs in the core .NET libraries.</span></span>
- <span data-ttu-id="5477b-114">Die statischen Methoden `Is<Platform>()` und `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` in der Klasse <xref:System.OperatingSystem?displayProperty=nameWithType> zum sicheren Aufrufen von plattformspezifischen APIs.</span><span class="sxs-lookup"><span data-stu-id="5477b-114">`Is<Platform>()` and `Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)` static methods in the <xref:System.OperatingSystem?displayProperty=nameWithType> class for safely calling platform-specific APIs.</span></span> <span data-ttu-id="5477b-115">Mit <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> kann beispielsweise ein Aufruf einer Windows-spezifischen API und mit <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() ein versionierter Windows-spezifischer API-Aufruf geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-115">For example, <xref:System.OperatingSystem.IsWindows?displayProperty=nameWithType> can be used to guard a call to a Windows-specific API, and <xref:System.OperatingSystem.IsWindowsVersionAtLeast%2A?displayProperty=nameWithType>() can be used to guard a versioned Windows-specific API call.</span></span> <span data-ttu-id="5477b-116">In diesen [Beispielen](#guard-platform-specific-apis-with-guard-methods) wird veranschaulicht, wie mithilfe dieser Methoden plattformspezifische API-Verweise geschützt werden können.</span><span class="sxs-lookup"><span data-stu-id="5477b-116">See these [examples](#guard-platform-specific-apis-with-guard-methods) of how these methods can be used as guards of platform-specific API references.</span></span>

> [!TIP]
> <span data-ttu-id="5477b-117">Das Analysetool für die Plattformkompatibilität aktualisiert und ersetzt das Feature für die [Ermittlung plattformübergreifender Probleme](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) des [.NET-API-Analysetools](../../standard/analyzers/api-analyzer.md).</span><span class="sxs-lookup"><span data-stu-id="5477b-117">The platform compatibility analyzer upgrades and replaces the [Discovering cross-platform issues](../../standard/analyzers/api-analyzer.md#discover-cross-platform-issues) feature of the [.NET API analyzer](../../standard/analyzers/api-analyzer.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5477b-118">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5477b-118">Prerequisites</span></span>

<span data-ttu-id="5477b-119">Bei dem Analysetool für die Plattformkompatibilität handelt es sich um eines der Codequalitätsanalysetools von Roslyn.</span><span class="sxs-lookup"><span data-stu-id="5477b-119">The platform compatibility analyzer is one of the Roslyn code quality analyzers.</span></span> <span data-ttu-id="5477b-120">Ab .NET 5.0 sind diese Analysetools im [.NET SDK](../../fundamentals/code-analysis/overview.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="5477b-120">Starting in .NET 5.0, these analyzers are [included with the .NET SDK](../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="5477b-121">Das Analysetool für die Plattformkompatibilität ist standardmäßig nur für Projekte aktiviert, die für `net5.0` oder höher entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-121">The platform compatibility analyzer is enabled by default only for projects that target `net5.0` or a later version.</span></span> <span data-ttu-id="5477b-122">Sie können es jedoch auch für Projekte [aktivieren](/visualstudio/code-quality/ca1416.md#configurability), die auf andere Frameworks abzielen.</span><span class="sxs-lookup"><span data-stu-id="5477b-122">However, you can [enable](/visualstudio/code-quality/ca1416.md#configurability) it for projects that target other frameworks.</span></span>

## <a name="how-the-analyzer-determines-platform-dependency"></a><span data-ttu-id="5477b-123">Bestimmen der Plattformabhängigkeit mithilfe des Analysetools</span><span class="sxs-lookup"><span data-stu-id="5477b-123">How the analyzer determines platform dependency</span></span>

- <span data-ttu-id="5477b-124">Bei einer **nicht attributierten API** wird davon ausgegangen, dass sie auf **allen Betriebssystemplattformen** funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5477b-124">An **unattributed API** is considered to work on **all OS platforms**.</span></span>
- <span data-ttu-id="5477b-125">Eine API, die mit `[SupportedOSPlatform("platform")]` gekennzeichnet ist, gilt als nur für das angegebene Betriebssystem (`platform`) portierbar.</span><span class="sxs-lookup"><span data-stu-id="5477b-125">An API marked with `[SupportedOSPlatform("platform")]` is considered only portable to the specified OS `platform`.</span></span>
  - <span data-ttu-id="5477b-126">Das Attribut kann mehrmals angewendet werden, um **Unterstützung für mehrere Plattformen** anzugeben (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span><span class="sxs-lookup"><span data-stu-id="5477b-126">The attribute can be applied multiple times to indicate **multiple platform support** (`[SupportedOSPlatform("windows"), SupportedOSPlatform("Android6.0")]`).</span></span>
  - <span data-ttu-id="5477b-127">Das Analysetool generiert eine **Warnung**, wenn ohne einen ordnungsgemäßen **Plattformkontext** auf plattformspezifische APIs verwiesen wird:</span><span class="sxs-lookup"><span data-stu-id="5477b-127">The analyzer will produce a **warning** if platform-specific APIs are referenced without a proper **platform context**:</span></span>
    - <span data-ttu-id="5477b-128">**Warnung**, wenn das Projekt nicht auf die unterstützte Plattform ausgerichtet ist (z. B. bei einem Windows-spezifischen API-Aufruf, wenn das Projekt auf `<TargetFramework>net5.0-ios14.0</TargetFramework>` abzielt)</span><span class="sxs-lookup"><span data-stu-id="5477b-128">**Warns** if the project doesn't target the supported platform (for example, a Windows-specific API call and the project targets `<TargetFramework>net5.0-ios14.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="5477b-129">**Warnung**, wenn das Projekt auf mehrere Zielanwendungen ausgerichtet ist (`<TargetFramework>net5.0</TargetFramework>`)</span><span class="sxs-lookup"><span data-stu-id="5477b-129">**Warns** if the project is multi-targeted (`<TargetFramework>net5.0</TargetFramework>`).</span></span>
    - <span data-ttu-id="5477b-130">**Keine Warnung**, wenn innerhalb eines Projekts auf die plattformspezifische API verwiesen wird, das auf eine der **angegebenen Plattformen** ausgerichtet ist (z. B. bei einem Windows-spezifischen API-Aufruf, wenn das Projekt auf `<TargetFramework>net5.0-windows</TargetFramework>` abzielt)</span><span class="sxs-lookup"><span data-stu-id="5477b-130">**Doesn't warn** if the platform-specific API is referenced within a project that targets any of the **specified platforms** (for example, for a Windows-specific API call and the project targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="5477b-131">**Keine Warnung**, wenn der plattformspezifische API-Aufruf durch entsprechende Plattformprüfmethoden geschützt wird (z. B. `if(OperatingSystem.IsWindows())`)</span><span class="sxs-lookup"><span data-stu-id="5477b-131">**Doesn't warn** if the platform-specific API call is guarded by corresponding platform-check methods (for example, `if(OperatingSystem.IsWindows())`).</span></span>
    - <span data-ttu-id="5477b-132">**Keine Warnung**, wenn aus dem gleichen plattformspezifischen Kontext auf die plattformspezifische API verwiesen wird (**Aufrufort auch attributiert** mit `[SupportedOSPlatform("platform")`)</span><span class="sxs-lookup"><span data-stu-id="5477b-132">**Doesn't warn** if the platform-specific API is referenced from the same platform-specific context (**call site also attributed** with `[SupportedOSPlatform("platform")`).</span></span>
- <span data-ttu-id="5477b-133">Eine API, die mit `[UnsupportedOSPlatform("platform")]` gekennzeichnet ist, gilt nur unter dem angegebenen Betriebssystem (`platform`) als nicht unterstützt, unter allen anderen Plattformen als unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5477b-133">An API marked with `[UnsupportedOSPlatform("platform")]` is considered unsupported only on the specified OS `platform` but supported for all other platforms.</span></span>
  - <span data-ttu-id="5477b-134">Das Attribut kann mehrmals für verschiedene Plattformen angewendet werden, z. B. `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span><span class="sxs-lookup"><span data-stu-id="5477b-134">The attribute can be applied multiple times with different platforms, for example, `[UnsupportedOSPlatform("iOS"), UnsupportedOSPlatform("Android6.0")]`.</span></span>
  - <span data-ttu-id="5477b-135">Das Analysetool generiert nur dann eine **Warnung**, wenn `platform` für den gesamten Aufrufort gilt:</span><span class="sxs-lookup"><span data-stu-id="5477b-135">The analyzer produces a **warning** only if the `platform` is effective for the call site:</span></span>
    - <span data-ttu-id="5477b-136">**Warnung**, wenn das Projekt auf die Plattform ausgerichtet ist, die laut Attribut nicht unterstützt wird (z. B. bei einer mit `[UnsupportedOSPlatform("windows")]` attributierten API, wenn der Aufrufort auf `<TargetFramework>net5.0-windows</TargetFramework>` abzielt)</span><span class="sxs-lookup"><span data-stu-id="5477b-136">**Warns** if the project targets the platform that's attributed as unsupported (for example, if the API is attributed with `[UnsupportedOSPlatform("windows")]` and the call site targets `<TargetFramework>net5.0-windows</TargetFramework>`).</span></span>
    - <span data-ttu-id="5477b-137">**Warnung**, wenn das Projekt auf mehrere Frameworks abzielt und `platform` in der Standardelementgruppe [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) enthalten ist oder manuell in die Elementgruppe `MSBuild` \<SupportedPlatform> eingefügt wird:</span><span class="sxs-lookup"><span data-stu-id="5477b-137">**Warns** if the project is multi-targeted and the `platform` is included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group, or the `platform` is manually included within the `MSBuild` \<SupportedPlatform> items group:</span></span>

      ```XML
      <ItemGroup>
          <SupportedPlatform Include="platform" />
      </ItemGroup>
      ```

    - <span data-ttu-id="5477b-138">**Keine Warnung**, wenn Sie eine App erstellen, die nicht auf die nicht unterstützte Plattform oder mehrere Zielplattform ausgerichtet ist, und die Plattform nicht in der Standardelementgruppe [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) enthalten ist</span><span class="sxs-lookup"><span data-stu-id="5477b-138">**Doesn't warn** if you're building an app that doesn't target the unsupported platform or is multi-targeted and the platform is not included in the default [MSBuild `<SupportedPlatform>`](https://github.com/dotnet/sdk/blob/master/src/Tasks/Microsoft.NET.Build.Tasks/targets/Microsoft.NET.SupportedPlatforms.props) items group.</span></span>
- <span data-ttu-id="5477b-139">Beide Attribute können mit oder ohne Versionsnummern als Teil des Plattformnamens instanziiert werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-139">Both attributes can be instantiated with or without version numbers as part of the platform name.</span></span>
  - <span data-ttu-id="5477b-140">Versionsnummern weisen das Format `major.minor[.build[.revision]]` auf. `major.minor` ist erforderlich, die Teile `build` und `revision` sind optional.</span><span class="sxs-lookup"><span data-stu-id="5477b-140">Version numbers are in the format of `major.minor[.build[.revision]]`; `major.minor` is required and the `build` and `revision` parts are optional.</span></span> <span data-ttu-id="5477b-141">„Windows7.0“ gibt z. B. die Windows-Version 7.0 an, „Windows“ wird jedoch wie „Windows 0.0“ interpretiert.</span><span class="sxs-lookup"><span data-stu-id="5477b-141">For example, "Windows7.0" indicates Windows version 7.0, but "Windows" is interpreted as Windows 0.0.</span></span>

<span data-ttu-id="5477b-142">Weitere Informationen finden Sie unter [Beispiele für die Funktionsweise von Attributen und ihre Diagnosen](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span><span class="sxs-lookup"><span data-stu-id="5477b-142">For more information, see [examples of how the attributes work and what diagnostics they cause](#examples-of-how-the-attributes-work-and-what-diagnostics-they-produce).</span></span>

### <a name="advanced-scenarios-for-combining-attributes"></a><span data-ttu-id="5477b-143">Erweiterte Szenarios für die Kombination von Attributen</span><span class="sxs-lookup"><span data-stu-id="5477b-143">Advanced scenarios for combining attributes</span></span>

- <span data-ttu-id="5477b-144">Wenn eine Kombination der Attribute `[SupportedOSPlatform]` und `[UnsupportedOSPlatform]` vorliegt, werden alle Attribute nach dem Bezeichner der Betriebssystemplattform gruppiert:</span><span class="sxs-lookup"><span data-stu-id="5477b-144">If a combination of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are present, all attributes are grouped by OS platform identifier:</span></span>
  - <span data-ttu-id="5477b-145">**Liste mit ausschließlich unterstützten Plattformen:**</span><span class="sxs-lookup"><span data-stu-id="5477b-145">**Supported only list**.</span></span> <span data-ttu-id="5477b-146">Wenn die niedrigste Version jeder Betriebssystemplattform das Attribut `[SupportedOSPlatform]` aufweist, gilt die API als nur von den aufgelisteten Plattformen unterstützt und für alle anderen Plattformen als nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5477b-146">If the lowest version for each OS platform is a `[SupportedOSPlatform]` attribute, the API is considered to only be supported by the listed platforms and unsupported by all other platforms.</span></span> <span data-ttu-id="5477b-147">Die optionalen `[UnsupportedOSPlatform]`-Attribute für die einzelnen Plattform können nur eine höhere Version der unterstützten Mindestversion aufweisen, was bedeutet, dass die API-Unterstützung ab der angegebenen Version entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="5477b-147">The optional `[UnsupportedOSPlatform]` attributes for each platform can only have higher version of the minimum supported version, which denotes that the API is removed starting from the specified version.</span></span>

    ```csharp
    // The API only supported on Windows 8.0 and later, not supported for all other.
    // The API is removed/unsupported from version 10.0.19041.0.
    [SupportedOSPlatform("windows8.0")]
    [UnsupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows80SupportFromCertainVersion();
    ```

  - <span data-ttu-id="5477b-148">**Liste mit ausschließlich nicht unterstützten Plattformen:**</span><span class="sxs-lookup"><span data-stu-id="5477b-148">**Unsupported only list**.</span></span> <span data-ttu-id="5477b-149">Wenn die niedrigste Version jeder Betriebssystemplattform das Attribut `[UnsupportedOSPlatform]` aufweist, gilt die API als nur von den aufgelisteten Plattformen nicht unterstützt und für alle anderen Plattformen als unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5477b-149">If the lowest version for each OS platform is an `[UnsupportedOSPlatform]` attribute, then the API is considered to only be unsupported by the listed platforms and supported by all other platforms.</span></span> <span data-ttu-id="5477b-150">Die Liste kann das Attribut `[SupportedOSPlatform]` für die gleiche Plattform, aber eine höhere Version aufweisen, was bedeutet, dass die API ab dieser Version unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5477b-150">The list could have `[SupportedOSPlatform]` attribute with the same platform but a higher version, which denotes that the API is supported starting from that version.</span></span>

    ```csharp
    // The API was unsupported on Windows until version 10.0.19041.0.
    // The API is considered supported everywhere else without constraints.
    [UnsupportedOSPlatform("windows")]
    [SupportedOSPlatform("windows10.0.19041.0")]
    public void ApiSupportedFromWindows8UnsupportFromWindows10();
    ```

  - <span data-ttu-id="5477b-151">**Inkonsistente Liste:**</span><span class="sxs-lookup"><span data-stu-id="5477b-151">**Inconsistent list**.</span></span> <span data-ttu-id="5477b-152">Wenn die niedrigste Version für einige Plattformen `[SupportedOSPlatform]`, für andere Plattformen jedoch `[UnsupportedOSPlatform]` ist, wird die Liste als inkonsistent eingestuft. Dies wird vom Analysetool nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5477b-152">If the lowest version for some platforms is `[SupportedOSPlatform]` while it is `[UnsupportedOSPlatform]` for other platforms, it's considered to be inconsistent, which is not supported for the analyzer.</span></span>
  - <span data-ttu-id="5477b-153">Wenn die niedrigsten Versionen der Attribute `[SupportedOSPlatform]` und `[UnsupportedOSPlatform]` gleich sind, gilt die Plattform für das Analysetool als Teil der **Liste mit ausschließlich unterstützten Plattformen**.</span><span class="sxs-lookup"><span data-stu-id="5477b-153">If the lowest versions of `[SupportedOSPlatform]` and `[UnsupportedOSPlatform]` attributes are equal, the analyzer considers the platform as part of the **Supported only list**.</span></span>
- <span data-ttu-id="5477b-154">Plattformattribute können auf Typen, Member (Methoden, Felder, Eigenschaften und Ereignisse) und Assemblys mit einem anderen Plattformnamen oder einer anderen Version angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-154">Platform attributes can be applied to types, members (methods, fields, properties, and events) and assemblies with different platform names or versions.</span></span>
  - <span data-ttu-id="5477b-155">Attribute, die auf das oberste Ziel (`target`) angewendet werden, gelten infolge auch für alle Member und Typen.</span><span class="sxs-lookup"><span data-stu-id="5477b-155">Attributes applied at the top level `target` affect all of its members and types.</span></span>
  - <span data-ttu-id="5477b-156">Untergeordnete Attribute gelten nur, wenn sie die Regel „Untergeordnete Attribute können die Plattformunterstützung nur einschränken, nicht erweitern“ befolgen.</span><span class="sxs-lookup"><span data-stu-id="5477b-156">Child-level attributes only apply if they adhere to the rule "child annotations can narrow the platforms support, but they cannot widen it".</span></span>
    - <span data-ttu-id="5477b-157">Wenn das übergeordnete Element eine **Liste mit ausschließlich unterstützten Plattformen** aufweist, können die untergeordneten Memberattribute keine neue Plattformunterstützung hinzufügen, da dies die Unterstützung für das übergeordnete Element erweitern würde.</span><span class="sxs-lookup"><span data-stu-id="5477b-157">When parent has **Supported only** list, then child member attributes cannot add a new platform support, as that would be extending parent support.</span></span> <span data-ttu-id="5477b-158">Neue Plattformunterstützung kann nur dem übergeordneten Element selbst hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-158">Support for a new platform can only be added to the parent itself.</span></span> <span data-ttu-id="5477b-159">Das untergeordnete Element kann jedoch das Attribut `Supported` für dieselbe Plattform mit höheren Versionen aufweisen, da dies die Unterstützung einschränkt.</span><span class="sxs-lookup"><span data-stu-id="5477b-159">But the child can have the `Supported` attribute for the same platform with later versions as that narrows the support.</span></span> <span data-ttu-id="5477b-160">Ebenso kann das untergeordnete Element das `Unsupported`-Attribut mit derselben Plattform aufweisen, da dies die übergeordnete Unterstützung ebenfalls einschränkt.</span><span class="sxs-lookup"><span data-stu-id="5477b-160">Also, the child can have the `Unsupported` attribute with the same platform as that also narrows parent support.</span></span>
    - <span data-ttu-id="5477b-161">Wenn das übergeordnete Element eine **Liste mit ausschließlich nicht unterstützten Plattformen** aufweist, können die untergeordneten Memberattribute Unterstützung für eine neue Plattform hinzufügen, da dies die übergeordnete Unterstützung einschränkt.</span><span class="sxs-lookup"><span data-stu-id="5477b-161">When parent has **Unsupported only** list, then child member attributes can add support for a new platform, as that narrows parent support.</span></span> <span data-ttu-id="5477b-162">Es kann jedoch nicht über das `Supported`-Attribut für dieselbe Plattform wie das übergeordnete Element verfügen, da dies die übergeordnete Unterstützung erweitert.</span><span class="sxs-lookup"><span data-stu-id="5477b-162">But it cannot have the `Supported` attribute for the same platform as the parent, because that extends parent support.</span></span> <span data-ttu-id="5477b-163">Unterstützung für dieselbe Plattform kann dem übergeordneten Element nur in den Fällen hinzugefügt werden, in denen das ursprüngliche `Unsupported`-Attribut angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5477b-163">Support for the same platform can only be added to the parent where the original `Unsupported` attribute was applied.</span></span>
  - <span data-ttu-id="5477b-164">Wenn `[SupportedOSPlatform("platformVersion")]` mehr als einmal auf eine API mit demselben `platform`-Namen angewendet wird, wird nur diejenige mit der Mindestversion vom Analysetool berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5477b-164">If `[SupportedOSPlatform("platformVersion")]` is applied more than once for an API with the same `platform` name, the analyzer only considers the one with the minimum version.</span></span>
  - <span data-ttu-id="5477b-165">Wenn `[UnsupportedOSPlatform("platformVersion")]` mehr als zweimal auf eine API mit demselben `platform`-Namen angewendet wird, werden nur die beiden mit den frühesten Versionen vom Analysetool berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5477b-165">If `[UnsupportedOSPlatform("platformVersion")]` is applied more than twice for an API with the same `platform` name, the analyzer only considers the two with the earliest versions.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5477b-166">Wenn die Unterstützung für eine API zunächst vorhanden war und in einer höheren Version abgeschafft wurde, wird sie erwartungsgemäß in einer noch höheren Version nicht wieder eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5477b-166">An API that was supported initially but unsupported (removed) in a later version is not expected to get resupported in an even later version.</span></span>

### <a name="examples-of-how-the-attributes-work-and-what-diagnostics-they-produce"></a><span data-ttu-id="5477b-167">Beispiele für die Funktionsweise von Attributen und ihre Diagnosen</span><span class="sxs-lookup"><span data-stu-id="5477b-167">Examples of how the attributes work and what diagnostics they produce</span></span>

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

## <a name="handle-reported-warnings"></a><span data-ttu-id="5477b-168">Verarbeiten gemeldeter Warnungen</span><span class="sxs-lookup"><span data-stu-id="5477b-168">Handle reported warnings</span></span>

<span data-ttu-id="5477b-169">Die empfohlene Umgangsweise mit diesen Diagnosen besteht darin, sicherzustellen, dass plattformspezifische APIs nur auf der passenden Plattform aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-169">The recommended way to deal with these diagnostics is to make sure you only call platform-specific APIs when running on an appropriate platform.</span></span> <span data-ttu-id="5477b-170">Nachstehend sind Ihre Optionen für die Behebung dieser Warnungen aufgeführt. Wählen Sie die Vorgehensweise aus, die sich am besten für Ihre Situation eignet:</span><span class="sxs-lookup"><span data-stu-id="5477b-170">Following are the options you can use to address the warnings; choose whichever is most appropriate for your situation:</span></span>

- <span data-ttu-id="5477b-171">**Schützen des Aufrufs:**</span><span class="sxs-lookup"><span data-stu-id="5477b-171">**Guard the call**.</span></span> <span data-ttu-id="5477b-172">Zu diesem Zweck können Sie den Code bedingt zur Laufzeit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5477b-172">You can achieve this by conditionally calling the code at run time.</span></span> <span data-ttu-id="5477b-173">Überprüfen Sie, ob die Ausführung auf einer gewünschten `Platform` erfolgt, indem Sie eine der Plattformprüfmethoden verwenden, z. B. `OperatingSystem.Is<Platform>()` oder `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span><span class="sxs-lookup"><span data-stu-id="5477b-173">Check whether you're running on a desired `Platform` by using one of platform-check methods, for example, `OperatingSystem.Is<Platform>()` or `OperatingSystem.Is<Platform>VersionAtLeast(int major, int minor = 0, int build = 0, int revision = 0)`.</span></span>

- <span data-ttu-id="5477b-174">**Markieren des Aufruforts als plattformspezifisch:**</span><span class="sxs-lookup"><span data-stu-id="5477b-174">**Mark the call site as platform-specific**.</span></span> <span data-ttu-id="5477b-175">Sie können auch Ihre eigenen APIs als plattformspezifisch kennzeichnen und die Anforderungen so effektiv an Ihre Aufrufer weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="5477b-175">You can also choose to mark your own APIs as being platform-specific, thus effectively just forwarding the requirements to your callers.</span></span> <span data-ttu-id="5477b-176">Kennzeichnen Sie die enthaltende Methode, den enthaltenden Typ oder die gesamte Assembly mit denselben Attributen wie den referenzierten plattformabhängigen Aufruf.</span><span class="sxs-lookup"><span data-stu-id="5477b-176">Mark the containing method or type or the entire assembly with the same attributes as the referenced platform-dependent call.</span></span> <span data-ttu-id="5477b-177">[Beispiele](#mark-call-site-as-platform-specific).</span><span class="sxs-lookup"><span data-stu-id="5477b-177">[Examples](#mark-call-site-as-platform-specific).</span></span>

- <span data-ttu-id="5477b-178">**Bestätigen des Aufruforts mit einer Plattformüberprüfung:**</span><span class="sxs-lookup"><span data-stu-id="5477b-178">**Assert the call site with platform check**.</span></span> <span data-ttu-id="5477b-179">Wenn Sie den Mehraufwand einer zusätzlichen `if`-Anweisung zur Laufzeit vermeiden möchten, verwenden Sie <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5477b-179">If you don't want the overhead of an additional `if` statement at run time, use <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5477b-180">[Beispiel](#assert-the-call-site-with-platform-check).</span><span class="sxs-lookup"><span data-stu-id="5477b-180">[Example](#assert-the-call-site-with-platform-check).</span></span>

- <span data-ttu-id="5477b-181">**Löschen des Codes:**</span><span class="sxs-lookup"><span data-stu-id="5477b-181">**Delete the code**.</span></span> <span data-ttu-id="5477b-182">Dies ist üblicherweise nicht die gewünschte Vorgehensweise, da Sie möglicherweise Kunden verlieren, wenn Ihr Code von Windows-Benutzern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5477b-182">Generally not what you want because it means you lose fidelity when your code is used by Windows users.</span></span> <span data-ttu-id="5477b-183">Falls eine plattformübergreifende Alternative vorhanden ist, sollten Sie lieber diese anstelle der plattformspezifischen APIs wählen.</span><span class="sxs-lookup"><span data-stu-id="5477b-183">For cases where a cross-platform alternative exists, you're likely better off using that over platform-specific APIs.</span></span>

- <span data-ttu-id="5477b-184">**Unterdrücken der Warnung:**</span><span class="sxs-lookup"><span data-stu-id="5477b-184">**Suppress the warning**.</span></span> <span data-ttu-id="5477b-185">Sie können die Warnung auch einfach unterdrücken, entweder über einen EditorConfig-Eintrag oder über `#pragma warning disable ca1416`.</span><span class="sxs-lookup"><span data-stu-id="5477b-185">You can also simply suppress the warning, either via an EditorConfig entry or `#pragma warning disable ca1416`.</span></span> <span data-ttu-id="5477b-186">Diese Option sollte jedoch bei der Verwendung von plattformspezifischen APIs als allerletzte Maßnahme eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-186">However, this option should be a last resort when using platform-specific APIs.</span></span>

### <a name="guard-platform-specific-apis-with-guard-methods"></a><span data-ttu-id="5477b-187">Schützen von plattformspezifischen APIs mit Schutzmethoden</span><span class="sxs-lookup"><span data-stu-id="5477b-187">Guard platform-specific APIs with guard methods</span></span>

<span data-ttu-id="5477b-188">Der Plattformname der Schutzmethode muss mit dem aufrufenden plattformabhängigen API-Plattformnamen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5477b-188">The guard method's platform name should match with the calling platform-dependent API platform name.</span></span> <span data-ttu-id="5477b-189">Wenn die Plattformzeichenfolge der aufrufenden API die Version enthält:</span><span class="sxs-lookup"><span data-stu-id="5477b-189">If the platform string of the calling API includes the version:</span></span>

- <span data-ttu-id="5477b-190">muss die Plattformversion (`version`) der Schutzmethode für das Attribut `[SupportedOSPlatform("platformVersion")]` größer oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="5477b-190">For the `[SupportedOSPlatform("platformVersion")]` attribute, the guard method platform `version` should be greater than or equal to the calling platform's `Version`.</span></span>
- <span data-ttu-id="5477b-191">muss die Plattformversion (`version`) der Schutzmethode für das Attribut `[UnsupportedOSPlatform("platformVersion")]` kleiner oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="5477b-191">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the guard method's platform `version` should be less than or equal to the calling platform's `Version`.</span></span>

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

- <span data-ttu-id="5477b-192">Wenn Code geschützt werden muss, der auf `netstandard` oder `netcoreapp` ausgerichtet ist, wo keine neuen <xref:System.OperatingSystem>-APIs verfügbar sind, kann die API <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> verwendet werden. Diese wird auch vom Analysetool berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5477b-192">If you need to guard code that targets `netstandard` or `netcoreapp` where new <xref:System.OperatingSystem> APIs are not available, the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform%2A?displayProperty=nameWithType> API can be used and will be respected by the analyzer.</span></span> <span data-ttu-id="5477b-193">Sie ist jedoch nicht so optimiert, wie die neuen APIs, die über <xref:System.OperatingSystem> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-193">But it's not as optimized as the new APIs added in <xref:System.OperatingSystem>.</span></span> <span data-ttu-id="5477b-194">Wenn die Plattform in der <xref:System.Runtime.InteropServices.OSPlatform>-Struktur nicht unterstützt wird, können Sie <xref:System.Runtime.InteropServices.OSPlatform.Create(System.String)?displayProperty=nameWithType> aufrufen und den Plattformnamen übergeben, der vom Analysetool ebenfalls berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="5477b-194">If the platform is not supported in the <xref:System.Runtime.InteropServices.OSPlatform> struct, you can call <xref:System.Runtime.InteropServices.OSPlatform.Create(System.String)?displayProperty=nameWithType> and pass in the platform name, which the analyzer also respects.</span></span>

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

### <a name="mark-call-site-as-platform-specific"></a><span data-ttu-id="5477b-195">Markieren des Aufruforts als plattformspezifisch</span><span class="sxs-lookup"><span data-stu-id="5477b-195">Mark call site as platform-specific</span></span>

<span data-ttu-id="5477b-196">Plattformnamen sollten mit der aufrufenden plattformabhängigen API übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5477b-196">Platform names should match the calling platform-dependent API.</span></span> <span data-ttu-id="5477b-197">Wenn die Plattformzeichenfolge eine Version enthält:</span><span class="sxs-lookup"><span data-stu-id="5477b-197">If the platform string includes a version:</span></span>

- <span data-ttu-id="5477b-198">muss die Plattformversion (`version`) des Aufruforts für das Attribut `[SupportedOSPlatform("platformVersion")]` größer oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="5477b-198">For the `[SupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be greater than or equal to the calling platform's `Version`</span></span>
- <span data-ttu-id="5477b-199">muss die Plattformversion (`version`) des Aufruforts für das Attribut `[UnsupportedOSPlatform("platformVersion")]` kleiner oder gleich der `Version` der aufrufenden Plattform sein</span><span class="sxs-lookup"><span data-stu-id="5477b-199">For the `[UnsupportedOSPlatform("platformVersion")]` attribute, the call site platform `version` should be less than or equal to the calling platform's `Version`</span></span>

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

### <a name="assert-the-call-site-with-platform-check"></a><span data-ttu-id="5477b-200">Bestätigen des Aufruforts mit einer Plattformüberprüfung</span><span class="sxs-lookup"><span data-stu-id="5477b-200">Assert the call-site with platform check</span></span>

<span data-ttu-id="5477b-201">Alle in den [Beispielen für den Plattformschutz](#guard-platform-specific-apis-with-guard-methods) verwendeten bedingten Überprüfungen können auch als Bedingung in <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType> eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5477b-201">All the conditional checks used in the [platform guard examples](#guard-platform-specific-apis-with-guard-methods) can also be used as the condition for <xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType>.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5477b-202">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5477b-202">See also</span></span>

- [<span data-ttu-id="5477b-203">Namen von Zielframeworks in .NET 5</span><span class="sxs-lookup"><span data-stu-id="5477b-203">Target Framework Names in .NET 5</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [<span data-ttu-id="5477b-204">Kommentieren von plattformspezifischen APIs und Erkennen der Verwendung</span><span class="sxs-lookup"><span data-stu-id="5477b-204">Annotating platform-specific APIs and detecting its use</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-checks/platform-checks.md)
- [<span data-ttu-id="5477b-205">Annotieren von APIs als nicht unterstützt auf bestimmten Plattformen</span><span class="sxs-lookup"><span data-stu-id="5477b-205">Annotating APIs as unsupported on specific platforms</span></span>](https://github.com/dotnet/designs/blob/master/accepted/2020/platform-exclusion/platform-exclusion.md)
- [<span data-ttu-id="5477b-206">CA1416: Analysetool für die Plattformkompatibilität</span><span class="sxs-lookup"><span data-stu-id="5477b-206">CA1416 Platform compatibility analyzer</span></span>](../../fundamentals/code-analysis/quality-rules/ca1416.md)
- [<span data-ttu-id="5477b-207">.NET API-Analysetool</span><span class="sxs-lookup"><span data-stu-id="5477b-207">.NET API analyzer</span></span>](../../standard/analyzers/api-analyzer.md)
