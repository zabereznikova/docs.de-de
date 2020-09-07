---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496993"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a>Kategorien der Unicode-Standardversion 8.0 werden jetzt unterstützt

#### <a name="details"></a>Details

In .NET Framework 4.6.2 ist für Unicode-Daten ein Upgrade von der Unicode-Standardversion 6.3 auf Version 8.0 erfolgt.  Wenn Sie Unicode-Zeichenkategorien in .NET Framework 4.6.2 abfragen, entsprechen einige Ergebnisse möglicherweise nicht den Ergebnissen der Vorgängerversionen von .NET Framework.  Diese Änderung betrifft hauptsächlich Cherokee-Silben und Neu-Tai-Lue-Vokalzeichen sowie Tonmarkierungen.

#### <a name="suggestion"></a>Vorschlag

Überprüfen Sie Code, und entfernen oder ändern Sie Logik, die von hartcodierten Unicode-Zeichenkategorien abhängt.

| Name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.6.2|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
