---
ms.openlocfilehash: 705bbd0e0bf80e0726d41898685a5e166e039f99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858432"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>Die DateTime-Elemente von „ContentDisposition“ geben eine etwas andere Zeichenfolge zurück

|   |   |
|---|---|
|Details|Zeichenfolgendarstellungen von <xref:System.Net.Mime.ContentDisposition?displayProperty=name> wurden ab Version 4.6 aktualisiert, um die Stundenkomponente von <xref:System.DateTime?displayProperty=name> immer durch zwei Ziffern darzustellen. Dies dient zur Einhaltung von [RFC822](https://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). Dies bewirkt, dass <xref:System.Net.Mime.ContentDisposition.ToString> in Version 4.6 eine etwas andere Zeichenfolge in Szenarien zurückgibt, bei denen eines der Zeitelemente der Anordnung vor 10:00 Uhr liegt. Beachten Sie, dass ContentDisposition-Klassen manchmal durch Konvertierung in Zeichenfolgen serialisiert werden, daher sollten alle <xref:System.Net.Mime.ContentDisposition.ToString>-Vorgänge, Serialisierungen oder GetHashCode-Aufrufe überprüft werden.|
|Vorschlag|Erwarten Sie nicht, dass die Zeichenfolgendarstellungen von „ContentDispositions“ aus verschiedenen Versionen von .NET Framework ordnungsgemäß miteinander verglichen werden können. Konvertieren Sie die Zeichenfolgen wieder in „ContentDispositions“, sofern möglich, bevor Sie einen Vergleich durchführen.|
|`Scope`|Nebenversion|
|Version|4.6|
|Geben Sie Folgendes ein:|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType></li><li><xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType></li></ul>|
