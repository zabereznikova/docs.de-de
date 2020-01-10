---
title: Kompilierte XPath-Ausdrücke
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
ms.openlocfilehash: b4675765849299050eb6cddeaaa497bc6cdc620a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711102"
---
# <a name="compiled-xpath-expressions"></a>Kompilierte XPath-Ausdrücke
Ein <xref:System.Xml.XPath.XPathExpression>-Objekt stellt eine kompilierte XPath-Abfrage dar, die entweder von der statischen <xref:System.Xml.XPath.XPathExpression.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathExpression>-Klasse oder der <xref:System.Xml.XPath.XPathNavigator.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse zurückgegeben wurde.  
  
## <a name="the-xpathexpression-class"></a>Die XPathExpression-Klasse  
 Eine durch ein <xref:System.Xml.XPath.XPathExpression>-Objekt dargestellte kompilierte XPath-Abfrage ist nützlich, wenn dieselbe XPath-Abfrage mehrmals verwendet wird.  
  
 Wenn z. B. die <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode mehrmals ausgerufen wird, verwenden Sie die <xref:System.Xml.XPath.XPathExpression.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathExpression>-Klasse oder die <xref:System.Xml.XPath.XPathNavigator.Compile%2A>-Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse, um die XPath-Abfrage zu kompilieren und in einem <xref:System.Xml.XPath.XPathExpression>-Objekt zur Wiederverwendung und Leistungssteigerung zwischenzuspeichern, anstatt jedes Mal eine Zeichenfolge zu verwenden, die die XPath-Abfrage darstellt.  
  
 Nach der Kompilierung kann das <xref:System.Xml.XPath.XPathExpression>-Objekt je nach dem Typ, der von der XPath-Abfrage zurückgegeben wird, als Eingabe für die folgenden Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse verwendet werden:  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 In der folgenden Tabelle werden alle XPath-Rückgabetypen des W3C sowie ihre Entsprechungen in Microsoft .NET Framework beschrieben. Außerdem wird erläutert, welche Methoden das <xref:System.Xml.XPath.XPathExpression>-Objekt auf der Basis des Rückgabetyps verwenden.  
  
|XPath-Rückgabetyp des W3C|Entsprechender .NET Framework-Typ|Beschreibung|Methoden|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|Eine ungeordnete Auflistung von Knoten ohne Duplikate, die in der Reihenfolge der Dokumente erstellt wurde.|<xref:System.Xml.XPath.XPathNavigator.Select%2A> oder <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`Boolean`|<xref:System.Boolean>|Ein `true`-Wert oder ein `false`-Wert.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> oder<br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|Eine Gleitkommazahl.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|Eine Folge von UCS-Zeichen.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
> Die <xref:System.Xml.XPath.XPathNavigator.Matches%2A>-Methode akzeptiert einen XPath-Ausdruck als Parameter. Die <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>-Methode gibt ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zurück, nicht einen der XPath-Rückgabetypen des W3C.  
  
### <a name="the-returntype-property"></a>Die ReturnType-Eigenschaft  
 Nachdem eine XPath-Abfrage in ein <xref:System.Xml.XPath.XPathExpression>-Objekt kompiliert wurde, können Sie mithilfe der <xref:System.Xml.XPath.XPathExpression.ReturnType%2A>-Eigenschaft des <xref:System.Xml.XPath.XPathExpression>-Objekts bestimmen, was die XPath-Abfrage zurückgibt.  
  
 Die <xref:System.Xml.XPath.XPathExpression.ReturnType%2A>-Eigenschaft gibt einen der folgenden <xref:System.Xml.XPath.XPathResultType>-Enumerationswerte zurück, die die XPath-Rückgabetypen des W3C darstellen:  
  
- <xref:System.Xml.XPath.XPathResultType.Any>  
  
- <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
- <xref:System.Xml.XPath.XPathResultType.Error>  
  
- <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
- <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
- <xref:System.Xml.XPath.XPathResultType.Number>  
  
- <xref:System.Xml.XPath.XPathResultType.String>  
  
 Im folgenden Beispiel werden mithilfe des <xref:System.Xml.XPath.XPathExpression>-Objekts eine Zahl und eine Knotengruppe aus der Datei `books.xml` zurückgegeben. Die <xref:System.Xml.XPath.XPathExpression.ReturnType%2A>-Eigenschaft aller <xref:System.Xml.XPath.XPathExpression>-Objekte sowie die Ergebnisse der <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>-Methode und der <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode werden in die Konsole geschrieben.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a>Leistungsfähigere XPath-Ausdrücke  
 Wenn Sie eine bessere Leistung erreichen möchten, verwenden Sie in Ihren Abfragen einen möglichst spezifischen XPath-Ausdruck. Wenn z. B. der `book`-Knoten ein untergeordneter Knoten des `bookstore`-Knotens ist, und der `bookstore`-Knoten ist das oberste Element in einem XML-Dokument, ist die Verwendung des XPath-Ausdrucks `/bookstore/book` schneller als die Verwendung von `//book`. Der XPath-Ausdruck `//book` durchsucht alle Knoten in der XML-Struktur nach übereinstimmenden Knoten.  
  
 Darüber hinaus kann die Verwendung der von der <xref:System.Xml.XPath.XPathNavigator>-Klasse bereitgestellten Methoden zur Knotensatznavigation zur Leistungssteigerung der Auswahlmethoden führen, die von der <xref:System.Xml.XPath.XPathNavigator>-Klasse für Fälle mit einfachen Auswahlkriterien bereitgestellt werden. Wenn Sie z. B. den ersten untergeordneten Knoten des aktuellen Knotens auswählen müssen, ist es schneller, die <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>-Methode zu verwenden, als den XPath-Ausdruck `child::*[1]` und die <xref:System.Xml.XPath.XPathNavigator.Select%2A>-Methode zu verwenden.  
  
 Weitere Informationen zu den Methoden der Knotensatznavigation der <xref:System.Xml.XPath.XPathNavigator>-Klasse finden Sie unter [Navigieren in Knotengruppen mit XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Auswählen von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Auswerten von XPath-Ausdrücken mit XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [Vergleich von Knoten mit XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [In XPath-Abfragen erkannte Knotentypen](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [XPath-Abfragen und Namespaces](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
