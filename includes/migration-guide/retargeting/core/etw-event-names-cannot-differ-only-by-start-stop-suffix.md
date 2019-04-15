---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234502"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>ETW-Ereignisnamen können sich nicht nur durch das Suffix „Start“ oder „Stop“ unterscheiden

|   |   |
|---|---|
|Details|In .NET Framework 4.6 und 4.6.1 löst die Laufzeit <xref:System.ArgumentException> aus, wenn zwei Ereignisnamen der Ereignisablaufverfolgung für Windows (ETW) sich lediglich durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden (z.B. wenn ein Ereignis mit <code>LogUser</code> benannt ist und das andere mit <code>LogUserStart</code>). In diesem Fall kann die Runtime die Ereignisquelle nicht erstellen, die dann keine Protokollierung durchführen kann.|
|Vorschlag|Stellen Sie sicher, dass zwei Ereignisnamen sich nicht nur durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden, um die Ausnahme zu verhindern. Diese Anforderung wird mit .NET Framework 4.6.2 entfernt. Die Laufzeit kann Ereignisnamen unterscheiden, die sich nur durch das Suffix &quot;Start&quot; oder &quot;Stop&quot; unterscheiden.|
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Neuzuweisung|
