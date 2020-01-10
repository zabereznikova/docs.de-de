---
title: Ausgaben aus "XslTransform"
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
ms.openlocfilehash: 178b1e949868d3af893cbcb6df63590053341a3e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710491"
---
# <a name="outputs-from-an-xsltransform"></a>Ausgaben aus "XslTransform"
Stylesheets bestimmen das Ausgabeformat mithilfe einer `<xsl:output>`-Anweisung mit dem `method`-Attribut. In der folgenden Tabelle wird das Ausgabeformat bei Verwendung der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode für das Schreiben der Ausgabe beschrieben; außerdem wird das Ausgabeformat als <xref:System.IO.Stream> oder <xref:System.IO.TextWriter> deklariert.  
  
> [!NOTE]
> Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet. Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen. Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md).  
  
 Stylesheets bestimmen das Ausgabeformat mithilfe einer `<xsl:output>`-Anweisung mit dem `method`-Attribut. In der folgenden Tabelle wird das Ausgabeformat bei Verwendung der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode für das Schreiben der Ausgabe beschrieben; außerdem wird das Ausgabeformat als <xref:System.IO.Stream> oder <xref:System.IO.TextWriter> deklariert. In der folgenden Tabelle wird beschrieben, was geschieht, wenn von der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein Ausgabetyp in Verbindung mit einer `<xsl:output>`-Anweisung deklariert wird.  
  
|\<xsl:output method = > attribute|Ergebnisformat|  
|-----------------------------------------|-------------------|  
|method="xml"|XML|  
|method="html"|HTML|  
|method="text"|Text|  
  
> [!NOTE]
> Hinweis: Wenn die Ausgabe der `<xsl:output>`-Methode ein <xref:System.Xml.Xsl.XslTransform.Transform%2A> oder ein <xref:System.Xml.XmlReader> ist, wird die <xref:System.Xml.XmlWriter>-Anweisung ignoriert.  
  
 Wenn die Ausgabe der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein <xref:System.IO.Stream> oder ein <xref:System.IO.TextWriter> ist, werden die folgenden Attribute unterstützt:  
  
- encoding*  
  
- omit-xml-declaration  
  
- standalone  
  
- doctype-public  
  
- doctype-system  
  
- cdata-section-elements  
  
- indent  
  
    > [!NOTE]
    > \*Das encoding-Attribut wird ignoriert, wenn die <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode die Ausgabe an <xref:System.IO.TextWriter> sendet. Stattdessen wird die encoding-Eigenschaft für den <xref:System.IO.TextWriter> verwendet. 
  
 Wenn die Ausgabe der <xref:System.Xml.Xsl.XslTransform.Transform%2A>-Methode ein <xref:System.IO.Stream> ist, wird das folgende Attribut ignoriert:  
  
- Version: Die Version ist immer 1.0.  
  
- Medientyp: Der Medientyp.  
  
## <a name="escaping-special-characters"></a>Escapezeichen für Sonderzeichen  
 Das `<xsl:text disable-output-escaping>`-Tag gibt an, ob Sonderzeichen mit Escapezeichen in ein XML-Formular geschrieben werden müssen (z. B. unter Verwendung von `<&lt>` anstelle des `"<"`-Symbols) oder unverändert bleiben. Bei der Transformation in ein `disable-output-escaping`-Objekt oder ein <xref:System.Xml.XmlReader>-Objekt wird das <xref:System.Xml.XmlWriter>-Attribut ignoriert und wirkt sich nicht auf Sonderzeichen aus.  
  
## <a name="see-also"></a>Siehe auch

- [Implementierung des XSLT-Prozessors durch die XslTransform-Klasse](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
