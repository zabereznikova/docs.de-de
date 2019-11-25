---
title: 'Gewusst wie: Suchen nach nebengeordneten Knoten (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 73082738-2113-4438-8545-98d5df0927cb
ms.openlocfilehash: 52151c939bbf67df37a9535b1081ff902d357123
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344638"
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-visual-basic"></a>How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)

Sie können nach allen nebengeordneten Knoten eines Knotens mit einem bestimmten Namen suchen. Die resultierende Auflistung kann den Kontextknoten enthalten, sofern der Kontextknoten ebenfalls diesen Namen besitzt.

Der XPath-Ausdruck lautet:

`../Book`

## <a name="example"></a>Beispiel

Dieses Beispiel sucht zuerst nach einem `Book`-Element und dann nach allen nebengeordneten Elementen mit dem Namen `Book`. Die resultierende Auflistung enthält den Kontextknoten.

In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).

```vb
Dim books As XDocument = XDocument.Load("Books.xml")
Dim book As XElement = books.Root.<Book>.Skip(1).First()

' LINQ to XML query
Dim list1 As IEnumerable(Of XElement) = book.Parent.<Book>

' XPath expression
Dim list2 As IEnumerable(Of XElement) = book.XPathSelectElements("../Book")

If list1.Count() = list2.Count() And _
        list1.Intersect(list2).Count() = list1.Count() Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
For Each el As XElement In list1
    Console.WriteLine(el)
Next
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```console
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

## <a name="see-also"></a>Siehe auch

- [LINQ to XML for XPath Users (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
