---
title: XPath-Abfragen und Namespaces
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: d3314a7ff4cf957dac4cd8ad0416aad434b19af2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283194"
---
# <a name="xpath-queries-and-namespaces"></a>XPath-Abfragen und Namespaces
XPath-Abfragen unterstützen Namespaces in einem XML-Dokument und können Namespacepräfixe zum Kennzeichnen von Element- und Attributnamen verwenden. Durch das Kennzeichnen von Element- und Attributnamen mit einem Namespacepräfix wird die Anzahl der von einer XPath-Abfrage zurückgegebenen Knoten auf die Knoten beschränkt, die zu einem bestimmten Namespace gehören.  
  
 Wenn z. B. das Präfix `books` dem Namespace `http://www.contoso.com/books` zugeordnet ist, wählt die folgende XPath-Abfrage `/books:books/books:book` nur die `book`-Elemente im Namespace `http://www.contoso.com/books` aus.  
  
## <a name="the-xmlnamespacemanager"></a>Der XmlNamespaceManager  
 Um Namespaces in einer XPath-Abfrage zu verwenden, wird ein von der <xref:System.Xml.IXmlNamespaceResolver>-Schnittstelle abgeleitetes Objekt wie die <xref:System.Xml.XmlNamespaceManager>-Klasse mit dem Namespace-URI und -präfix erstellt, die in die XPath-Abfrage eingefügt werden sollen.  
  
 Das <xref:System.Xml.XmlNamespaceManager>-Objekt kann in der Abfrage auf eine der folgenden Arten verwendet werden:  
  
- Das <xref:System.Xml.XmlNamespaceManager>-Objekt wird mithilfe der <xref:System.Xml.XPath.XPathExpression>-Methode des <xref:System.Xml.XPath.XPathExpression.SetContext%2A>-Objekts einem vorhandenen <xref:System.Xml.XPath.XPathExpression>-Objekt zugeordnet. Sie können auch mithilfe der statischen <xref:System.Xml.XPath.XPathExpression>-Methode ein neues <xref:System.Xml.XPath.XPathExpression.Compile%2A>-Objekt kompilieren, das eine den XPath-Ausdruck darstellende Zeichenfolge und ein <xref:System.Xml.XmlNamespaceManager>-Objekt als Parameter akzeptiert und ein neues <xref:System.Xml.XPath.XPathExpression>-Objekt zurückgibt.  
  
- Das <xref:System.Xml.XmlNamespaceManager>-Objekt selbst wird zusammen mit einer den XPath-Ausdruck darstellenden Zeichenfolge als Parameter an eine akzeptierende Methode der <xref:System.Xml.XPath.XPathNavigator>-Klasse übergeben.  
  
 Im Folgenden finden Sie eine Auflistung der Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse, die ein von der <xref:System.Xml.IXmlNamespaceResolver>-Schnittstelle abgeleitetes Objekt als Parameter akzeptieren.  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a>Der Standardnamespace  
 Im folgenden XML-Dokument wird der Standardnamespace mit einem leeren Präfix für die Deklaration des `http://www.contoso.com/books`-Namespaces verwendet.  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 XPath behandelt das leere Präfix als `null`-Namespace. Mit anderen Worten: In XPath-Abfragen können nur Präfixe verwendet werden, die Namespaces zugeordnet sind. Das bedeutet, dass Sie ein Präfix definieren müssen, wenn Sie einen Namespace in einem XML-Dokument abfragen möchten, auch wenn es sich um den Standardnamespace handelt.  
  
 Ohne die Definition eines Präfixes für das obige XML-Dokument gibt z. B. die XPath-Abfrage `/books/book` kein Ergebnis zurück.  
  
 Ein Präfix muss gebunden sein, um Mehrdeutigkeit beim Abfragen von Dokumenten zu vermeiden, die einige Knoten außerhalb der Namespaces sowie einige Knoten in einem Standardnamespace enthalten.  
  
 Im folgenden Code wird ein Präfix für den Standardnamespace definiert, und alle `book`-Elemente aus dem `http://www.contoso.com/books`-Namespace werden ausgewählt.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Auswählen von XML-Daten mit XPathNavigator](select-xml-data-using-xpathnavigator.md)
- [Auswerten von XPath-Ausdrücken mit XPathNavigator](evaluate-xpath-expressions-using-xpathnavigator.md)
- [Vergleich von Knoten mit XPathNavigator](matching-nodes-using-xpathnavigator.md)
- [In XPath-Abfragen erkannte Knotentypen](node-types-recognized-with-xpath-queries.md)
- [Kompilierte XPath-Ausdrücke](compiled-xpath-expressions.md)
