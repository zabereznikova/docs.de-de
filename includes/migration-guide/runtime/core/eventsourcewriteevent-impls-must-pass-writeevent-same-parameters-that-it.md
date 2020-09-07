---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496097"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>„EventSource.WriteEvent impls“ muss denselben Parameter (inklusive einer ID) an WriteEvent übergeben, den es erhalten hat

#### <a name="details"></a>Details

Die Runtime erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> abgeleitet wird und eine ETW-Ereignismethode definiert, muss die <code>EventSource.WriteEvent</code>-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.

#### <a name="suggestion"></a>Vorschlag

Eine <xref:System.IndexOutOfRangeException?displayProperty=fullName>-Ausnahme wird ausgelöst, wenn <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5.1|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

Nicht über API-Analyse erkennbar.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
