---
ms.openlocfilehash: 277a91fbfbf0c6aaaa0dc044ef0c079ad8607699
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496938"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="1c05d-101">BlockingCollection&lt;T&gt;.TryTakeFromAny löst keine Ausnahmen mehr aus</span><span class="sxs-lookup"><span data-stu-id="1c05d-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="1c05d-102">Details</span><span class="sxs-lookup"><span data-stu-id="1c05d-102">Details</span></span>

<span data-ttu-id="1c05d-103">Wenn eine der Eingabeauflistungen als abgeschlossen markiert ist, gibt <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> nicht länger „-1“ zurück und <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> löst keine Ausnahme mehr aus.</span><span class="sxs-lookup"><span data-stu-id="1c05d-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="1c05d-104">Diese Änderung ermöglicht das Verwenden von Auflistungen, wenn eine der Auflistungen entweder leer oder abgeschlossen ist, die andere Auflistung aber weiterhin abrufbare Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="1c05d-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1c05d-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1c05d-105">Suggestion</span></span>

<span data-ttu-id="1c05d-106">Wenn die Rückgabe von „-1“ durch „TryTakeFromAny“ oder das Auslösen einer Ausnahme durch „TakeFromAny“ für solche Situationen zu Ablaufsteuerungszwecken verwendet wurde, in denen eine blockierende Auflistung abgeschlossen wurde, sollte dieser Code jetzt geändert werden, um <code>.Any(b =&gt; b.IsCompleted)</code> zum Erkennen dieser Bedingung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c05d-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="1c05d-107">name</span><span class="sxs-lookup"><span data-stu-id="1c05d-107">Name</span></span>    | <span data-ttu-id="1c05d-108">Wert</span><span class="sxs-lookup"><span data-stu-id="1c05d-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1c05d-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="1c05d-109">Scope</span></span>   |<span data-ttu-id="1c05d-110">Gering</span><span class="sxs-lookup"><span data-stu-id="1c05d-110">Minor</span></span>|
|<span data-ttu-id="1c05d-111">Version</span><span class="sxs-lookup"><span data-stu-id="1c05d-111">Version</span></span>|<span data-ttu-id="1c05d-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1c05d-112">4.5</span></span>|
|<span data-ttu-id="1c05d-113">Typ</span><span class="sxs-lookup"><span data-stu-id="1c05d-113">Type</span></span>|<span data-ttu-id="1c05d-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1c05d-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1c05d-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1c05d-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Threading.CancellationToken)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.Int32)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``
- ``M:System.Collections.Concurrent.BlockingCollection`1.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{`0}[],`0@,System.TimeSpan)``

-->
