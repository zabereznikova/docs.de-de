---
title: 'Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: 15752805f35b145514d25208b6de44a7ed8ade47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580537"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a>Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (Visual Basic)
In diesem Thema wird gezeigt, wie Sie zum übergeordneten Element navigieren und nach einem Attribut dieses übergeordneten Elements suchen können.  
  
 Der XPath-Ausdruck lautet:  
  
 `../@id`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht zuerst nach einem `Author`-Element. Anschließend wird das `id`-Attribut des übergeordneten Elements ermittelt.  
  
 In diesem Beispiel wird die folgende XML-Dokument verwendet: [XML-Beispieldatei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>Siehe auch
- [LINQ to XML für XPath-Benutzer (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
