---
title: 'Breaking Change: System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Kryptografie-APIs eine Ausnahme auslösen, wenn sie in einem Browser ausgeführt werden.
ms.date: 09/16/2020
ms.openlocfilehash: ec10fa777e91f641b5582378830536a0cfa8dd72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759227"
---
# <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="41f1c-103">System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="41f1c-103">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="41f1c-104"><xref:System.Security.Cryptography>-APIs lösen zur Laufzeit eine <xref:System.PlatformNotSupportedException> aus, wenn sie in einem Browser ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="41f1c-104"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

## <a name="change-description"></a><span data-ttu-id="41f1c-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="41f1c-105">Change description</span></span>

<span data-ttu-id="41f1c-106">In früheren Versionen von .NET waren die meisten <xref:System.Security.Cryptography>-APIs für Blazor WebAssembly-Apps nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41f1c-106">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="41f1c-107">Ab .NET 5.0 sind Blazor WebAssembly-Apps zwar auf die gesamte API-Oberfläche für .NET 5 ausgerichtet, aber aufgrund von Browsereinschränkungen der Sandbox werden nicht alle .NET 5-APIs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41f1c-107">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="41f1c-108">In .NET 5.0 und höheren Versionen lösen die nicht unterstützten <xref:System.Security.Cryptography>-APIs eine <xref:System.PlatformNotSupportedException> aus, wenn sie in WebAssembly ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="41f1c-108">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="41f1c-109">Wenn Sie ein Projekt erstellen, das die Browserplattform unterstützt, kennzeichnet das [Analysetool für die Plattformkompatibilität](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) sämtliche Aufrufe der betroffenen APIs.</span><span class="sxs-lookup"><span data-stu-id="41f1c-109">The [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="41f1c-110">Dieses Analysetool wird standardmäßig in Apps für .NET 5.0 und höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="41f1c-110">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="41f1c-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="41f1c-111">Reason for change</span></span>

<span data-ttu-id="41f1c-112">Microsoft kann OpenSSL nicht als Abhängigkeit mit der Blazor WebAssembly-Konfiguration integrieren.</span><span class="sxs-lookup"><span data-stu-id="41f1c-112">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="41f1c-113">Wir haben versucht, dieses Problem zu umgehen, indem wir eine Integration in die API `SubtleCrypto` des Browsers vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="41f1c-113">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="41f1c-114">Leider waren dafür aber einschlägige API-Änderungen erforderlich, die die Integration zu kompliziert machten.</span><span class="sxs-lookup"><span data-stu-id="41f1c-114">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="41f1c-115">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="41f1c-115">Version introduced</span></span>

<span data-ttu-id="41f1c-116">5.0</span><span class="sxs-lookup"><span data-stu-id="41f1c-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="41f1c-117">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="41f1c-117">Recommended action</span></span>

<span data-ttu-id="41f1c-118">Zurzeit gibt es keine gute Möglichkeit, dieses Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="41f1c-118">There are no good workarounds to suggest at this time.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="41f1c-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="41f1c-119">Affected APIs</span></span>

<span data-ttu-id="41f1c-120">Alle <xref:System.Security.Cryptography?displayProperty=fullName>-APIs außer:</span><span class="sxs-lookup"><span data-stu-id="41f1c-120">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

### Affected APIs

- `T:System.Security.Cryptography`

### Category

- ASP.NET Core
- Cryptography

-->
