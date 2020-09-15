---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614455"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="d5c65-101">ETW-Ereignisnamen können sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden</span><span class="sxs-lookup"><span data-stu-id="d5c65-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

#### <a name="details"></a><span data-ttu-id="d5c65-102">Details</span><span class="sxs-lookup"><span data-stu-id="d5c65-102">Details</span></span>

<span data-ttu-id="d5c65-103">In .NET Framework 4.6 und 4.6.1 löst die Runtime <xref:System.ArgumentException> aus, wenn zwei Ereignisnamen der Ereignisablaufverfolgung für Windows (ETW) sich lediglich durch das Suffix „Start“ oder „Stop“ unterscheiden (z. B. wenn ein Ereignis mit `LogUser` benannt ist und das andere mit `LogUserStart`).</span><span class="sxs-lookup"><span data-stu-id="d5c65-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a "Start" or "Stop" suffix (as when one event is named `LogUser` and another is named `LogUserStart`).</span></span> <span data-ttu-id="d5c65-104">In diesem Fall kann die Runtime die Ereignisquelle nicht erstellen, die dann keine Protokollierung durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="d5c65-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d5c65-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d5c65-105">Suggestion</span></span>

<span data-ttu-id="d5c65-106">Stellen Sie sicher, dass zwei Ereignisnamen sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden, um die Ausnahme zu verhindern. Diese Anforderung wird mit .NET Framework 4.6.2 entfernt. Die Runtime kann Ereignisnamen unterscheiden, die sich nur durch das Suffix „Start“ oder „Stop“ unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d5c65-106">To prevent the exception, ensure that no two event names differ only by a "Start" or "Stop" suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the "Start" and "Stop" suffix.</span></span>

| <span data-ttu-id="d5c65-107">name</span><span class="sxs-lookup"><span data-stu-id="d5c65-107">Name</span></span>    | <span data-ttu-id="d5c65-108">Wert</span><span class="sxs-lookup"><span data-stu-id="d5c65-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d5c65-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="d5c65-109">Scope</span></span>   | <span data-ttu-id="d5c65-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d5c65-110">Edge</span></span>        |
| <span data-ttu-id="d5c65-111">Version</span><span class="sxs-lookup"><span data-stu-id="d5c65-111">Version</span></span> | <span data-ttu-id="d5c65-112">4.6</span><span class="sxs-lookup"><span data-stu-id="d5c65-112">4.6</span></span>         |
| <span data-ttu-id="d5c65-113">Typ</span><span class="sxs-lookup"><span data-stu-id="d5c65-113">Type</span></span>    | <span data-ttu-id="d5c65-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d5c65-114">Retargeting</span></span> |
