---
ms.openlocfilehash: 662c140f019add66ff6605d47ad1f32c3f50d711
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620242"
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
