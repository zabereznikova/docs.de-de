---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496454"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a>Die DateTime-Elemente von „ContentDisposition“ geben eine etwas andere Zeichenfolge zurück

#### <a name="details"></a>Details

Zeichenfolgendarstellungen von <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName> wurden ab Version 4.6 aktualisiert, um die Stundenkomponente von <xref:System.DateTime?displayProperty=fullName> immer durch zwei Ziffern darzustellen. Dies dient zur Einhaltung von [RFC822](https://www.ietf.org/rfc/rfc0822.txt) und [RFC2822](https://www.ietf.org/rfc/rfc2822.txt). Dies bewirkt, dass <xref:System.Net.Mime.ContentDisposition.ToString> in Version 4.6 eine etwas andere Zeichenfolge in Szenarien zurückgibt, bei denen eines der Zeitelemente der Anordnung vor 10:00 Uhr liegt. Beachten Sie, dass ContentDisposition-Klassen manchmal durch Konvertierung in Zeichenfolgen serialisiert werden, daher sollten alle <xref:System.Net.Mime.ContentDisposition.ToString>-Vorgänge, Serialisierungen oder GetHashCode-Aufrufe überprüft werden.

#### <a name="suggestion"></a>Vorschlag

Erwarten Sie nicht, dass die Zeichenfolgendarstellungen von „ContentDispositions“ aus verschiedenen Versionen von .NET Framework ordnungsgemäß miteinander verglichen werden können. Konvertieren Sie die Zeichenfolgen wieder in „ContentDispositions“, sofern möglich, bevor Sie einen Vergleich durchführen.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
