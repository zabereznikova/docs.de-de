---
ms.openlocfilehash: 19be8a7755d9b238ab6507eaa73319bddf39faa3
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496843"
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
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Printing.PrintSystemJobInfo.JobStream`

-->
