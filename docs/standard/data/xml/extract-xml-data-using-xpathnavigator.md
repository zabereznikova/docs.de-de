---
title: Extrahieren von XML-Daten mit XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
ms.openlocfilehash: 627da3c8c45d007e677c4f92f4d5cd602d34ae84
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710855"
---
# <a name="extract-xml-data-using-xpathnavigator"></a>Extrahieren von XML-Daten mit XPathNavigator
Es gibt in Microsoft .NET Framework mehre Möglichkeiten zur Darstellung eines XML-Dokuments. Es kann ein <xref:System.String> oder eine der Klassen <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> oder <xref:System.Xml.XPath.XPathDocument> verwendet werden. Um den Wechsel zwischen verschiedenen Darstellungen eines XML-Dokuments zu erleichtern, stellt die <xref:System.Xml.XPath.XPathNavigator>-Klasse eine Reihe von Methoden und Eigenschaften zum Extrahieren von XML als <xref:System.String>, als <xref:System.Xml.XmlReader>-Objekt oder als <xref:System.Xml.XmlWriter>-Objekt bereit.  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a>Konvertiert einen XPathNavigator in eine Zeichenfolge.  
 Die <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse wird zum Abrufen des Markups des ganzen XML-Dokuments oder des Markups eines einzelnen Knotens und seiner untergeordneten Knoten verwendet.  
  
> [!NOTE]
> Die <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A>-Eigenschaft ruft das Markup der einem Knoten untergeordneten Knoten ab.  
  
 Im folgenden Codebeispiel wird das ganze in einem <xref:System.Xml.XPath.XPathNavigator>-Objekt enthaltene XML-Dokument sowohl als <xref:System.String> als auch als einzelner Knoten mit untergeordneten Knoten gespeichert.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a>Konvertiert von XPathNavigator in XmlReader  
 Mit der <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A>-Methode wird gesamte Inhalt eines XML-Dokuments oder nur ein einzelner Knoten und seine untergeordneten Knoten als Stream in ein <xref:System.Xml.XmlReader>-Objekt übertragen.  
  
 Beim Erstellen des <xref:System.Xml.XmlReader>-Objekts aus dem aktuellen Knoten und den untergeordneten Knoten wird die <xref:System.Xml.XmlReader>-Eigenschaft des <xref:System.Xml.XmlReader.ReadState%2A>-Objekts auf <xref:System.Xml.ReadState.Initial> festgelegt. Beim ersten Aufruf der <xref:System.Xml.XmlReader>-Methode des <xref:System.Xml.XmlReader.Read%2A>-Objekts wird die Position des <xref:System.Xml.XmlReader> auf den aktuellen Knoten des <xref:System.Xml.XPath.XPathNavigator> verschoben. Das neue <xref:System.Xml.XmlReader>-Objekt setzt den Lesevorgang bis zum Ende der XML-Struktur fort. In diesem Fall gibt die <xref:System.Xml.XmlReader.Read%2A>-Methode `false` zurück und die <xref:System.Xml.XmlReader>-Eigenschaft des <xref:System.Xml.XmlReader.ReadState%2A>-Objekts wird auf <xref:System.Xml.ReadState.EndOfFile> festgelegt.  
  
 Die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts wird durch das Erstellen oder das Verschieben des <xref:System.Xml.XmlReader>-Objekts nicht geändert. Ein Aufruf der <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A>-Methode ist nur dann zulässig, wenn das Objekt auf einem Element oder auf dem Stammknoten positioniert ist.  
  
 Im folgenden Beispiel wird ein <xref:System.Xml.XmlReader>-Objekt erstellt, das das ganze XML-Dokument sowohl in einem <xref:System.Xml.XPath.XPathDocument>-Objekt als auch als einzelnen Knoten mit untergeordneten Knoten enthält.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a>Konvertieren von XPathNavigator in XmlWriter  
 Mit der <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A>-Methode wird gesamte Inhalt eines XML-Dokuments oder nur ein einzelner Knoten und seine untergeordneten Knoten als Stream in ein <xref:System.Xml.XmlWriter>-Objekt übertragen.  
  
 Die Position des <xref:System.Xml.XPath.XPathNavigator>-Objekts wird durch das Erstellen des <xref:System.Xml.XmlWriter>-Objekts nicht geändert.  
  
 Im folgenden Beispiel wird ein <xref:System.Xml.XmlWriter>-Objekt erstellt, das das ganze XML-Dokument sowohl in einem <xref:System.Xml.XPath.XPathDocument>-Objekt als auch als einzelnen Knoten mit untergeordneten Knoten enthält.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 In dem Beispiel wird die bereits erwähnte Datei `books.xml` als Eingabe verwendet.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Navigieren in Knotengruppen mit XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)
- [Das Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Zugreifen auf streng typisierte XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)
