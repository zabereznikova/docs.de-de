---
title: 'Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: 006a6afbb07ceea64b8fcc6cdab1d4fd31ae3c87
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="6fbeb-102">Gewusst wie: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fbeb-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="6fbeb-103">In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen untergeordneten Elements nach dessen Namen erläutert.</span><span class="sxs-lookup"><span data-stu-id="6fbeb-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="6fbeb-104">Wenn Sie den Namen des untergeordneten Elements kennen und wissen, dass es nur ein Element mit diesem Namen gibt, ist es möglicherweise sinnvoll, statt einer ganzen Auflistung nur ein einzelnes Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6fbeb-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="6fbeb-105">Die <xref:System.Xml.Linq.XContainer.Element%2A>Methode gibt die untergeordneten-erste <xref:System.Xml.Linq.XElement>mit der angegebenen <xref:System.Xml.Linq.XName></xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> zurück</xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="6fbeb-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="6fbeb-106">Zum Abrufen eines einzelnen untergeordneten Elements in Visual Basic wird häufig die XML-Eigenschaft verwendet und dann das erste Element mittels der Arrayindexernotation abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6fbeb-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fbeb-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fbeb-107">Example</span></span>  
 <span data-ttu-id="6fbeb-108">Das folgende Beispiel veranschaulicht die Verwendung von der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode.</xref:System.Xml.Linq.XContainer.Element%2A></span><span class="sxs-lookup"><span data-stu-id="6fbeb-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="6fbeb-109">In diesem Beispiel wird die XML-Struktur mit dem Namen `po` genommen und nach dem ersten Element mit dem Namen `Comment` gesucht.</span><span class="sxs-lookup"><span data-stu-id="6fbeb-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="6fbeb-110">Das Visual Basic-Beispiel zeigt die Verwendung der Arrayindexernotation, um ein einzelnes Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6fbeb-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="6fbeb-111">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6fbeb-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="6fbeb-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6fbeb-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="6fbeb-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fbeb-113">Example</span></span>  
 <span data-ttu-id="6fbeb-114">Im folgenden Beispiel wird der gleiche Code für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6fbeb-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="6fbeb-115">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="6fbeb-115">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="6fbeb-116">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Typical Purchase Order in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="6fbeb-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="6fbeb-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="6fbeb-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6fbeb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fbeb-118">See Also</span></span>  
 [<span data-ttu-id="6fbeb-119">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fbeb-119">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)

