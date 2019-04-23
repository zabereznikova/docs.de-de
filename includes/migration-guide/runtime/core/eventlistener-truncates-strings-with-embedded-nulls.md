---
ms.openlocfilehash: 9084c135769f595491d645e49d24cf507f5f6070
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235630"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab

|   |   |
|---|---|
|Details|<xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab. NULL-Zeichen werden nicht von der <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>-Klasse unterstützt. Die Änderung betrifft nur Apps, die <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> verwenden, um <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>-Daten im Prozess zu lesen, und die NULL-Zeichen als Trennzeichen verwenden.|
|Vorschlag|<xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> -Daten sollten nach Möglichkeit aktualisiert werden, damit sie keine eingebetteten NULL-Zeichen verwenden.|
|Bereich|Microsoft Edge|
|Version|4.5.1|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Diagnostics.Tracing.EventListener.%23ctor?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
