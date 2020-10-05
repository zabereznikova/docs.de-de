---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406146"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="b5049-101">System.Security.Cryptography-APIs werden in Blazor WebAssembly nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b5049-101">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="b5049-102"><xref:System.Security.Cryptography>-APIs lösen zur Laufzeit eine <xref:System.PlatformNotSupportedException> aus, wenn sie in einem Browser ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b5049-102"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b5049-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b5049-103">Change description</span></span>

<span data-ttu-id="b5049-104">In früheren Versionen von .NET waren die meisten <xref:System.Security.Cryptography>-APIs für Blazor WebAssembly-Apps nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b5049-104">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="b5049-105">Ab .NET 5.0 sind Blazor WebAssembly-Apps zwar auf die gesamte API-Oberfläche für .NET 5 ausgerichtet, aber aufgrund von Browsereinschränkungen der Sandbox werden nicht alle .NET 5-APIs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b5049-105">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="b5049-106">In .NET 5.0 und höheren Versionen lösen die nicht unterstützten <xref:System.Security.Cryptography>-APIs eine <xref:System.PlatformNotSupportedException> aus, wenn sie in WebAssembly ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b5049-106">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="b5049-107">Wenn Sie ein Projekt erstellen, das die Browserplattform unterstützt, kennzeichnet das [Analysetool für die Plattformkompatibilität](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) sämtliche Aufrufe der betroffenen APIs.</span><span class="sxs-lookup"><span data-stu-id="b5049-107">The [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="b5049-108">Dieses Analysetool wird standardmäßig in Apps für .NET 5.0 und höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5049-108">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b5049-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b5049-109">Reason for change</span></span>

<span data-ttu-id="b5049-110">Microsoft kann OpenSSL nicht als Abhängigkeit mit der Blazor WebAssembly-Konfiguration integrieren.</span><span class="sxs-lookup"><span data-stu-id="b5049-110">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="b5049-111">Wir haben versucht, dieses Problem zu umgehen, indem wir eine Integration in die API `SubtleCrypto` des Browsers vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="b5049-111">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="b5049-112">Leider waren dafür aber einschlägige API-Änderungen erforderlich, die die Integration zu kompliziert machten.</span><span class="sxs-lookup"><span data-stu-id="b5049-112">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b5049-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b5049-113">Version introduced</span></span>

<span data-ttu-id="b5049-114">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="b5049-114">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b5049-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="b5049-115">Recommended action</span></span>

<span data-ttu-id="b5049-116">Zurzeit gibt es keine gute Möglichkeit, dieses Problem zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="b5049-116">There are no good workarounds to suggest at this time.</span></span>

#### <a name="category"></a><span data-ttu-id="b5049-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b5049-117">Category</span></span>

- <span data-ttu-id="b5049-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b5049-118">ASP.NET Core</span></span>
- <span data-ttu-id="b5049-119">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="b5049-119">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b5049-120">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b5049-120">Affected APIs</span></span>

<span data-ttu-id="b5049-121">Alle <xref:System.Security.Cryptography?displayProperty=fullName>-APIs außer:</span><span class="sxs-lookup"><span data-stu-id="b5049-121">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

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

#### Affected APIs

- `T:System.Security.Cryptography`

-->
