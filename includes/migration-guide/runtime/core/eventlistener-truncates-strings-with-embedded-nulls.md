---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496571"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
