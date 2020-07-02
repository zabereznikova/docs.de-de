---
ms.openlocfilehash: 6f5c1ecead4e2f74e621354058aab70bfa1cccb6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620223"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a>EventListener schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab

#### <a name="details"></a>Details

<xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> schneidet Zeichenfolgen mit eingebetteten NULL-Werten ab. NULL-Zeichen werden nicht von der <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Klasse unterstützt. Die Änderung betrifft nur Apps, die <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> verwenden, um <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten im Prozess zu lesen, und die NULL-Zeichen als Trennzeichen verwenden.

#### <a name="suggestion"></a>Vorschlag

<xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten sollten nach Möglichkeit aktualisiert werden, damit sie keine eingebetteten NULL-Zeichen verwenden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5.1|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Diagnostics.Tracing.EventListener.%23ctor></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType></li></ul>|
