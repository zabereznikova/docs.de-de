---
ms.openlocfilehash: 9c3eedb7f7d4cd030a12c141b8630876c1ffdb4d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236448"
---
### <a name="throttle-concurrent-requests-per-session"></a>Einschränken von gleichzeitigen Anforderungen pro Sitzung

|   |   |
|---|---|
|Details|In .NET Framework 4.6.2 und früheren Versionen führt ASP.NET Anforderungen mit der gleichen SessionID sequentiell durch, und ASP.NET stellt die SessionID standardmäßig über Cookies aus. Wenn eine Seite zum Reagieren viel Zeit in Anspruch nimmt, wird die Serverleistung durch einfaches Drücken von F5 im Browser erheblich eingeschränkt. Mit der Fehlerbehebung verfolgt ein Zähler die in die Warteschlange eingestellten Anforderungen nach und beendet die Anforderungen, wenn sie einen angegebenen Grenzwert überschreiten. Der Standardwert ist 50. Wenn der Grenzwert erreicht wird, wird eine Warnung in das Ereignisprotokoll geschrieben, und möglicherweise wird eine HTTP 500-Antwort im IIS-Protokoll aufgezeichnet.|
|Vorschlag|Um das alte Verhalten wiederherzustellen, können Sie Ihrer web.config-Datei die folgende Einstellung hinzufügen, um sich gegen das neue Verhalten zu entscheiden.<pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;aspnet:RequestQueueLimitPerSession&quot; value=&quot;2147483647&quot;/&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|Bereich|Microsoft Edge|
|Version|4.7|
|Typ|Neuzuweisung|
