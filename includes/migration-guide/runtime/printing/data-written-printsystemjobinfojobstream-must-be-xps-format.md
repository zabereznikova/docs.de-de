---
ms.openlocfilehash: 74f00821f2304664729faa8de2f0163c6611f513
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235640"
---
### <a name="data-written-to-printsystemjobinfojobstream-must-be-in-xps-format"></a>In PrintSystemJobInfo.JobStream geschriebene Daten müssen in XPS formatiert sein

|   |   |
|---|---|
|Details|Die <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft macht den Stream eines Druckauftrags verfügbar. Der Benutzer kann Rohdaten an das zugrunde liegende Betriebssystem senden, das Komponenten druckt, indem es in diesen Stream schreibt. Ab .NET Framework 4.5 unter Windows 8 und höheren Windows-Betriebssystemversionen müssen in diesen Stream geschriebene Daten als Paketstream im XPS-Format vorliegen.|
|Vorschlag|Zum Ausgeben der Druckinhalte können Sie einen der folgenden Schritte ausführen:<ul><li>Verwenden Sie die <xref:System.Windows.Xps.XpsDocumentWriter>-Klasse, um Druckinhalte auszugeben. Dies ist die empfohlene Alternative.</li><li>Stellen Sie sicher, dass die Daten, die an den von der <xref:System.Printing.PrintSystemJobInfo.JobStream>-Eigenschaft zurückgegebenen Stream gesendet werden, im XPS-Format als Paketstream vorliegen.</li></ul>|
|Bereich|Gering|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Printing.PrintSystemJobInfo.JobStream?displayProperty=nameWithType></li></ul>|
