---
ms.openlocfilehash: a8f51dfa1c82e3b166449d2432dfe8a9b96564b9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620201"
---
### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="53100-101">BlockingCollection&lt;T&gt;.TryTakeFromAny löst keine Ausnahmen mehr aus</span><span class="sxs-lookup"><span data-stu-id="53100-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

#### <a name="details"></a><span data-ttu-id="53100-102">Details</span><span class="sxs-lookup"><span data-stu-id="53100-102">Details</span></span>

<span data-ttu-id="53100-103">Wenn eine der Eingabeauflistungen als abgeschlossen markiert ist, gibt <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> nicht länger „-1“ zurück und <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> löst keine Ausnahme mehr aus.</span><span class="sxs-lookup"><span data-stu-id="53100-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="53100-104">Diese Änderung ermöglicht das Verwenden von Auflistungen, wenn eine der Auflistungen entweder leer oder abgeschlossen ist, die andere Auflistung aber weiterhin abrufbare Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="53100-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="53100-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="53100-105">Suggestion</span></span>

<span data-ttu-id="53100-106">Wenn die Rückgabe von „-1“ durch „TryTakeFromAny“ oder das Auslösen einer Ausnahme durch „TakeFromAny“ für solche Situationen zu Ablaufsteuerungszwecken verwendet wurde, in denen eine blockierende Auflistung abgeschlossen wurde, sollte dieser Code jetzt geändert werden, um <code>.Any(b =&gt; b.IsCompleted)</code> zum Erkennen dieser Bedingung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="53100-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>

| <span data-ttu-id="53100-107">name</span><span class="sxs-lookup"><span data-stu-id="53100-107">Name</span></span>    | <span data-ttu-id="53100-108">Wert</span><span class="sxs-lookup"><span data-stu-id="53100-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="53100-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="53100-109">Scope</span></span>   |<span data-ttu-id="53100-110">Gering</span><span class="sxs-lookup"><span data-stu-id="53100-110">Minor</span></span>|
|<span data-ttu-id="53100-111">Version</span><span class="sxs-lookup"><span data-stu-id="53100-111">Version</span></span>|<span data-ttu-id="53100-112">4.5</span><span class="sxs-lookup"><span data-stu-id="53100-112">4.5</span></span>|
|<span data-ttu-id="53100-113">Typ</span><span class="sxs-lookup"><span data-stu-id="53100-113">Type</span></span>|<span data-ttu-id="53100-114">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="53100-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="53100-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="53100-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
