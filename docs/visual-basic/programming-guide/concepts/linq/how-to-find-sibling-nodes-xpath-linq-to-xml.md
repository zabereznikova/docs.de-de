---
title: 'Vorgehensweise: Suchen nach nebengeordneten Knoten (XPath-LINQ to XML) (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73082738-2113-4438-8545-98d5df0927cb
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bb981cf60d8950de2b5484946b5105dbe817ae3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-sibling-nodes-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="67145-102">Vorgehensweise: Suchen nach nebengeordneten Knoten (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67145-102">How to: Find Sibling Nodes (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="67145-103">Sie können nach allen nebengeordneten Knoten eines Knotens mit einem bestimmten Namen suchen.</span><span class="sxs-lookup"><span data-stu-id="67145-103">You might want to find all siblings of a node that have a specific name.</span></span> <span data-ttu-id="67145-104">Die resultierende Auflistung kann den Kontextknoten enthalten, sofern der Kontextknoten ebenfalls diesen Namen besitzt.</span><span class="sxs-lookup"><span data-stu-id="67145-104">The resulting collection might include the context node if the context node also has the specific name.</span></span>  
  
 <span data-ttu-id="67145-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="67145-105">The XPath expression is:</span></span>  
  
 `../Book`  
  
## <a name="example"></a><span data-ttu-id="67145-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67145-106">Example</span></span>  
 <span data-ttu-id="67145-107">Dieses Beispiel sucht zuerst nach einem `Book`-Element und dann nach allen nebengeordneten Elementen mit dem Namen `Book`.</span><span class="sxs-lookup"><span data-stu-id="67145-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`.</span></span> <span data-ttu-id="67145-108">Die resultierende Auflistung enthält den Kontextknoten.</span><span class="sxs-lookup"><span data-stu-id="67145-108">The resulting collection includes the context node.</span></span>  
  
 <span data-ttu-id="67145-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="67145-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="67145-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="67145-110">This example produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="67145-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67145-111">See Also</span></span>  
 [<span data-ttu-id="67145-112">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="67145-112">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
