---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394339"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a><span data-ttu-id="da4c5-101">Hosting: Typen IHostingEnvironment und IApplicationLifetime wurden als veraltet markiert und ersetzt.</span><span class="sxs-lookup"><span data-stu-id="da4c5-101">Hosting: IHostingEnvironment and IApplicationLifetime types marked obsolete and replaced</span></span>

<span data-ttu-id="da4c5-102">Es wurden neue Typen eingeführt, um die vorhandenen Typen `IHostingEnvironment` und `IApplicationLifetime` zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="da4c5-102">New types have been introduced to replace existing `IHostingEnvironment` and `IApplicationLifetime` types.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="da4c5-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="da4c5-103">Version introduced</span></span>

<span data-ttu-id="da4c5-104">3.0</span><span class="sxs-lookup"><span data-stu-id="da4c5-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="da4c5-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="da4c5-105">Old behavior</span></span>

<span data-ttu-id="da4c5-106">Es gab zwei verschiedene `IHostingEnvironment`- und `IApplicationLifetime`-Typen von `Microsoft.Extensions.Hosting` und `Microsoft.AspNetCore.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="da4c5-106">There were two different `IHostingEnvironment` and `IApplicationLifetime` types from `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="da4c5-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="da4c5-107">New behavior</span></span>

<span data-ttu-id="da4c5-108">Die alten Typen wurden als veraltet markiert und durch neue ersetzt.</span><span class="sxs-lookup"><span data-stu-id="da4c5-108">The old types have been marked as obsolete and replaced with new types.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="da4c5-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="da4c5-109">Reason for change</span></span>

<span data-ttu-id="da4c5-110">Als `Microsoft.Extensions.Hosting` in ASP.NET Core 2.1 eingeführt wurde, wurden einige Typen wie `IHostingEnvironment` und `IApplicationLifetime` aus `Microsoft.AspNetCore.Hosting` kopiert.</span><span class="sxs-lookup"><span data-stu-id="da4c5-110">When `Microsoft.Extensions.Hosting` was introduced in ASP.NET Core 2.1, some types like `IHostingEnvironment` and `IApplicationLifetime` were copied from `Microsoft.AspNetCore.Hosting`.</span></span> <span data-ttu-id="da4c5-111">Einige Änderungen in ASP.NET Core 3.0 führen dazu, dass Apps die beiden Namespaces `Microsoft.Extensions.Hosting` und `Microsoft.AspNetCore.Hosting` enthalten.</span><span class="sxs-lookup"><span data-stu-id="da4c5-111">Some ASP.NET Core 3.0 changes cause apps to include both the `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting` namespaces.</span></span> <span data-ttu-id="da4c5-112">Jede Verwendung dieser doppelten Typen verursacht einen Compilerfehler aufgrund eines mehrdeutigen Verweises, wenn auf beide Namespaces verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="da4c5-112">Any use of those duplicate types causes an "ambiguous reference" compiler error when both namespaces are referenced.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="da4c5-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="da4c5-113">Recommended action</span></span>

<span data-ttu-id="da4c5-114">Ersetzen Sie alle Verwendungen der alten Typen wie unten gezeigt durch die neu eingeführten Typen:</span><span class="sxs-lookup"><span data-stu-id="da4c5-114">Replaced any usages of the old types with the newly introduced types as below:</span></span>

<span data-ttu-id="da4c5-115">**Veraltete Typen (Warnung):**</span><span class="sxs-lookup"><span data-stu-id="da4c5-115">**Obsolete types (warning):**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

<span data-ttu-id="da4c5-116">**Neue Typen:**</span><span class="sxs-lookup"><span data-stu-id="da4c5-116">**New types:**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

<span data-ttu-id="da4c5-117">Die neuen Erweiterungsmethoden `IHostEnvironment`, `IsDevelopment` und `IsProduction` befinden sich im `Microsoft.Extensions.Hosting`-Namespace.</span><span class="sxs-lookup"><span data-stu-id="da4c5-117">The new `IHostEnvironment` `IsDevelopment` and `IsProduction` extension methods are in the `Microsoft.Extensions.Hosting` namespace.</span></span> <span data-ttu-id="da4c5-118">Dieser Namespace muss Ihrem Projekt eventuell hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="da4c5-118">That namespace may need to be added to your project.</span></span>

#### <a name="category"></a><span data-ttu-id="da4c5-119">Kategorie</span><span class="sxs-lookup"><span data-stu-id="da4c5-119">Category</span></span>

<span data-ttu-id="da4c5-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="da4c5-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="da4c5-121">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="da4c5-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
