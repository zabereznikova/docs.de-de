---
ms.openlocfilehash: 004e2d1883b631e88ab5e164b1120c3b081b7041
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496732"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="194e7-101">ConcurrentQueue&lt;T&gt;.TryPeek kann über einen out-Parameter einen fehlerhaften NULL-Wert zurückgeben</span><span class="sxs-lookup"><span data-stu-id="194e7-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="194e7-102">Details</span><span class="sxs-lookup"><span data-stu-id="194e7-102">Details</span></span>

<span data-ttu-id="194e7-103">In einigen Multithreaded-Szenarien kann <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> „true“ zurückgeben, aber den Out-Parameter mit einem Nullwert füllen (anstelle des richtigen Werts).</span><span class="sxs-lookup"><span data-stu-id="194e7-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="194e7-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="194e7-104">Suggestion</span></span>

<span data-ttu-id="194e7-105">Dieses Problem wurde in .NET Framework 4.5.1 behoben.</span><span class="sxs-lookup"><span data-stu-id="194e7-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="194e7-106">Dieses Problem wird durch ein Upgrade auf diese .NET Framework-Version behoben.</span><span class="sxs-lookup"><span data-stu-id="194e7-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="194e7-107">name</span><span class="sxs-lookup"><span data-stu-id="194e7-107">Name</span></span>    | <span data-ttu-id="194e7-108">Wert</span><span class="sxs-lookup"><span data-stu-id="194e7-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="194e7-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="194e7-109">Scope</span></span>   |<span data-ttu-id="194e7-110">Hauptversion</span><span class="sxs-lookup"><span data-stu-id="194e7-110">Major</span></span>|
|<span data-ttu-id="194e7-111">Version</span><span class="sxs-lookup"><span data-stu-id="194e7-111">Version</span></span>|<span data-ttu-id="194e7-112">4.5</span><span class="sxs-lookup"><span data-stu-id="194e7-112">4.5</span></span>|
|<span data-ttu-id="194e7-113">Typ</span><span class="sxs-lookup"><span data-stu-id="194e7-113">Type</span></span>|<span data-ttu-id="194e7-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="194e7-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="194e7-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="194e7-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.ConcurrentQueue`1.TryPeek(`0@)``

-->
