---
ms.openlocfilehash: 9131c91b34f4c24653dea37ea39af6be6e072287
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620333"
---
### <a name="enumerableemptylttresultgt-always-returns-cached-instance"></a><span data-ttu-id="cd062-101">Enumerable.Empty&lt;TResult&gt; gibt immer die zwischengespeicherte Instanz zurück</span><span class="sxs-lookup"><span data-stu-id="cd062-101">Enumerable.Empty&lt;TResult&gt; always returns cached instance</span></span>

#### <a name="details"></a><span data-ttu-id="cd062-102">Details</span><span class="sxs-lookup"><span data-stu-id="cd062-102">Details</span></span>

<span data-ttu-id="cd062-103">Ab .NET Framework 4.5 gibt <xref:System.Linq.Enumerable.Empty%60%601> eine zwischengespeicherte interne Instanz von <xref:System.Collections.Generic.IEnumerable%601> zurück. Zuvor zwischenspeicherte <xref:System.Linq.Enumerable.Empty%60%601> beim Aufruf der API eine leere <xref:System.Collections.Generic.IEnumerable%601>-Instanz, wodurch unter bestimmten Umständen, durch die <xref:System.Linq.Enumerable.Empty%60%601> schnell und gleichzeitig aufgerufen wurde, verschiedene Instanzen des Typs für unterschiedliche Aufrufe der API zurückgegeben werden konnten.</span><span class="sxs-lookup"><span data-stu-id="cd062-103">Beginning in .NET Framework 4.5, <xref:System.Linq.Enumerable.Empty%60%601> always returns a cached internal instance <xref:System.Collections.Generic.IEnumerable%601>.Previously, <xref:System.Linq.Enumerable.Empty%60%601> would cache an empty <xref:System.Collections.Generic.IEnumerable%601> at the time the API was called, meaning that in some conditions in which <xref:System.Linq.Enumerable.Empty%60%601> was called rapidly and concurrently, different instances of the type could be returned for different calls to the API.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cd062-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="cd062-104">Suggestion</span></span>

<span data-ttu-id="cd062-105">Da das vorherige Verhalten nicht deterministisch war, ist es unwahrscheinlich, dass der Code davon abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="cd062-105">Because the previous behavior was non-deterministic, code is unlikely to depend on it.</span></span> <span data-ttu-id="cd062-106">Jedoch für den unwahrscheinlichen Fall, dass leere Enumerables verglichen werden und dabei erwartet wird, dass diese gelegentlich ungleich sind, sollten explizite leere Arrays erstellt werden (<code>new T[0]</code>), anstatt <xref:System.Linq.Enumerable.Empty%60%601> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd062-106">However, in the unlikely case that empty enumerables are being compared and expected to sometimes be unequal, explicit empty arrays should be created (<code>new T[0]</code>) instead of using <xref:System.Linq.Enumerable.Empty%60%601>.</span></span>

| <span data-ttu-id="cd062-107">name</span><span class="sxs-lookup"><span data-stu-id="cd062-107">Name</span></span>    | <span data-ttu-id="cd062-108">Wert</span><span class="sxs-lookup"><span data-stu-id="cd062-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cd062-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="cd062-109">Scope</span></span>   |<span data-ttu-id="cd062-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cd062-110">Edge</span></span>|
|<span data-ttu-id="cd062-111">Version</span><span class="sxs-lookup"><span data-stu-id="cd062-111">Version</span></span>|<span data-ttu-id="cd062-112">4.5</span><span class="sxs-lookup"><span data-stu-id="cd062-112">4.5</span></span>|
|<span data-ttu-id="cd062-113">Typ</span><span class="sxs-lookup"><span data-stu-id="cd062-113">Type</span></span>|<span data-ttu-id="cd062-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="cd062-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cd062-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="cd062-115">Affected APIs</span></span>

-<xref:System.Linq.Enumerable.Empty%60%601?displayProperty=nameWithType></li></ul>|
