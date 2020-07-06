---
ms.openlocfilehash: 7d50962b518c15875a5f1a82f5b89ab87a1db02e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620233"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a><span data-ttu-id="f3eef-101">ETW EventListeners erfassen keine Ereignisse von Anbietern mit expliziten Schlüsselwörtern (wie der TPL-Anbieter).</span><span class="sxs-lookup"><span data-stu-id="f3eef-101">ETW EventListeners do not capture events from providers with explicit keywords (like the TPL provider)</span></span>

#### <a name="details"></a><span data-ttu-id="f3eef-102">Details</span><span class="sxs-lookup"><span data-stu-id="f3eef-102">Details</span></span>

<span data-ttu-id="f3eef-103">ETW EventListeners mit leerer Schlüsselwortmaske erfassen Ereignisse von Anbietern mit expliziten Schlüsselwörtern nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="f3eef-103">ETW EventListeners with a blank keyword mask do not properly capture events from providers with explicit keywords.</span></span> <span data-ttu-id="f3eef-104">In .NET Framework 4.5 hat der TPL-Anbieter damit begonnen, explizite Schlüsselwörter bereitzustellen und dadurch dieses Problem ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f3eef-104">In the .NET Framework 4.5, the TPL provider began providing explicit keywords and triggered this issue.</span></span> <span data-ttu-id="f3eef-105">In .NET Framework 4.6 wurde „EventListeners“ aktualisiert, damit dieses Problem nicht mehr auftritt.</span><span class="sxs-lookup"><span data-stu-id="f3eef-105">In the .NET Framework 4.6, EventListeners have been updated to no longer have this issue.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f3eef-106">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="f3eef-106">Suggestion</span></span>

<span data-ttu-id="f3eef-107">Wenn Sie dieses Problem umgehen möchten, ersetzen Sie die Aufrufe von <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> durch Aufrufe der EnableEvents-Überladung, die explizit die Maske &quot;any keywords&quot; (beliebige Schlüsselwörter), die verwendet werden soll: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Außerdem wurde dieses Problem in .NET Framework 4.6 behoben und kann sich in Ihrem Fall möglicherweise auch durch ein Upgrade auflösen.</span><span class="sxs-lookup"><span data-stu-id="f3eef-107">To work around this problem, replace calls to <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> with calls to the EnableEvents overload that explicitly specifies the &quot;any keywords&quot; mask to use: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>.Alternatively, this issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="f3eef-108">Name</span><span class="sxs-lookup"><span data-stu-id="f3eef-108">Name</span></span>    | <span data-ttu-id="f3eef-109">Wert</span><span class="sxs-lookup"><span data-stu-id="f3eef-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f3eef-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="f3eef-110">Scope</span></span>   |<span data-ttu-id="f3eef-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f3eef-111">Edge</span></span>|
|<span data-ttu-id="f3eef-112">Version</span><span class="sxs-lookup"><span data-stu-id="f3eef-112">Version</span></span>|<span data-ttu-id="f3eef-113">4.5</span><span class="sxs-lookup"><span data-stu-id="f3eef-113">4.5</span></span>|
|<span data-ttu-id="f3eef-114">Typ</span><span class="sxs-lookup"><span data-stu-id="f3eef-114">Type</span></span>|<span data-ttu-id="f3eef-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f3eef-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f3eef-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="f3eef-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
