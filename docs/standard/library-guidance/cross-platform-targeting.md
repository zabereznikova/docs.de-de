---
title: Plattformübergreifende Ziele für .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden zum Erstellen von plattformübergreifenden .NET Bibliotheken.
ms.date: 08/12/2019
ms.openlocfilehash: 6309e300861ab286dcaba3256267b3459e6e0d10
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223345"
---
# <a name="cross-platform-targeting"></a><span data-ttu-id="522aa-103">Plattformübergreifende Ziele</span><span class="sxs-lookup"><span data-stu-id="522aa-103">Cross-platform targeting</span></span>

<span data-ttu-id="522aa-104">Modernes .NET unterstützt mehrere Betriebssysteme und Geräte.</span><span class="sxs-lookup"><span data-stu-id="522aa-104">Modern .NET supports multiple operating systems and devices.</span></span> <span data-ttu-id="522aa-105">Es ist wichtig, dass .NET-Open-Source-Bibliotheken so viele Entwickler wie möglich unterstützen, unabhängig davon, ob sie eine in Azure gehostete ASP.NET-Website oder ein .NET-Spiel in Unity erstellen.</span><span class="sxs-lookup"><span data-stu-id="522aa-105">It's important for .NET open-source libraries to support as many developers as possible, whether they're building an ASP.NET website hosted in Azure, or a .NET game in Unity.</span></span>

## <a name="net-standard"></a><span data-ttu-id="522aa-106">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="522aa-106">.NET Standard</span></span>

<span data-ttu-id="522aa-107">.NET Standard ist die beste Möglichkeit, plattformübergreifenden Support zu einer .NET-Bibliothek hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="522aa-107">.NET Standard is the best way to add cross-platform support to a .NET library.</span></span> <span data-ttu-id="522aa-108">[.NET Standard](../net-standard.md) ist eine Spezifikation von .NET-APIs, die für alle .NET-Implementierungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="522aa-108">[.NET Standard](../net-standard.md) is a specification of .NET APIs that are available on all .NET implementations.</span></span> <span data-ttu-id="522aa-109">Wenn Sie Software für .NET Standard entwickeln, können Sie Bibliotheken erstellen, die nur APIs aus einer bestimmten Version von .NET Standard verwenden. Dies bedeutet, dass die Bibliotheken von allen Plattformen verwendet werden können, die diese Version von .NET Standard implementieren.</span><span class="sxs-lookup"><span data-stu-id="522aa-109">Targeting .NET Standard lets you produce libraries that are constrained to use APIs that are in a given version of .NET Standard, which means it's usable by all platforms that implement that version of .NET Standard.</span></span>

<span data-ttu-id="522aa-110">![.NET-Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span><span class="sxs-lookup"><span data-stu-id="522aa-110">![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")</span></span>

<span data-ttu-id="522aa-111">Das Targeting von .NET Standard und die erfolgreiche Kompilierung Ihres Projekts garantieren nicht, dass die Bibliothek auf allen Plattformen erfolgreich läuft:</span><span class="sxs-lookup"><span data-stu-id="522aa-111">Targeting .NET Standard, and successfully compiling your project, doesn't guarantee the library will run successfully on all platforms:</span></span>

1. <span data-ttu-id="522aa-112">Bei plattformspezifischen APIs tritt auf anderen Plattformen ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="522aa-112">Platform-specific APIs will fail on other platforms.</span></span> <span data-ttu-id="522aa-113">Beispielsweise wird <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> unter Windows erfolgreich ausgeführt, gibt jedoch unter anderen Betriebssystemen <xref:System.PlatformNotSupportedException> aus.</span><span class="sxs-lookup"><span data-stu-id="522aa-113">For example, <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> will succeed on Windows and throw <xref:System.PlatformNotSupportedException> when used on any other OS.</span></span>
2. <span data-ttu-id="522aa-114">APIs können sich unterschiedlich verhalten.</span><span class="sxs-lookup"><span data-stu-id="522aa-114">APIs can behave differently.</span></span> <span data-ttu-id="522aa-115">Beispielsweise haben Reflektions-APIs unterschiedliche Leistungsmerkmale, wenn eine Anwendung eine Ahead-of-time-Kompilierung auf iOS oder UWP verwendet.</span><span class="sxs-lookup"><span data-stu-id="522aa-115">For example, reflection APIs have different performance characteristics when an application uses ahead-of-time compilation on iOS or UWP.</span></span>

> [!TIP]
> <span data-ttu-id="522aa-116">Das .NET-Team [bietet ein Roslyn-Analysetool](../analyzers/api-analyzer.md) zur Erkennung möglicher Probleme.</span><span class="sxs-lookup"><span data-stu-id="522aa-116">The .NET team [offers a Roslyn analyzer](../analyzers/api-analyzer.md) to help you discover possible issues.</span></span>

<span data-ttu-id="522aa-117">✔️ Beginnen Sie, indem Sie ein `netstandard2.0`-Ziel einschließen.</span><span class="sxs-lookup"><span data-stu-id="522aa-117">✔️ DO start with including a `netstandard2.0` target.</span></span>

> <span data-ttu-id="522aa-118">Die meisten Bibliotheken für allgemeine Zwecke sollte außerhalb von .NET Standard 2.0 keine APIs erfordern.</span><span class="sxs-lookup"><span data-stu-id="522aa-118">Most general-purpose libraries should not need APIs outside of .NET Standard 2.0.</span></span> <span data-ttu-id="522aa-119">.NET Standard 2.0 wird von allen modernen Plattformen unterstützt und ist der empfohlene Weg, um mehrere Plattformen mit einem Ziel zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="522aa-119">.NET Standard 2.0 is supported by all modern platforms and is the recommended way to support multiple platforms with one target.</span></span>

<span data-ttu-id="522aa-120">❌ Vermeiden Sie es, ein `netstandard1.x`-Ziel einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="522aa-120">❌ AVOID including a `netstandard1.x` target.</span></span>

> <span data-ttu-id="522aa-121">.NET Standard 1.x wird als ein granularer Satz von NuGet-Paketen verteilt, der ein großes Abhängigkeitsdiagramm erstellt und dazu führt, dass Entwickler beim Erstellen viele Pakete herunterladen.</span><span class="sxs-lookup"><span data-stu-id="522aa-121">.NET Standard 1.x is distributed as a granular set of NuGet packages, which creates a large package dependency graph and results in developers downloading a lot of packages when building.</span></span> <span data-ttu-id="522aa-122">Moderne .NET-Plattformen, einschließlich .NET Framework 4.6.1, UWP und Xamarin unterstützen .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="522aa-122">Modern .NET platforms, including .NET Framework 4.6.1, UWP and Xamarin, all support .NET Standard 2.0.</span></span> <span data-ttu-id="522aa-123">Sie sollten.NET Standard 1.x nur dann als Ziel verwenden, wenn Sie speziell auf eine ältere Plattform abzielen müssen.</span><span class="sxs-lookup"><span data-stu-id="522aa-123">You should only target .NET Standard 1.x if you specifically need to target an older platform.</span></span>

<span data-ttu-id="522aa-124">✔️ Schließen Sie ein `netstandard2.0`-Ziel ein, wenn Sie ein `netstandard1.x`-Ziel benötigen.</span><span class="sxs-lookup"><span data-stu-id="522aa-124">✔️ DO include a `netstandard2.0` target if you require a `netstandard1.x` target.</span></span>

> <span data-ttu-id="522aa-125">Alle Plattformen, die .NET Standard 2.0 unterstützen, verwenden das `netstandard2.0`-Ziel und profitieren von einem kleineren Paketdiagramm, während ältere Plattformen noch funktionieren und auf die Verwendung des `netstandard1.x`-Ziels zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="522aa-125">All platforms supporting .NET Standard 2.0 will use the `netstandard2.0` target and benefit from having a smaller package graph while older platforms will still work and fall back to using the `netstandard1.x` target.</span></span>

<span data-ttu-id="522aa-126">❌ Fügen Sie kein .NET Standard-Ziel ein, wenn die Bibliothek auf einem plattformspezifischen App-Modell basiert.</span><span class="sxs-lookup"><span data-stu-id="522aa-126">❌ DO NOT include a .NET Standard target if the library relies on a platform-specific app model.</span></span>

> <span data-ttu-id="522aa-127">Beispielsweise hängt eine Bibliothek eines UWP-Steuerelemente-Toolkit von einem Appmodell ab, das nur in UWP verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="522aa-127">For example, a UWP control toolkit library depends on an app model that is only available on UWP.</span></span> <span data-ttu-id="522aa-128">Appmodell-spezifische APIs sind nicht in .NET Standard verfügbar.</span><span class="sxs-lookup"><span data-stu-id="522aa-128">App model specific APIs will not be available in .NET Standard.</span></span>

## <a name="multi-targeting"></a><span data-ttu-id="522aa-129">Festlegung von Zielversionen</span><span class="sxs-lookup"><span data-stu-id="522aa-129">Multi-targeting</span></span>

<span data-ttu-id="522aa-130">Manchmal müssen über Ihre Bibliotheken auf Framework-spezifische APIs zugreifen.</span><span class="sxs-lookup"><span data-stu-id="522aa-130">Sometimes you need to access framework-specific APIs from your libraries.</span></span> <span data-ttu-id="522aa-131">Der beste Weg, Framework-spezifische APIs aufzurufen, ist die Verwendung der Festlegung von Zielversionen, das Ihr Projekt für viele [.NET-Zielframeworks](../frameworks.md) und nicht nur für eines erstellt.</span><span class="sxs-lookup"><span data-stu-id="522aa-131">The best way to call framework-specific APIs is using multi-targeting, which builds your project for many [.NET target frameworks](../frameworks.md) rather than for just one.</span></span>

<span data-ttu-id="522aa-132">Um Ihre Kunden davor zu schützen, Bibliotheken für einzelne Frameworks erstellen zu müssen, sollten Sie eine .NET Standard-Ausgabe sowie eine oder mehrere Framework-spezifische Ausgaben anstreben.</span><span class="sxs-lookup"><span data-stu-id="522aa-132">To shield your consumers from having to build for individual frameworks, you should strive to have a .NET Standard output plus one or more framework-specific outputs.</span></span> <span data-ttu-id="522aa-133">Bei der Festlegung von Zielversionen werden alle Assemblys in einem einzigen NuGet-Paket verpackt.</span><span class="sxs-lookup"><span data-stu-id="522aa-133">With multi-targeting, all assemblies are packaged inside a single NuGet package.</span></span> <span data-ttu-id="522aa-134">Die Benutzer können dann auf das gleiche Paket zurückgreifen, und NuGet wählt die passende Implementierung aus.</span><span class="sxs-lookup"><span data-stu-id="522aa-134">Consumers can then reference the same package and NuGet will pick the appropriate implementation.</span></span> <span data-ttu-id="522aa-135">Ihre .NET Standard-Bibliothek dient als Fallbackbibliothek, die überall verwendet wird, mit Ausnahme der Fälle, in denen Ihr NuGet-Paket eine Framework-spezifische Implementierung bietet.</span><span class="sxs-lookup"><span data-stu-id="522aa-135">Your .NET Standard library serves as the fallback library that is used everywhere, except for the cases where your NuGet package offers a framework-specific implementation.</span></span> <span data-ttu-id="522aa-136">Die Festlegung von Zielversionen ermöglicht es Ihnen, die bedingte Kompilierung in Ihrem Code zu verwenden und Framework-spezifische APIs aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="522aa-136">Multi-targeting allows you to use conditional compilation in your code and call framework-specific APIs.</span></span>

<span data-ttu-id="522aa-137">![NuGet-Paket mit mehreren Assemblys](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet-Paket mit mehreren Assemblys")</span><span class="sxs-lookup"><span data-stu-id="522aa-137">![NuGet package with multiple assemblies](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet package with multiple assemblies")</span></span>

<span data-ttu-id="522aa-138">✔️ Erwägen Sie das Targeting von .NET-Implementierungen zusätzlich zu .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="522aa-138">✔️ CONSIDER targeting .NET implementations in addition to .NET Standard.</span></span>

> <span data-ttu-id="522aa-139">Das Targeting von .NET-Implementierungen ermöglichen es Ihnen, plattformspezifische APIs aufzurufen, die sich außerhalb von .NET-Standard befinden.</span><span class="sxs-lookup"><span data-stu-id="522aa-139">Targeting .NET implementations allows you to call platform-specific APIs that are outside of .NET Standard.</span></span>
>
> <span data-ttu-id="522aa-140">Dabei muss weiterhin der Support für .NET Standard gewährleistet sein.</span><span class="sxs-lookup"><span data-stu-id="522aa-140">Do not drop support for .NET Standard when you do this.</span></span> <span data-ttu-id="522aa-141">Lösen Sie sich stattdessen von der Implementierung und bieten Sie Funktions-APIs.</span><span class="sxs-lookup"><span data-stu-id="522aa-141">Instead, throw from the implementation and offer capability APIs.</span></span> <span data-ttu-id="522aa-142">Auf diese Weise kann Ihre Bibliothek überall verwendet werden und unterstützt die Runtimehervorhebung von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="522aa-142">This way, your library can be used anywhere and supports runtime light-up of features.</span></span>

```csharp
public static class GpsLocation
{
    // This project uses multi-targeting to expose device-specific APIs to .NET Standard.
    public static async Task<(double latitude, double longitude)> GetCoordinatesAsync()
    {
#if NET461
        return CallDotNetFramworkApi();
#elif WINDOWS_UWP
        return CallUwpApi();
#else
        throw new PlatformNotSupportedException();
#endif
    }

    // Allows callers to check without having to catch PlatformNotSupportedException
    // or replicating the OS check.
    public static bool IsSupported
    {
        get
        {
#if NET461 || WINDOWS_UWP
            return true;
#else
            return false;
#endif
        }
    }
}
```

<span data-ttu-id="522aa-143">❌ Vermeiden Sie das Festlegen von mehreren Zielen sowie das Verwenden von .NET Standard als Ziel, wenn Ihr Quellcode für alle Ziele identisch ist.</span><span class="sxs-lookup"><span data-stu-id="522aa-143">❌ AVOID multi-targeting as well as targeting .NET Standard, if your source code is the same for all targets.</span></span>

> <span data-ttu-id="522aa-144">Die .NET Standard-Assembly wird von NuGet automatisch verwendet.</span><span class="sxs-lookup"><span data-stu-id="522aa-144">The .NET Standard assembly will automatically be used by NuGet.</span></span> <span data-ttu-id="522aa-145">Das Targeting einzelner .NET-Implementierungen erhöht die `*.nupkg`-Größe, ohne dass sich daraus Vorteil ergeben.</span><span class="sxs-lookup"><span data-stu-id="522aa-145">Targeting individual .NET implementations increases the `*.nupkg` size for no benefit.</span></span>

<span data-ttu-id="522aa-146">✔️ Erwägen Sie, ein Ziel für `net461` hinzuzufügen, wenn Sie ein `netstandard2.0`-Ziel anbieten.</span><span class="sxs-lookup"><span data-stu-id="522aa-146">✔️ CONSIDER adding a target for `net461` when you're offering a `netstandard2.0` target.</span></span>

> <span data-ttu-id="522aa-147">Bei der Verwendung von .NET Standard 2.0 aus .NET Framework gibt es einige Probleme, die in .NET Framework 4.7.2 behoben wurden.</span><span class="sxs-lookup"><span data-stu-id="522aa-147">Using .NET Standard 2.0 from .NET Framework has some issues that were addressed in .NET Framework 4.7.2.</span></span> <span data-ttu-id="522aa-148">Sie können das Erlebnis für Entwickler, die noch mit .NET Framework 4.6.1 bis 4.7.1 arbeiten, verbessern, indem Sie ihnen eine Binärdatei anbieten, die für .NET Framework 4.6.1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="522aa-148">You can improve the experience for developers that are still on .NET Framework 4.6.1 - 4.7.1 by offering them a binary that is built for .NET Framework 4.6.1.</span></span>

<span data-ttu-id="522aa-149">✔️ DO Verteilen Sie Ihre Bibliothek mithilfe eines NuGet-Pakets.</span><span class="sxs-lookup"><span data-stu-id="522aa-149">✔️ DO distribute your library using a NuGet package.</span></span>

> <span data-ttu-id="522aa-150">NuGet wählt das beste Ziel für den Entwickler aus und schützt ihn davor, die passende Implementierung auswählen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="522aa-150">NuGet will select the best target for the developer and shield them having to pick the appropriate implementation.</span></span>

<span data-ttu-id="522aa-151">✔️ Verwenden Sie bei der Festlegung von Zielversionen die `TargetFrameworks`-Eigenschaft der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="522aa-151">✔️ DO use a project file's `TargetFrameworks` property when multi-targeting.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="522aa-152">✔ Erwägen Sie bei der Festlegung von Zielversionen für UWP und Xamarin die Verwendung von [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras), da es Ihre Projektdatei stark vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="522aa-152">✔️ CONSIDER using [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) when multi-targeting for UWP and Xamarin as it greatly simplifies your project file.</span></span>

## <a name="older-targets"></a><span data-ttu-id="522aa-153">Ältere Ziele</span><span class="sxs-lookup"><span data-stu-id="522aa-153">Older targets</span></span>

<span data-ttu-id="522aa-154">.NET unterstützt die Festlegung von Versionen des .NET Frameworks, die seit langem nicht mehr unterstützt werden, sowie Plattformen, die selten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="522aa-154">.NET supports targeting versions of the .NET Framework that are long out of support as well as platforms that are no longer commonly used.</span></span> <span data-ttu-id="522aa-155">Es ist zwar sinnvoll, Ihre Bibliothek mit so vielen Zielen wie möglich arbeiten zu lassen, aber die Notwendigkeit, fehlende APIs zu umgehen, kann zu einem erheblichen Aufwand führen.</span><span class="sxs-lookup"><span data-stu-id="522aa-155">While there's value in making your library work on as many targets as possible, having to work around missing APIs can add significant overhead.</span></span> <span data-ttu-id="522aa-156">Wir glauben, dass bestimmte Frameworks angesichts ihrer Reichweite und Grenzen nicht mehr als Ziel genutzt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="522aa-156">We believe certain frameworks are no longer worth targeting, considering their reach and limitations.</span></span>

<span data-ttu-id="522aa-157">❌ Schließen Sie keine portable Klassenbibliothek (PCL) als Ziel ein.</span><span class="sxs-lookup"><span data-stu-id="522aa-157">❌ DO NOT include a Portable Class Library (PCL) target.</span></span> <span data-ttu-id="522aa-158">Beispiel: `portable-net45+win8+wpa81+wp8`.</span><span class="sxs-lookup"><span data-stu-id="522aa-158">For example, `portable-net45+win8+wpa81+wp8`.</span></span>

> <span data-ttu-id="522aa-159">.NET Standard ist die moderne Möglichkeit, um plattformübergreifende .NET-Bibliotheken zu unterstützen und ist der Ersatz für PCLs.</span><span class="sxs-lookup"><span data-stu-id="522aa-159">.NET Standard is the modern way to support cross-platform .NET libraries and replaces PCLs.</span></span>

<span data-ttu-id="522aa-160">❌ Schließen Sie keine Ziele für .NET-Plattformen ein, die nicht mehr unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="522aa-160">❌ DO NOT include targets for .NET platforms that are no longer supported.</span></span> <span data-ttu-id="522aa-161">Platzhalter in einer derartigen Schreibweise sind z.B. `SL4` und `WP`.</span><span class="sxs-lookup"><span data-stu-id="522aa-161">For example, `SL4`, `WP`.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="522aa-162">[Zurück](get-started.md)
>[Weiter](strong-naming.md)</span><span class="sxs-lookup"><span data-stu-id="522aa-162">[Previous](get-started.md)
[Next](strong-naming.md)</span></span>
