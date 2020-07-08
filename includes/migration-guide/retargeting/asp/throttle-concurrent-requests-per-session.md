---
ms.openlocfilehash: b521f4163bf5bf4a369d0eec12dae503703a976e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614434"
---
### <a name="throttle-concurrent-requests-per-session"></a>Einschränken von gleichzeitigen Anforderungen pro Sitzung

#### <a name="details"></a>Details

In .NET Framework 4.6.2 und früheren Versionen führt ASP.NET Anforderungen mit der gleichen SessionID sequentiell durch, und ASP.NET stellt die SessionID standardmäßig über Cookies aus. Wenn eine Seite zum Reagieren viel Zeit in Anspruch nimmt, wird die Serverleistung allein durch Drücken von <kbd>F5</kbd> im Browser erheblich eingeschränkt. Mit der Fehlerbehebung verfolgt ein Zähler die in die Warteschlange eingestellten Anforderungen nach und beendet die Anforderungen, wenn sie einen angegebenen Grenzwert überschreiten. Der Standardwert ist 50. Wenn der Grenzwert erreicht wird, wird eine Warnung in das Ereignisprotokoll geschrieben, und möglicherweise wird eine HTTP 500-Antwort im IIS-Protokoll aufgezeichnet.

#### <a name="suggestion"></a>Vorschlag

Um das alte Verhalten wiederherzustellen, können Sie Ihrer web.config-Datei die folgende Einstellung hinzufügen, um sich gegen das neue Verhalten zu entscheiden.

```xml
<appSettings>
    <add key="aspnet:RequestQueueLimitPerSession" value="2147483647"/>
</appSettings>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.7         |
| Typ    | Neuzuweisung |
