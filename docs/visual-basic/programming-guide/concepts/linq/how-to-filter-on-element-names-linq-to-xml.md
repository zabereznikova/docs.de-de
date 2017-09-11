---
title: 'Gewusst wie: Filtern nach Elementnamen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: b1437b4a-48aa-4546-834a-d6d3ab015fe1
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 07f7867b0fc5cf79ba5ce06f95b07b5c538e83d3
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-filter-on-element-names-linq-to-xml-visual-basic"></a><span data-ttu-id="41b68-102">Gewusst wie: Filtern nach Elementnamen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41b68-102">How to: Filter on Element Names (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="41b68-103">Beim Aufruf einer der Methoden, die zurückgeben <xref:System.Collections.Generic.IEnumerable%601>der <xref:System.Xml.Linq.XElement>, Sie können Filtern nach Elementnamen vornehmen.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="41b68-103">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41b68-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41b68-104">Example</span></span>  
 <span data-ttu-id="41b68-105">In diesem Beispiel wird eine Auflistung mit Nachfolgerelementen abgerufen, die gefiltert wird, damit sie nur die Nachfolgerelemente mit dem angegebenen Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="41b68-105">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="41b68-106">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="41b68-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
<span data-ttu-id="41b68-107"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="41b68-107"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="41b68-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="41b68-108">This code produces the following output:</span></span>  
  
<span data-ttu-id="41b68-109"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="41b68-109"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="41b68-110">Die anderen Methoden, die zurückgeben <xref:System.Collections.Generic.IEnumerable%601>von <xref:System.Xml.Linq.XElement>Sammlungen folgen demselben Muster.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="41b68-110">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="41b68-111">Ihre Signaturen entsprechen und <xref:System.Xml.Linq.XContainer.Elements%2A> <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-111">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="41b68-112">Im Folgenden finden Sie eine vollständige Liste der Methoden, die gleiche Methodensignaturen besitzen:</span><span class="sxs-lookup"><span data-stu-id="41b68-112">The following is the complete list of methods that have similar method signatures:</span></span>  
  
-   <span data-ttu-id="41b68-113"><xref:System.Xml.Linq.XNode.Ancestors%2A></xref:System.Xml.Linq.XNode.Ancestors%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-113"><xref:System.Xml.Linq.XNode.Ancestors%2A></span></span>  
  
-   <span data-ttu-id="41b68-114"><xref:System.Xml.Linq.XContainer.Descendants%2A></xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-114"><xref:System.Xml.Linq.XContainer.Descendants%2A></span></span>  
  
-   <span data-ttu-id="41b68-115"><xref:System.Xml.Linq.XContainer.Elements%2A></xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-115"><xref:System.Xml.Linq.XContainer.Elements%2A></span></span>  
  
-   <span data-ttu-id="41b68-116"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-116"><xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A></span></span>  
  
-   <span data-ttu-id="41b68-117"><xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-117"><xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A></span></span>  
  
-   <span data-ttu-id="41b68-118"><xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-118"><xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A></span></span>  
  
-   <span data-ttu-id="41b68-119"><xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></span><span class="sxs-lookup"><span data-stu-id="41b68-119"><xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A></span></span>  
  
## <a name="example"></a><span data-ttu-id="41b68-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41b68-120">Example</span></span>  
 <span data-ttu-id="41b68-121">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="41b68-121">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="41b68-122">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="41b68-122">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="41b68-123">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="41b68-123">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim items As IEnumerable(Of XElement) = _  
            From el In po...<aw:ProductName> _  
            Select el  
        For Each prdName As XElement In items  
            Console.WriteLine(prdName.Name.ToString & ":" & prdName.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="41b68-124">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="41b68-124">This code produces the following output:</span></span>  
  
```  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="41b68-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41b68-125">See Also</span></span>  
 [<span data-ttu-id="41b68-126">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41b68-126">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
