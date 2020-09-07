---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496949"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="28f6b-101">ETW EventListeners erfassen keine Ereignisse von Anbietern mit expliziten Schlüsselwörtern (wie der TPL-Anbieter).</span><span class="sxs-lookup"><span data-stu-id="28f6b-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="28f6b-102">Details</span><span class="sxs-lookup"><span data-stu-id="28f6b-102">Details</span></span>

<span data-ttu-id="28f6b-103">ETW EventListeners mit leerer Schlüsselwortmaske erfassen Ereignisse von Anbietern mit expliziten Schlüsselwörtern nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="28f6b-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="28f6b-104">In .NET Framework 4.5 hat der TPL-Anbieter damit begonnen, explizite Schlüsselwörter bereitzustellen und dadurch dieses Problem ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="28f6b-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="28f6b-105">In .NET Framework 4.6 wurde „EventListeners“ aktualisiert, damit dieses Problem nicht mehr auftritt.</span><span class="sxs-lookup"><span data-stu-id="28f6b-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="28f6b-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="28f6b-106">Suggestion</span></span>

<span data-ttu-id="28f6b-107">Wenn Sie dieses Problem umgehen möchten, ersetzen Sie die Aufrufe von <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> durch Aufrufe der EnableEvents-Überladung, die explizit die Maske &quot;any keywords&quot; (beliebige Schlüsselwörter), die verwendet werden soll: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Außerdem wurde dieses Problem in .NET Framework 4.6 behoben und kann sich in Ihrem Fall möglicherweise auch durch ein Upgrade auflösen.</span><span class="sxs-lookup"><span data-stu-id="28f6b-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="28f6b-108">Name</span><span class="sxs-lookup"><span data-stu-id="28f6b-108">Name</span></span>    | <span data-ttu-id="28f6b-109">Wert</span><span class="sxs-lookup"><span data-stu-id="28f6b-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="28f6b-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="28f6b-110">Scope</span></span>   |<span data-ttu-id="28f6b-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="28f6b-111">Edge</span></span>|
|<span data-ttu-id="28f6b-112">Version</span><span class="sxs-lookup"><span data-stu-id="28f6b-112">Version</span></span>|<span data-ttu-id="28f6b-113">4.5</span><span class="sxs-lookup"><span data-stu-id="28f6b-113">4.5</span></span>|
|<span data-ttu-id="28f6b-114">Typ</span><span class="sxs-lookup"><span data-stu-id="28f6b-114">Type</span></span>|<span data-ttu-id="28f6b-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="28f6b-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="28f6b-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="28f6b-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
