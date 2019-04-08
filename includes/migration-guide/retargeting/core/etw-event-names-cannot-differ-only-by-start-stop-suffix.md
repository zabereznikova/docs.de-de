---
ms.openlocfilehash: 9ad283af76085c228bedceb6db723a1d18b10210
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761119"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="8b064-101">ETW-Ereignisnamen können sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden</span><span class="sxs-lookup"><span data-stu-id="8b064-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8b064-102">Details</span><span class="sxs-lookup"><span data-stu-id="8b064-102">Details</span></span>|<span data-ttu-id="8b064-103">In .NET Framework 4.6 und 4.6.1 löst die Laufzeit <xref:System.ArgumentException> aus, wenn zwei Ereignisnamen der Ereignisablaufverfolgung für Windows (ETW) sich lediglich durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden (z.B. wenn ein Ereignis mit <code>LogUser</code> benannt ist und das andere mit <code>LogUserStart</code>).</span><span class="sxs-lookup"><span data-stu-id="8b064-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix (as when one event is named <code>LogUser</code> and another is named <code>LogUserStart</code>).</span></span> <span data-ttu-id="8b064-104">In diesem Fall kann die Runtime die Ereignisquelle nicht erstellen, die dann keine Protokollierung durchführen kann.</span><span class="sxs-lookup"><span data-stu-id="8b064-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>|
|<span data-ttu-id="8b064-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="8b064-105">Suggestion</span></span>|<span data-ttu-id="8b064-106">Stellen Sie sicher, dass zwei Ereignisnamen sich nicht nur durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden, um die Ausnahme zu verhindern. Diese Anforderung wird mit .NET Framework 4.6.2 entfernt. Die Laufzeit kann Ereignisnamen unterscheiden, die sich nur durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="8b064-106">To prevent the exception, ensure that no two event names differ only by a &quot;Start&quot; or &quot;Stop&quot; suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the &quot;Start&quot; and &quot;Stop&quot; suffix.</span></span>|
|<span data-ttu-id="8b064-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="8b064-107">Scope</span></span>|<span data-ttu-id="8b064-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8b064-108">Edge</span></span>|
|<span data-ttu-id="8b064-109">Version</span><span class="sxs-lookup"><span data-stu-id="8b064-109">Version</span></span>|<span data-ttu-id="8b064-110">4.6</span><span class="sxs-lookup"><span data-stu-id="8b064-110">4.6</span></span>|
|<span data-ttu-id="8b064-111">Typ</span><span class="sxs-lookup"><span data-stu-id="8b064-111">Type</span></span>|<span data-ttu-id="8b064-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="8b064-112">Retargeting</span></span>|

