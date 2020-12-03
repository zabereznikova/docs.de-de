---
title: 'Breaking Change: Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, bei dem das Paket „Microsoft.DotNet.PlatformAbstractions“ entfernt wurde.
ms.date: 11/01/2020
ms.openlocfilehash: 38ffe5e592d01c3bae14fc41becb594283b975a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759468"
---
# <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="acdbc-103">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="acdbc-103">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="acdbc-104">Es werden keine neuen Versionen des [Microsoft.DotNet.PlatformAbstractions-Pakets](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) erzeugt.</span><span class="sxs-lookup"><span data-stu-id="acdbc-104">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

## <a name="change-description"></a><span data-ttu-id="acdbc-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="acdbc-105">Change description</span></span>

<span data-ttu-id="acdbc-106">Zuvor wurden neue Versionen der <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek zusammen mit neuen Versionen von .NET Core erstellt.</span><span class="sxs-lookup"><span data-stu-id="acdbc-106">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="acdbc-107">In Zukunft werden der Bibliothek keine neuen Funktionen hinzugefügt, und es werden keine neuen Hauptversionen mehr veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="acdbc-107">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="acdbc-108">Vorhandene Versionen der Bibliothek funktionieren jedoch weiterhin und werden gewartet.</span><span class="sxs-lookup"><span data-stu-id="acdbc-108">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="acdbc-109">Die <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek überschneidet sich mit APIs, die bereits in den System.\*-APIs eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="acdbc-109">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="acdbc-110">Außerdem werden einige <xref:Microsoft.DotNet.PlatformAbstractions>-APIs nicht mit dem gleichen Maß an Genauigkeit und langfristiger Unterstützbarkeit wie der Rest des Systems\* entworfen. APIs.</span><span class="sxs-lookup"><span data-stu-id="acdbc-110">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="acdbc-111"><xref:Microsoft.DotNet.PlatformAbstractions> verwendet beispielsweise die `Platform`-Enumeration, um die aktuelle Betriebssystemplattform zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="acdbc-111">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="acdbc-112">Dieser Enumerationsentwurf wurde explizit abgelehnt, als die <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType>-API entworfen wurde, um neue Plattformen und zukünftige Flexibilität zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="acdbc-112">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="acdbc-113">Die von der <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek aktivierten Szenarios sind jetzt ohne sie möglich.</span><span class="sxs-lookup"><span data-stu-id="acdbc-113">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="acdbc-114">Vorhandene Versionen funktionieren weiterhin, auch in .NET 5.0 und später, und werden zusammen mit früheren Versionen von .NET Core gewartet.</span><span class="sxs-lookup"><span data-stu-id="acdbc-114">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="acdbc-115">Der Bibliothek werden jedoch keine neuen Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="acdbc-115">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="acdbc-116">Stattdessen werden anderen Bibliotheken und APIs neue Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="acdbc-116">Instead, new functionality will be added to other libraries and APIs.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="acdbc-117">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="acdbc-117">Version introduced</span></span>

<span data-ttu-id="acdbc-118">5.0</span><span class="sxs-lookup"><span data-stu-id="acdbc-118">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="acdbc-119">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="acdbc-119">Recommended action</span></span>

- <span data-ttu-id="acdbc-120">Sie können weiterhin ältere Versionen der Bibliothek verwenden, wenn diese Ihre Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="acdbc-120">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="acdbc-121">Wenn die älteren Versionen Ihre Anforderungen nicht erfüllen, ersetzen Sie die Verwendung der `PlatformAbstractions`-APIs durch die empfohlenen Ersetzungen.</span><span class="sxs-lookup"><span data-stu-id="acdbc-121">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="acdbc-122">`PlatformAbstractions`-API</span><span class="sxs-lookup"><span data-stu-id="acdbc-122">`PlatformAbstractions` API</span></span> | <span data-ttu-id="acdbc-123">Empfohlener Ersatz</span><span class="sxs-lookup"><span data-stu-id="acdbc-123">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="acdbc-124"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> und <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="acdbc-124"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="acdbc-125">Die meisten Anwendungsfälle für `RuntimeEnvironment.OperatingSystem` und `RuntimeEnvironment.OperatingSystemVersion` dienen zu Anzeigezwecken, zum Beispiel die Anzeige eines Benutzers, der Protokollierung und der Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="acdbc-125">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="acdbc-126">Es wird nicht empfohlen, Entscheidungen zur Runtime basierend auf der Betriebssystemversion zu treffen.</span><span class="sxs-lookup"><span data-stu-id="acdbc-126">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="acdbc-127"><xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt nun die [korrekte Version](environment-osversion-returns-correct-version.md) für die Betriebssysteme Windows und macOS zurück.</span><span class="sxs-lookup"><span data-stu-id="acdbc-127"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now [returns the correct version](environment-osversion-returns-correct-version.md) for Windows and macOS operating systems.</span></span> <span data-ttu-id="acdbc-128">Für die meisten Unix-Distributionen ist das, was man als „Betriebssystemversion“ bezeichnet, nicht ganz so einfach.</span><span class="sxs-lookup"><span data-stu-id="acdbc-128">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="acdbc-129">Es kann beispielsweise hier die Linux-Kernelversion sein oder die Distributionsversion.</span><span class="sxs-lookup"><span data-stu-id="acdbc-129">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="acdbc-130">Bei den meisten Unix-Plattformen geben <xref:System.Environment.OSVersion?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> die Version zurück, die von `uname` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="acdbc-130">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="acdbc-131">Der empfohlene Ansatz zum Abrufen des Linux-Distributionsnamens und der Version ist es, die Datei */etc/os-release* zu lesen.</span><span class="sxs-lookup"><span data-stu-id="acdbc-131">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="acdbc-132">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="acdbc-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
