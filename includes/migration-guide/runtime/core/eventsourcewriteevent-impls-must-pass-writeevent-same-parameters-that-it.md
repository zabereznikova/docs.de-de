---
ms.openlocfilehash: 47d0aa554d88726caca35fa6bebe4d863fdc0695
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804060"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a>„EventSource.WriteEvent impls“ muss denselben Parameter (inklusive einer ID) an WriteEvent übergeben, den es erhalten hat

|   |   |
|---|---|
|Details|Die Runtime erzwingt jetzt den Vertrag, der Folgendes angibt: Eine Klasse, die von <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name> abgeleitet wird und eine ETW-Ereignismethode definiert, muss die <code>EventSource.WriteEvent</code>-Methode der Basisklasse mit der Ereignis-ID, gefolgt von den gleichen Argumenten, die an die ETW-Ereignismethode übergeben wurden, aufrufen.|
|Vorschlag|Eine <xref:System.IndexOutOfRangeException?displayProperty=name>-Ausnahme wird ausgelöst, wenn <xref:System.Diagnostics.Tracing.EventListener?displayProperty=name> <xref:System.Diagnostics.Tracing.EventSource?displayProperty=name>-Daten im Prozess für eine Ereignisquelle liest, die gegen diesen Vertrag verstößt.|
|Bereich|Gering|
|Version|4.5.1|
|Typ|Laufzeit|
