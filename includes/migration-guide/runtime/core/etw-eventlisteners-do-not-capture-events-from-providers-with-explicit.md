---
ms.openlocfilehash: 1ef31202d7c072ca27c21fc22db102aafa6b8de7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858835"
---
### <a name="etw-eventlisteners-do-not-capture-events-from-providers-with-explicit-keywords-like-the-tpl-provider"></a>ETW EventListeners erfassen keine Ereignisse von Anbietern mit expliziten Schlüsselwörtern (wie der TPL-Anbieter).

|   |   |
|---|---|
|Details|ETW EventListeners mit leerer Schlüsselwortmaske erfassen Ereignisse von Anbietern mit expliziten Schlüsselwörtern nicht ordnungsgemäß. In .NET Framework 4.5 hat der TPL-Anbieter damit begonnen, explizite Schlüsselwörter bereitzustellen und dadurch dieses Problem ausgelöst. In .NET Framework 4.6 wurde „EventListeners“ aktualisiert, damit dieses Problem nicht mehr auftritt.|
|Vorschlag|Wenn Sie dieses Problem umgehen möchten, ersetzen Sie die Aufrufe von <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)> durch Aufrufe der EnableEvents-Überladung, die explizit die Maske &quot;any keywords&quot; (beliebige Schlüsselwörter), die verwendet werden soll: <code>EnableEvents(eventSource, level, unchecked((EventKeywords)0xFFFFffffFFFFffff))</code>. Außerdem wurde dieses Problem in .NET Framework 4.6 behoben und kann sich in Ihrem Fall möglicherweise auch durch ein Upgrade auflösen.|
|`Scope`|Edge|
|Version|4.5|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li></ul>|
