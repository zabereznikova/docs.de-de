---
ms.openlocfilehash: a007022bf32ffe76861f6f9016a7edace17b0f61
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620353"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>In PrintSystemJobInfo.JobStream geschriebene Daten müssen in XPS formatiert sein

#### <a name="details"></a>Details

Die <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft macht den Stream eines Druckauftrags verfügbar. Der Benutzer kann Rohdaten an das zugrunde liegende Betriebssystem senden, das Komponenten druckt, indem es in diesen Stream schreibt. Ab .NET Framework 4.5 unter Windows 8 und höheren Windows-Betriebssystemversionen müssen in diesen Stream geschriebene Daten als Paketstream im XPS-Format vorliegen.

#### <a name="suggestion"></a>Vorschlag

Zum Ausgeben der Druckinhalte können Sie einen der folgenden Schritte ausführen:<ul><li>Verwenden Sie die <xref:System.Windows.Xps.XpsDocumentWriter>-Klasse, um Druckinhalte auszugeben. Dies ist die empfohlene Alternative.</li><li>Stellen Sie sicher, dass die Daten, die an den von der <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft zurückgegebenen Stream gesendet werden, im XPS-Format als Paketstream vorliegen.</li></ul>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
