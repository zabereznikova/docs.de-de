---
title: Auswählen von Knoten mithilfe der XPath-Navigation
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: 85f3ae9ec9f3b4d0949a893dd1e59fbbda139066
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291460"
---
# <a name="select-nodes-using-xpath-navigation"></a>Auswählen von Knoten mithilfe der XPath-Navigation
Das XML-DOM (Document Object Model) enthält Methoden, die Ihnen ermöglichen, mithilfe der XPath-Navigation (XML Path Language) Informationen im DOM abzufragen. Mit XPath können Sie einen bestimmten einzelnen Knoten oder alle Knoten suchen, die bestimmte Kriterien erfüllen.  
  
## <a name="xpath-select-methods"></a>XPath-Auswahlmethoden  
 Die DOM-Klassen stellen zwei Methoden für die XPath-Auswahl bereit: die <xref:System.Xml.XmlNode.SelectSingleNode%2A>-Methode und die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode. Die <xref:System.Xml.XmlNode.SelectSingleNode%2A>-Methode gibt den ersten Knoten zurück, der die Auswahlkriterien erfüllt. Die <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode gibt eine <xref:System.Xml.XmlNodeList> zurück, die die übereinstimmenden Knoten enthält.  
  
 Im folgenden Beispiel wird mit der <xref:System.Xml.XmlNode.SelectSingleNode%2A>-Methode der erste `book`-Knoten ausgewählt, bei dem der Nachname des Autors den angegebenen Kriterien entspricht. Die Datei bookstore.xml (die am Ende dieses Themas zur Verfügung gestellt wird) wird als Eingabedatei verwendet.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 Im nächsten Beispiel werden mit der <xref:System.Xml.XmlNode.SelectNodes%2A>-Methode alle Buchknoten ausgewählt, bei denen der Preis größer ist als eine angegebene Summe. Der Preis für jedes Buch in der ausgewählten Liste wird dann programmgesteuert um zehn Prozent reduziert. Schließlich wird die aktualisierte Datei in die Konsole geschrieben. Die Datei bookstore.xml (die am Ende dieses Themas zur Verfügung gestellt wird) wird als Eingabedatei verwendet.  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 In den Beispielen oben wird die XPath-Abfrage beim Dokumentelement begonnen. Durch das Festlegen des Anfangspunkts für die XPath-Abfrage wird der Kontextknoten festgelegt, der den Anfangspunkt der XPath-Abfrage darstellt. Wenn Sie nicht beim Dokumentelement beginnen möchten, sondern bei seinem ersten untergeordneten Element, können Sie die select-Anweisung wie folgt schreiben:  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 Alle <xref:System.Xml.XmlNodeList>-Objekte werden mit dem zugrunde liegenden Dokument synchronisiert. Wenn Sie die Knotenliste durchlaufen und den Wert eines Knotens ändern, wird dieser Knoten daher auch in dem Dokument aktualisiert, aus dem er stammt. Beachten Sie, dass im vorhergehenden Beispiel auch das zugrunde liegende Dokument geändert wird, wenn ein Knoten in der ausgewählten <xref:System.Xml.XmlNodeList> geändert wird.  
  
> [!NOTE]
> Wenn das zugrunde liegenden Dokument verändert wird, ist es empfehlenswert, die Auswahl erneut auszuführen. Wenn die Änderung des Knoten dazu führen kann, dass der Knoten der Knotenliste hinzugefügt wird, wenn dies vorher nicht der Fall war, oder dass der Knoten aus der Knotenliste entfernt wird, kann nicht garantiert werden, dass die Knotenliste korrekt ist.  
  
## <a name="namespaces-in-xpath-expressions"></a>Namespaces in XPath-Ausdrücken  
 XPath-Ausdrücke können Namespaces enthalten. Namespace-Auflösung wird mithilfe von <xref:System.Xml.XmlNamespaceManager> unterstützt. Wenn der XPath-Ausdruck ein Präfix umfasst, muss das Paar aus Präfix- und Namespace-URI <xref:System.Xml.XmlNamespaceManager> hinzugefügt werden, und <xref:System.Xml.XmlNamespaceManager> wird an die <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29>-Methode oder die <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>-Methode übergeben. Beachten Sie, dass die oben aufgeführten Codebeispiele <xref:System.Xml.XmlNamespaceManager> verwenden, um den Namespace des Dokuments bookstore.xml aufzulösen.  
  
> [!NOTE]
> Wenn der XPath-Ausdruck kein Präfix umfasst, wird davon ausgegangen, dass der Namespace-URI (Uniform Resource Identifier) der leere Namespace ist. Wenn die XML einen Standardnamespace umfasst, muss <xref:System.Xml.XmlNamespaceManager> trotzdem ein Präfix und Namespace-URI hinzugefügt werden. Andernfalls werden keine Knoten ausgewählt.  
  
#### <a name="input-file"></a>Eingabedatei  
 Nachfolgend ist die Datei bookstore.xml aufgeführt, die für die Beispiele in diesem Thema als Eingabedatei verwendet wird:  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
