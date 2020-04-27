---
title: Auswerten von XPath-Ausdrücken mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2913ccf3-f932-4363-8028-9e2d22ce6093
ms.openlocfilehash: 1a17aea66be7f9d35336434408c49bae8046b7e7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710907"
---
# <a name="evaluate-xpath-expressions-using-xpathnavigator"></a>Auswerten von XPath-Ausdrücken mit XPathNavigator
Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode bereit, mit der ein XPath-Ausdruck ausgewertet werden kann. Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode verwendet einen XPath-Ausdruck, wertet ihn aus und gibt je nach Ergebnis des XPath-Ausdrucks einen der W3C-XPath-Typen Boolean, Number, String oder Node Set zurück.  
  
## <a name="the-evaluate-method"></a>Die Evaluate-Methode  
 Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode akzeptiert einen XPath-Ausdruck, wertet ihn aus und gibt ein typisiertes Ergebnis vom Typ Boolean (<xref:System.Boolean>), Number (<xref:System.Double>), String (<xref:System.String>) oder Node Set (<xref:System.Xml.XPath.XPathNodeIterator>) zurück. Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode kann z. B. in einer mathematischen Methode verwendet werden. Im folgenden Beispielcode wird der Gesamtpreis aller Bücher in der Datei `books.xml` berechnet.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Dim query As XPathExpression = navigator.Compile("sum(//price/text())")  
Dim total As Double = CType(navigator.Evaluate(query), Double)  
Console.WriteLine(total)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
XPathExpression query = navigator.Compile("sum(//price/text())");  
Double total = (Double)navigator.Evaluate(query);  
Console.WriteLine(total);  
```  
  
 In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="position-and-last-functions"></a>position-Funktion und last-Funktion  
 Die <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode ist überladen. Eine der <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methoden akzeptiert ein <xref:System.Xml.XPath.XPathNodeIterator>-Objekt als Parameter. Diese bestimmte <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode ist identisch mit der <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode, die nur ein <xref:System.Xml.XPath.XPathExpression>-Objekt als Parameter verwendet, außer dass sie ein node-set-Argument zulässt, um den aktuellen Kontext anzugeben, in dem die Auswertung ausgeführt werden soll. Dieser Kontext ist für die XPath-Funktionen `position()` und `last()` erforderlich, da diese relativ zum aktuellen Kontextknoten sind. Für die `position()`-Funktion und die `last()`-Funktion ist für die Auswertung ein Verweis auf eine Knotengruppe erforderlich, sofern sie nicht als Prädikat in einem Location-Step verwendet werden, da die `position`-Funktion und die `last`-Funktion andernfalls `0` zurückgeben.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Auswählen von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Vergleich von Knoten mit XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [In XPath-Abfragen erkannte Knotentypen](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [XPath-Abfragen und Namespaces](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [Kompilierte XPath-Ausdrücke](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
