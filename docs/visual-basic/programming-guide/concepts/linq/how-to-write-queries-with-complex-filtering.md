---
title: 'Gewusst wie: Schreiben von Abfragen mit komplexer Filterung (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: bf286ffc-7990-4b00-a4eb-ee3d70129950
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f8f6dfc78fb94dcb719ca68841dba54fe92ec75
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017


---
# <a name="how-to-write-queries-with-complex-filtering-visual-basic"></a><span data-ttu-id="cb0c5-102">Gewusst wie: Schreiben von Abfragen mit komplexer Filterung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb0c5-102">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>
<span data-ttu-id="cb0c5-103">Es kann vorkommen, dass Sie LINQ to XML-Abfragen mit komplexen Filtern schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="cb0c5-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="cb0c5-104">Vielleicht möchten Sie z. B. auf diese Weise nach allen Elementen suchen, die ein untergeordnetes Element mit einem bestimmten Namen und einem bestimmten Wert besitzen.</span><span class="sxs-lookup"><span data-stu-id="cb0c5-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="cb0c5-105">In diesem Thema finden Sie ein Beispiel für das Schreiben von Fragen mit komplexer Filterung.</span><span class="sxs-lookup"><span data-stu-id="cb0c5-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb0c5-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb0c5-106">Example</span></span>  
 <span data-ttu-id="cb0c5-107">Dieses Beispiel zeigt, wie Sie nach allen `PurchaseOrder`-Elementen suchen können, die ein untergeordnetes `Address`-Element mit einem `Type`-Attribut "Shipping" und einem untergeordneten `State`-Element "NY" besitzen.</span><span class="sxs-lookup"><span data-stu-id="cb0c5-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="cb0c5-108">Das Beispiel verwendet eine geschachtelte Abfrage in der `Where`-Klausel, und der `Any`-Operator gibt `True` zurück, sofern die Auflistung überhaupt Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="cb0c5-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `True` if the collection has any elements in it.</span></span>  
  
 <span data-ttu-id="cb0c5-109">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: mehrere Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c5-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="cb0c5-110">Weitere Informationen zu den `Any` Operator finden Sie unter [Quantifizierer-Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c5-110">For more information about the `Any` operator, see [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("PurchaseOrders.xml")  
Dim purchaseOrders As IEnumerable(Of XElement) = _  
    From el In root.<PurchaseOrder> _  
    Where _  
        (From add In el.<Address> _  
        Where _  
             add.@Type = "Shipping" And _  
             add.<State>.Value = "NY" _  
        Select add) _  
    .Any() _  
    Select el  
For Each el As XElement In purchaseOrders  
    Console.WriteLine(el.@PurchaseOrderNumber)  
Next  
```  
  
 <span data-ttu-id="cb0c5-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cb0c5-111">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="cb0c5-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb0c5-112">Example</span></span>  
 <span data-ttu-id="cb0c5-113">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb0c5-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cb0c5-114">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c5-114">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="cb0c5-115">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: mehrere Bestellungen in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="cb0c5-115">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim purchaseOrders As IEnumerable(Of XElement) = _  
            From el In root.<aw:PurchaseOrder> _  
            Where _  
                (From add In el.<aw:Address> _  
                Where _  
                     add.@aw:Type = "Shipping" And _  
                     add.<aw:State>.Value = "NY" _  
                Select add) _  
            .Any() _  
            Select el  
        For Each el As XElement In purchaseOrders  
            Console.WriteLine(el.@aw:PurchaseOrderNumber)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="cb0c5-116">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cb0c5-116">This code produces the following output:</span></span>  
  
```  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="cb0c5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb0c5-117">See Also</span></span>  
 <span data-ttu-id="cb0c5-118"><xref:System.Xml.Linq.XElement.Attribute%2A></xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="cb0c5-118"><xref:System.Xml.Linq.XElement.Attribute%2A></span></span>   
 <span data-ttu-id="cb0c5-119"><xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="cb0c5-119"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>   
<span data-ttu-id="cb0c5-120"> [Standardabfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="cb0c5-120"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md) </span></span>  
<span data-ttu-id="cb0c5-121"> [Untergeordnete XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="cb0c5-121"> [XML Child Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md) </span></span>  
<span data-ttu-id="cb0c5-122"> [XML-Attributachseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span><span class="sxs-lookup"><span data-stu-id="cb0c5-122"> [XML Attribute Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md) </span></span>  
<span data-ttu-id="cb0c5-123"> [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md) </span><span class="sxs-lookup"><span data-stu-id="cb0c5-123"> [XML Value Property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md) </span></span>  
<span data-ttu-id="cb0c5-124"> [Projektionsvorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md) </span><span class="sxs-lookup"><span data-stu-id="cb0c5-124"> [Projection Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md) </span></span>  
<span data-ttu-id="cb0c5-125"> [Quantifizierer-Vorgänge (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)</span><span class="sxs-lookup"><span data-stu-id="cb0c5-125"> [Quantifier Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)</span></span>
