---
title: "Gewusst wie: Suchen eines Attributs des übergeordneten Elements (XPath-LINQ to XML) (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 93cc2804f52201bd87282020a381ada8550b7a0f
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="644da-102">Gewusst wie: Suchen eines Attributs des übergeordneten Elements (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="644da-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="644da-103">In diesem Thema wird gezeigt, wie Sie zum übergeordneten Element navigieren und nach einem Attribut dieses übergeordneten Elements suchen können.</span><span class="sxs-lookup"><span data-stu-id="644da-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="644da-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="644da-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="644da-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="644da-105">Example</span></span>  
 <span data-ttu-id="644da-106">Dieses Beispiel sucht zuerst nach einem `Author`-Element.</span><span class="sxs-lookup"><span data-stu-id="644da-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="644da-107">Anschließend wird das `id`-Attribut des übergeordneten Elements ermittelt.</span><span class="sxs-lookup"><span data-stu-id="644da-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="644da-108">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="644da-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 <span data-ttu-id="644da-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="644da-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="644da-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="644da-110">See Also</span></span>  
 [<span data-ttu-id="644da-111">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="644da-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

