---
title: 'Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
ms.openlocfilehash: 52b626cfa7227312b1251a6fc998112268564084
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521919"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a><span data-ttu-id="36839-102">Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36839-102">How to: Retrieve a Single Child Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="36839-103">In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen untergeordneten Elements nach dessen Namen erläutert.</span><span class="sxs-lookup"><span data-stu-id="36839-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="36839-104">Wenn Sie den Namen des untergeordneten Elements kennen und wissen, dass es nur ein Element mit diesem Namen gibt, ist es möglicherweise sinnvoll, statt einer ganzen Auflistung nur ein einzelnes Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="36839-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="36839-105">Die <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gibt das erste untergeordnete <xref:System.Xml.Linq.XElement> mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.</span><span class="sxs-lookup"><span data-stu-id="36839-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="36839-106">Zum Abrufen eines einzelnen untergeordneten Elements in Visual Basic wird häufig die XML-Eigenschaft verwendet und dann das erste Element mittels der Arrayindexernotation abgerufen.</span><span class="sxs-lookup"><span data-stu-id="36839-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36839-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36839-107">Example</span></span>  
 <span data-ttu-id="36839-108">Im folgenden Beispiel wird die Verwendung der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="36839-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="36839-109">In diesem Beispiel wird die XML-Struktur mit dem Namen `po` genommen und nach dem ersten Element mit dem Namen `Comment` gesucht.</span><span class="sxs-lookup"><span data-stu-id="36839-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="36839-110">Das Visual Basic-Beispiel zeigt die Verwendung der Arrayindexernotation, um ein einzelnes Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="36839-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="36839-111">In diesem Beispiel wird die folgende XML-Dokument verwendet: [XML-Beispieldatei: Typische Bestellung (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="36839-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 <span data-ttu-id="36839-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="36839-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="36839-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36839-113">Example</span></span>  
 <span data-ttu-id="36839-114">Im folgenden Beispiel wird der gleiche Code für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="36839-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="36839-115">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="36839-115">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="36839-116">In diesem Beispiel wird die folgende XML-Dokument verwendet: [XML-Beispieldatei: Typische Bestellung in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="36839-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="36839-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="36839-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36839-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36839-118">See also</span></span>
- [<span data-ttu-id="36839-119">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36839-119">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
