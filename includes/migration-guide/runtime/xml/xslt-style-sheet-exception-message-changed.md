---
ms.openlocfilehash: be9933e177954dc0aced81a550ef92f2c2ca08f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803993"
---
### <a name="xslt-style-sheet-exception-message-changed"></a>Ausnahmemeldung für XSLT-Stylesheet wurde geändert

|   |   |
|---|---|
|Details|In .NET Framework 4.5 lautet die Fehlermeldung bei einer zu komplexen XSLT-Datei wie folgt: &quot;The style sheet is too complex.&quot; (Das Stylesheet ist zu komplex.) In früheren Versionen lautete die Fehlermeldung &quot;XSLT-Compilerfehler.&quot; Anwendungscode, der vom Text der Fehlermeldung abhängt, funktioniert nicht mehr. Die Ausnahmetypen sind jedoch nach wie vor identisch, daher sollte diese Änderung keine tatsächlichen Auswirkungen haben.|
|Vorschlag|Aktualisieren Sie jeglichen App-Code so, dass er von der Ausnahmemeldung dieser Fehlerbedingung abhängig ist, um die neue Meldung zu erwarten, oder (noch besser) aktualisieren Sie den Code so, dass er nur vom Ausnahmetyp (<xref:System.Xml.Xsl.XsltException?displayProperty=name>) abhängig ist, der nicht geändert wurde.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Type)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Reflection.MethodInfo,System.Byte[],System.Type[])?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.String,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XmlReader,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li><li><xref:System.Xml.Xsl.XslCompiledTransform.Load(System.Xml.XPath.IXPathNavigable,System.Xml.Xsl.XsltSettings,System.Xml.XmlResolver)?displayProperty=nameWithType></li></ul>|
