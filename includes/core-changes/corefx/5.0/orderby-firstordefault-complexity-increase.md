---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137479"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="b143c-101">Die Komplexität von OrderBy.First{OrDefault} in LINQ wurde erhöht</span><span class="sxs-lookup"><span data-stu-id="b143c-101">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="b143c-102">Die Implementierung von <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> und <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> wurde geändert, wodurch die Komplexität des Vorgangs erhöht wurde.</span><span class="sxs-lookup"><span data-stu-id="b143c-102">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b143c-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="b143c-103">Change description</span></span>

<span data-ttu-id="b143c-104">In .NET Core 1.x bis 3.x werden Aufrufe von <xref:System.Linq.Enumerable.OrderBy%2A> oder <xref:System.Linq.Enumerable.OrderByDescending%2A> gefolgt von <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> mit der Komplexität `O(N)` durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b143c-104">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="b143c-105">Da nur das erste Element (oder das Standardelement) erforderlich ist, ist nur eine Enumeration erforderlich, um es zu finden.</span><span class="sxs-lookup"><span data-stu-id="b143c-105">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="b143c-106">Allerdings wird das für <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> bereitgestellte Prädikat genau `N` Mal aufgerufen. Dabei entspricht `N` der Länge der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="b143c-106">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="b143c-107">In .NET 5.0 und höheren Versionen [wurde eine Änderung eingeführt](https://github.com/dotnet/runtime/pull/36643), durch die Aufrufe von <xref:System.Linq.Enumerable.OrderBy%2A> oder <xref:System.Linq.Enumerable.OrderByDescending%2A> gefolgt von <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> mit der Komplexität `O(N log N)` anstelle von `O(N)` durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b143c-107">In .NET 5.0 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="b143c-108">Allerdings kann das für <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> oder <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> bereitgestellte Prädikat *weniger* als `N` Mal aufgerufen werden, was für die Gesamtleistung wichtiger ist.</span><span class="sxs-lookup"><span data-stu-id="b143c-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="b143c-109">Diese Änderung entspricht der Implementierung und Komplexität des Vorgangs im .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b143c-109">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b143c-110">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="b143c-110">Reason for change</span></span>

<span data-ttu-id="b143c-111">Der Vorteil weniger Aufrufe des Prädikats überwiegt geringere Gesamtkomplexität, daher wurde die in .NET Core 1.0 eingeführte Implementierung rückgängig gemacht.</span><span class="sxs-lookup"><span data-stu-id="b143c-111">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="b143c-112">Weitere Informationen finden Sie in [diesem Dotnet-/Runtime-Issue](https://github.com/dotnet/runtime/issues/31554).</span><span class="sxs-lookup"><span data-stu-id="b143c-112">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b143c-113">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="b143c-113">Version introduced</span></span>

<span data-ttu-id="b143c-114">5.0</span><span class="sxs-lookup"><span data-stu-id="b143c-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b143c-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="b143c-115">Recommended action</span></span>

<span data-ttu-id="b143c-116">Der Entwickler muss keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="b143c-116">No action is required on the developer's part.</span></span>

#### <a name="category"></a><span data-ttu-id="b143c-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="b143c-117">Category</span></span>

<span data-ttu-id="b143c-118">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="b143c-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b143c-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b143c-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
