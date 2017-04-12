---
title: Serialisieren in einen XmlReader (XSLT aufrufen) (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bca1e63bbe5b3ccd13f183c3cc6081917624ad94
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a>Serialisieren in einen XmlReader (XSLT aufrufen) (Visual Basic)
Bei Verwendung der <xref:System.Xml?displayProperty=fullName>interoperabilitätsmöglichkeiten [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], können Sie <xref:System.Xml.Linq.XNode.CreateReader%2A>zum Erstellen einer <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XNode.CreateReader%2A> </xref:System.Xml?displayProperty=fullName> Das Modul, das von diesem liest <xref:System.Xml.XmlReader>liest die Knoten aus der XML-Struktur und verarbeitet sie entsprechend.</xref:System.Xml.XmlReader>  
  
## <a name="invoking-an-xslt-transformation"></a>Aufrufen einer XSLT-Transformation  
 Diese Methode kann z. B. zum Aufrufen einer XSLT-Transformation verwendet werden. Sie können eine XML-Struktur erstellen, erstellen Sie eine <xref:System.Xml.XmlReader>aus der XML-Struktur ein neues Dokument erstellen, und erstellen Sie dann eine <xref:System.Xml.XmlWriter>zum Schreiben in das neue Dokument.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> Anschließend können Sie die XSLT-Transformation übergeben <xref:System.Xml.XmlReader>und <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> aufrufen. Nach erfolgreichem Abschluss der Transformation wird die neue XML-Struktur mit den Ergebnissen der Transformation aufgefüllt.  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>  
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
        <xsl:template match='/Parent'>  
            <Root>  
                <C1>  
                    <xsl:value-of select='Child1'/>  
                </C1>  
                <C2>  
                    <xsl:value-of select='Child2'/>  
                </C2>  
            </Root>  
        </xsl:template>  
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
