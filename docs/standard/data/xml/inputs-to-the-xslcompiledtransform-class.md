---
title: Eingaben für die XslCompiledTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 834049f1-ab41-449e-9f10-4a1d0701bc48
ms.openlocfilehash: 9aae85aa4516dc0555e959358ba1b7db3002145d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710738"
---
# <a name="inputs-to-the-xslcompiledtransform-class"></a>Eingaben für die XslCompiledTransform-Klasse
Die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode akzeptiert drei Eingabetypen für das Quelldokument: ein Objekt, das die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle implementiert, ein <xref:System.Xml.XmlReader>-Objekt, das das Quelldokument liest, oder einen Zeichenfolgen-URI.  
  
> [!NOTE]
> Mit der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse wird Leerraum standardmäßig beibehalten. Dies entspricht [Abschnitt 3.4 der W3C-Empfehlung zu XSLT, Version 1.0](https://www.w3.org/TR/xslt.html#strip).  
  
## <a name="ixpathnavigable-interface"></a>"IXPathNavigable"-Schnittstelle  
 Die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle ist in der <xref:System.Xml.XmlNode>-Klasse und der <xref:System.Xml.XPath.XPathDocument>-Klasse implementiert. Diese Klassen stellen einen speicherinternen Cache der XML-Daten dar.  
  
- Die <xref:System.Xml.XmlNode>-Klasse basiert auf dem W3C-DOM (Document Object Model) und umfasst Bearbeitungsfunktionen.  
  
- Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist ein schreibgeschützter Datenspeicher, der auf dem XPath-Datenmodell basiert. <xref:System.Xml.XPath.XPathDocument> ist die empfohlene Klasse zu XSLT-Verarbeitung. Im Vergleich zur <xref:System.Xml.XmlNode>-Klasse bietet sie eine schnellere Leistung.  
  
> [!NOTE]
> Transformationen werden auf das gesamte Dokument angewendet. Wenn Sie einen anderen Knoten als den Stammknoten des Dokuments übergeben, wird dadurch nicht verhindert, dass im Transformationsprozess auf alle Knoten im geladenen Dokument zugegriffen wird. Zum Transformieren eines Knotenfragments müssen Sie ein Objekt erstellen, das nur das Knotenfragment enthält, und dieses Objekt an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode übergeben. Weitere Informationen finden Sie unter [Gewusst wie: Transformieren eines Knotenfragments](../../../../docs/standard/data/xml/how-to-transform-a-node-fragment.md).  
  
 Im folgenden Beispiel wird die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType>-Methode zum Transformieren der Datei books.xml in die Datei books.html mit dem Stylesheet transform.xsl verwendet. Die Dateien „books.xml“ und „transform.xsl“ kommen in folgendem Thema vor: [Gewusst wie: Ausführen einer XSLT-Transformation mittels einer Assembly](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#1)]
 [!code-vb[XslCompiledTransform.Transform2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#1)]  
  
## <a name="xmlreader-object"></a>"XmlReader"-Objekt  
 Die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode wird aus dem aktuellen Knoten vom <xref:System.Xml.XmlReader> über alle untergeordneten Elemente geladen. Dadurch können Sie einen Teil eines Dokuments als Kontextdokument verwenden. Nach der Rückgabe der <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode wird der <xref:System.Xml.XmlReader> auf dem nächsten Knoten nach dem Ende des Kontextdokuments platziert. Wenn das Ende des Dokuments erreicht wird, wird der <xref:System.Xml.XmlReader> am Ende der Datei (EOF) platziert.  
  
 Im folgenden Beispiel wird die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType>-Methode zum Transformieren der Datei books.xml in die Datei books.html mit dem Stylesheet transform.xsl verwendet. Die Dateien „books.xml“ und „transform.xsl“ kommen in folgendem Thema vor: [Gewusst wie: Ausführen einer XSLT-Transformation mittels einer Assembly](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#2)]
 [!code-vb[XslCompiledTransform.Transform2#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#2)]  
  
## <a name="string-uri"></a>Zeichenfolgen-URI  
 Sie können auch den URI des Quelldokuments als XSLT-Eingabe angeben. Mit einem <xref:System.Xml.XmlResolver> wird der URI aufgelöst. Sie können angeben, welcher <xref:System.Xml.XmlResolver> verwendet werden soll, indem Sie ihn an die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode übergeben. Wenn kein <xref:System.Xml.XmlResolver> angegeben ist, verwendet die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A>-Methode einen Standard-<xref:System.Xml.XmlUrlResolver> ohne Anmeldeinformationen.  
  
 Im folgenden Beispiel wird die <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A?displayProperty=nameWithType>-Methode zum Transformieren der Datei books.xml in die Datei books.html mit dem Stylesheet transform.xsl verwendet. Die Dateien „books.xml“ und „transform.xsl“ kommen in folgendem Thema vor: [Gewusst wie: Ausführen einer XSLT-Transformation mittels einer Assembly](../../../../docs/standard/data/xml/how-to-perform-an-xslt-transformation-by-using-an-assembly.md).  
  
 [!code-csharp[XslCompiledTransform.Transform2#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Transform2/CS/Program.cs#3)]
 [!code-vb[XslCompiledTransform.Transform2#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Transform2/VB/Module1.vb#3)]  
  
 Weitere Informationen finden Sie unter [Auflösen von externen Ressourcen während der XSLT-Verarbeitung](../../../../docs/standard/data/xml/resolving-external-resources-during-xslt-processing.md).  
  
## <a name="see-also"></a>Siehe auch

- [XSLT Transformations (XSLT-Transformationen)](../../../../docs/standard/data/xml/xslt-transformations.md)
