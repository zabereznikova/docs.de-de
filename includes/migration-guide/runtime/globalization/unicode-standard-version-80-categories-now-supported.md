---
ms.openlocfilehash: a20fad5f9c95e59c14ffd91f4921cf8bfab443cd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621186"
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
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
