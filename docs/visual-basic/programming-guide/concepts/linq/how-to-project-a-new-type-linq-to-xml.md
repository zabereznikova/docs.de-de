---
title: 'Gewusst wie: Projizieren eines neuen Typs (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 8cfb24f5-89b2-4cfb-b85d-e7963f8f1845
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b0e3149ca2fb5e36ebc759421e9489cbfe3dde5f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-project-a-new-type-linq-to-xml-visual-basic"></a><span data-ttu-id="272e3-102">Gewusst wie: Projizieren eines neuen Typs (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="272e3-102">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="272e3-103">Andere Beispiele in diesem Abschnitt wurden Abfragen, die als Ergebnis gezeigt <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601>der `string`, und <xref:System.Collections.Generic.IEnumerable%601>von `int`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="272e3-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="272e3-104">Dabei handelt es sich zwar um gängige Ergebnistypen, die sich aber nicht für jedes Szenario eignen.</span><span class="sxs-lookup"><span data-stu-id="272e3-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="272e3-105">In vielen Fällen sollten Sie Ihre Abfragen zurückgeben einer <xref:System.Collections.Generic.IEnumerable%601>eines anderen Typs.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="272e3-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="272e3-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="272e3-106">Example</span></span>  
 <span data-ttu-id="272e3-107">In diesem Beispiel wird gezeigt, wie Sie Objekte in der `Select`-Klausel instanziieren können.</span><span class="sxs-lookup"><span data-stu-id="272e3-107">This example shows how to instantiate objects in the `Select` clause.</span></span> <span data-ttu-id="272e3-108">Der Code definiert zuerst mit einem Konstruktor eine neue Klasse und ändert anschließend die `Select`-Anweisung so, dass der Ausdruck zu einer neuen Instanz der neuen Klasse wird.</span><span class="sxs-lookup"><span data-stu-id="272e3-108">The code first defines a new class with a constructor, and then modifies the `Select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="272e3-109">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="272e3-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Public Class NameQty  
    Public name As String  
    Public qty As Integer  
    Public Sub New(ByVal n As String, ByVal q As Integer)  
        name = n  
        qty = q  
    End Sub  
End Class  
  
Public Class Program  
    Shared Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
  
        Dim nqList As IEnumerable(Of NameQty) = _  
            From n In po...<Item> _  
            Select New NameQty( _  
                n.<ProductName>.Value, CInt(n.<Quantity>.Value))  
  
        For Each n As NameQty In nqList  
            Console.WriteLine(n.name & ":" & n.qty)  
        Next  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="272e3-110">Dieses Beispiel verwendet die `M:System.Xml.Linq.XElement.Element` -Methode, die in diesem Thema eingeführten [Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="272e3-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="272e3-111">Außerdem verwendet das Beispiel Umwandlungen, um die Werte der Elemente abzurufen, die von der `M:System.Xml.Linq.XElement.Element`-Methode zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="272e3-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="272e3-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="272e3-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="272e3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="272e3-113">See Also</span></span>  
 [<span data-ttu-id="272e3-114">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="272e3-114">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
