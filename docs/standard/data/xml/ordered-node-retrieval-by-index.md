---
title: Abrufen von geordneten Knoten anhand des Indexes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5412c90f-2703-4aa8-a9c4-1b8a35183c37
ms.openlocfilehash: 37d350231e03e8a435977328a288abff2f336a4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731162"
---
# <a name="ordered-node-retrieval-by-index"></a>Abrufen von geordneten Knoten anhand des Indexes

Das W3C-XML-Dokumentobjektmodell (Document Object Model – DOM) beschreibt auch eine NodeList. Diese kann eine geordnete Liste von Knoten behandeln, anders als die **XmlNamedNodeMap**, die einen ungeordneten Knotensatz behandelt. Die NodeList in Microsoft .NET Framework wird als **XmlNodeList** bezeichnet. Folgende Methoden und Eigenschaften geben eine **XmlNodeList** zurück:  
  
- XmlNode.ChildNodes  
  
- XmlDocument.GetElementsByTagName  
  
- XmlElement.GetElementsByTagName  
  
- XmlNode.SelectNodes  
  
 Die **XmlNodeList** weist eine **Count**-Eigenschaft auf, mit der eine Schleife zum Durchlaufen der Knoten in der **XmlNodeList** geschrieben werden kann, wie im folgenden Codebeispiel gezeigt:  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
   doc.Load("books.xml")  
  
    ' Retrieve all book titles.  
    Dim root as XmlElement = doc.DocumentElement  
    Dim elemList as XmlNodeList = root.GetElementsByTagName("title")  
    Dim i as integer  
    for i=0  to elemList.Count-1  
        ' Display all book titles in the Node List.  
        Console.WriteLine(elemList.ItemOf(i).InnerXml)  
    next  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
// Retrieve all book titles.  
XmlElement root = doc.DocumentElement;  
XmlNodeList elemList = root.GetElementsByTagName("title");  
for (int i=0; i < elemList.Count; i++)  
{
   // Display all book titles in the Node List.  
   Console.WriteLine(elemList[i].InnerXml);  
}
```  
  
 Zusätzlich zur **Count**-Eigenschaft gibt es die **GetEnumerator**-Methode, die eine `foreach`-Iteration der Knotenauflistung in der **XmlNodeList** ermöglicht. Im folgenden Codebeispiel wird die Verwendung der `foreach`-Anweisung veranschaulicht.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("books.xml")  
  
' Get book titles.  
Dim root As XmlElement = doc.DocumentElement  
Dim elemList As XmlNodeList = root.GetElementsByTagName("title")  
Dim ienum As IEnumerator = elemList.GetEnumerator()  
' Loop over the XmlNodeList using the enumerator ienum
While ienum.MoveNext()  
    ' Display the book title.  
    Dim title As XmlNode = CType(ienum.Current, XmlNode)  
    Console.WriteLine(title.InnerText)  
End While  
```  
  
```csharp  
{  
     XmlDocument doc = new XmlDocument();  
     doc.Load("books.xml");  
  
     // Get book titles.  
     XmlElement root = doc.DocumentElement;  
     XmlNodeList elemList = root.GetElementsByTagName("title");  
     IEnumerator ienum = elemList.GetEnumerator();
     // Loop over the XmlNodeList using the enumerator ienum
     while (ienum.MoveNext())  
     {  
          // Display the book title.  
           XmlNode title = (XmlNode) ienum.Current;  
           Console.WriteLine(title.InnerText);  
     }  
  }  
```  
  
 Weitere Informationen zu den für die **XmlNodeList** verfügbaren Methoden und Eigenschaften finden Sie unter <xref:System.Xml.XmlNodeList>.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
