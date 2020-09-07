---
ms.openlocfilehash: 5a96b40e5e0df6a47415acecab410444a713632b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496949"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>ETW EventListeners erfassen keine Ereignisse von Anbietern mit expliziten Schlüsselwörtern (wie der TPL-Anbieter).

#### <a name="details"></a>Details

ETW EventListeners mit leerer Schlüsselwortmaske erfassen Ereignisse von Anbietern mit expliziten Schlüsselwörtern nicht ordnungsgemäß. In .NET Framework 4.5 hat der TPL-Anbieter damit begonnen, explizite Schlüsselwörter bereitzustellen und dadurch dieses Problem ausgelöst. In .NET Framework 4.6 wurde „EventListeners“ aktualisiert, damit dieses Problem nicht mehr auftritt.

#### <a name="suggestion"></a>Vorschlag

Wenn Sie dieses Problem umgehen möchten, ersetzen Sie die Aufrufe von <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> durch Aufrufe der EnableEvents-Überladung, die explizit die Maske &quot;any keywords&quot; (beliebige Schlüsselwörter), die verwendet werden soll: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Außerdem wurde dieses Problem in .NET Framework 4.6 behoben und kann sich in Ihrem Fall möglicherweise auch durch ein Upgrade auflösen.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`

-->
