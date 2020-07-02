---
ms.openlocfilehash: 5c27e8acdf30533036546ba4cca9e06877bde362
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620520"
---
### <a name="xslt-style-sheet-exception-message-changed"></a>Ausnahmemeldung für XSLT-Stylesheet wurde geändert

#### <a name="details"></a>Details

In .NET Framework 4.5 lautet die Fehlermeldung bei einer zu komplexen XSLT-Datei wie folgt: &quot;The style sheet is too complex.&quot; (Das Stylesheet ist zu komplex.) In früheren Versionen lautete die Fehlermeldung &quot;XSLT-Compilerfehler.&quot; Anwendungscode, der vom Text der Fehlermeldung abhängt, funktioniert nicht mehr. Die Ausnahmetypen sind jedoch nach wie vor identisch, daher sollte diese Änderung keine tatsächlichen Auswirkungen haben.

#### <a name="suggestion"></a>Vorschlag

Aktualisieren Sie jeglichen App-Code so, dass er von der Ausnahmemeldung dieser Fehlerbedingung abhängig ist, um die neue Meldung zu erwarten, oder (noch besser) aktualisieren Sie den Code so, dass er nur vom Ausnahmetyp (<xref:System.Xml.Xsl.XsltException?displayProperty=fullName>) abhängig ist, der nicht geändert wurde.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
