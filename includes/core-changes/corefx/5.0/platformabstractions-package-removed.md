---
ms.openlocfilehash: a635e2ed6a735b5234c92fd8f5ffa1685fe9373e
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558175"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="906d9-101">Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt</span><span class="sxs-lookup"><span data-stu-id="906d9-101">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="906d9-102">Es werden keine neuen Versionen des [Microsoft.DotNet.PlatformAbstractions-Pakets](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) erzeugt.</span><span class="sxs-lookup"><span data-stu-id="906d9-102">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

#### <a name="change-description"></a><span data-ttu-id="906d9-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="906d9-103">Change description</span></span>

<span data-ttu-id="906d9-104">Zuvor wurden neue Versionen der <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek zusammen mit neuen Versionen von .NET Core erstellt.</span><span class="sxs-lookup"><span data-stu-id="906d9-104">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="906d9-105">In Zukunft werden der Bibliothek keine neuen Funktionen hinzugefügt, und es werden keine neuen Hauptversionen mehr veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="906d9-105">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="906d9-106">Vorhandene Versionen der Bibliothek funktionieren jedoch weiterhin und werden gewartet.</span><span class="sxs-lookup"><span data-stu-id="906d9-106">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="906d9-107">Die <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek überschneidet sich mit APIs, die bereits in den System.\*-APIs eingerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="906d9-107">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="906d9-108">Außerdem werden einige <xref:Microsoft.DotNet.PlatformAbstractions>-APIs nicht mit dem gleichen Maß an Genauigkeit und langfristiger Unterstützbarkeit wie der Rest des Systems\* entworfen. APIs.</span><span class="sxs-lookup"><span data-stu-id="906d9-108">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="906d9-109"><xref:Microsoft.DotNet.PlatformAbstractions> verwendet beispielsweise die `Platform`-Enumeration, um die aktuelle Betriebssystemplattform zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="906d9-109">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="906d9-110">Dieser Enumerationsentwurf wurde explizit abgelehnt, als die <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType>-API entworfen wurde, um neue Plattformen und zukünftige Flexibilität zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="906d9-110">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="906d9-111">Die von der <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek aktivierten Szenarios sind jetzt ohne sie möglich.</span><span class="sxs-lookup"><span data-stu-id="906d9-111">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="906d9-112">Vorhandene Versionen funktionieren weiterhin, auch in .NET 5.0 und später, und werden zusammen mit früheren Versionen von .NET Core gewartet.</span><span class="sxs-lookup"><span data-stu-id="906d9-112">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="906d9-113">Der Bibliothek werden jedoch keine neuen Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="906d9-113">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="906d9-114">Stattdessen werden anderen Bibliotheken und APIs neue Funktionen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="906d9-114">Instead, new functionality will be added to other libraries and APIs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="906d9-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="906d9-115">Version introduced</span></span>

<span data-ttu-id="906d9-116">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="906d9-116">5.0 Preview 6</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="906d9-117">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="906d9-117">Recommended action</span></span>

- <span data-ttu-id="906d9-118">Sie können weiterhin ältere Versionen der Bibliothek verwenden, wenn diese Ihre Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="906d9-118">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="906d9-119">Wenn die älteren Versionen Ihre Anforderungen nicht erfüllen, ersetzen Sie die Verwendung der `PlatformAbstractions`-APIs durch die empfohlenen Ersetzungen.</span><span class="sxs-lookup"><span data-stu-id="906d9-119">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="906d9-120">`PlatformAbstractions`-API</span><span class="sxs-lookup"><span data-stu-id="906d9-120">`PlatformAbstractions` API</span></span> | <span data-ttu-id="906d9-121">Empfohlener Ersatz</span><span class="sxs-lookup"><span data-stu-id="906d9-121">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="906d9-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> und <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="906d9-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="906d9-123">Die meisten Anwendungsfälle für `RuntimeEnvironment.OperatingSystem` und `RuntimeEnvironment.OperatingSystemVersion` dienen zu Anzeigezwecken, zum Beispiel die Anzeige eines Benutzers, der Protokollierung und der Telemetrie.</span><span class="sxs-lookup"><span data-stu-id="906d9-123">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="906d9-124">Es wird nicht empfohlen, Entscheidungen zur Runtime basierend auf der Betriebssystemversion zu treffen.</span><span class="sxs-lookup"><span data-stu-id="906d9-124">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="906d9-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt nun die [korrekte Version](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version) für die Betriebssysteme Windows und macOS zurück.</span><span class="sxs-lookup"><span data-stu-id="906d9-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now [returns the correct version](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version) for Windows and macOS operating systems.</span></span> <span data-ttu-id="906d9-126">Für die meisten Unix-Distributionen ist das, was man als „Betriebssystemversion“ bezeichnet, nicht ganz so einfach.</span><span class="sxs-lookup"><span data-stu-id="906d9-126">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="906d9-127">Es kann beispielsweise hier die Linux-Kernelversion sein oder die Distributionsversion.</span><span class="sxs-lookup"><span data-stu-id="906d9-127">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="906d9-128">Bei den meisten Unix-Plattformen geben <xref:System.Environment.OSVersion?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> die Version zurück, die von `uname` zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="906d9-128">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="906d9-129">Der empfohlene Ansatz zum Abrufen des Linux-Distributionsnamens und der Version ist es, die Datei */etc/os-release* zu lesen.</span><span class="sxs-lookup"><span data-stu-id="906d9-129">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

#### <a name="category"></a><span data-ttu-id="906d9-130">Kategorie</span><span class="sxs-lookup"><span data-stu-id="906d9-130">Category</span></span>

<span data-ttu-id="906d9-131">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="906d9-131">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="906d9-132">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="906d9-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
