---
title: 'Vorgehensweise: Suchen nach nebengeordneten Knoten (XPath-LINQ to XML) (C#)'
description: Dieses C#-Beispiel vergleicht XPath mit LINQ to XML darin, wie nach allen gleichgeordneten Elementen eines Knotens gesucht werden kann, die einen bestimmten Namen haben.
ms.date: 07/20/2015
ms.assetid: e2c73d10-a8ca-4e11-b5aa-d055de285874
ms.openlocfilehash: 2936fc4ad088580a9644f79f1797e679fe877e00
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105213"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen nach nebengeordneten Knoten (XPath-LINQ to XML) (C#)
Sie können nach allen nebengeordneten Knoten eines Knotens mit einem bestimmten Namen suchen. Die resultierende Auflistung kann den Kontextknoten enthalten, sofern der Kontextknoten ebenfalls diesen Namen besitzt.  
  
 Der XPath-Ausdruck lautet:  
  
 `../Book`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht zuerst nach einem `Book`-Element und dann nach allen nebengeordneten Elementen mit dem Namen `Book`. Die resultierende Auflistung enthält den Kontextknoten.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =
    books  
    .Root  
    .Elements("Book")  
    .Skip(1)  
    .First();  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    book  
    .Parent  
    .Elements("Book");  
  
// XPath expression  
IEnumerable<XElement> list2 = book.XPathSelectElements("../Book");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
Results are identical  
<Book id="bk101">  
  <Author>Garghentini, Davide</Author>  
  <Title>XML Developer's Guide</Title>  
  <Genre>Computer</Genre>  
  <Price>44.95</Price>  
  <PublishDate>2000-10-01</PublishDate>  
  <Description>An in-depth look at creating applications
      with XML.</Description>  
</Book>  
<Book id="bk102">  
  <Author>Garcia, Debra</Author>  
  <Title>Midnight Rain</Title>  
  <Genre>Fantasy</Genre>  
  <Price>5.95</Price>  
  <PublishDate>2000-12-16</PublishDate>  
  <Description>A former architect battles corporate zombies,
      an evil sorceress, and her own childhood to become queen
      of the world.</Description>  
</Book>  
```  
