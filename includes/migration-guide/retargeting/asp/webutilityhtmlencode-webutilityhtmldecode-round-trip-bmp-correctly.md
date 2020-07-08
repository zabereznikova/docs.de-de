---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617164"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode und WebUtility.HtmlDecode führen für die BMP eine ordnungsgemäße Roundtripkonvertierung durch

#### <a name="details"></a>Details

Bei Anwendungen mit der Zielplattform .NET Framework 4.5 wird für Zeichen, die sich außerhalb der Basic Multilingual Plane (BMP) befinden, eine erfolgreiche Roundtripkonvertierung durchgeführt, wenn sie an die <xref:System.Net.WebUtility.HtmlDecode(System.String)>-Methoden übergeben werden.

#### <a name="suggestion"></a>Vorschlag

Diese Änderung sollte keine Auswirkung auf aktuelle Anwendungen haben. Wenn Sie jedoch das ursprüngliche Verhalten wiederherstellen möchten, legen Sie das Attribut `targetFramework` des Elements `<httpRuntime>` auf eine andere Zeichenfolge als „4.5“ fest. Sie können die `unicodeEncodingConformance`- und `unicodeDecodingConformance`-Attribute des `<webUtility>`-Konfigurationselements auch festlegen, um dieses Verhalten unabhängig von der Zielversion von .NET Framework zu steuern.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Microsoft Edge        |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
