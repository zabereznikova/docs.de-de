---
title: 'Vorgehensweise: Abrufen eine Elementauflistung (LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
ms.openlocfilehash: 53572ac3c80e012b95527d32da28c8685cd8cfd3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58833632"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a><span data-ttu-id="05e24-102">Vorgehensweise: Abrufen eine Elementauflistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05e24-102">How to: Retrieve a Collection of Elements (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="05e24-103">In diesem Thema wird die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode erläutert.</span><span class="sxs-lookup"><span data-stu-id="05e24-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="05e24-104">Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.</span><span class="sxs-lookup"><span data-stu-id="05e24-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05e24-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05e24-105">Example</span></span>  
 <span data-ttu-id="05e24-106">Dieses Beispiel durchläuft die untergeordneten Elemente des `purchaseOrder`-Elements.</span><span class="sxs-lookup"><span data-stu-id="05e24-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="05e24-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="05e24-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 <span data-ttu-id="05e24-108">Folgende Ergebnisse werden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="05e24-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="05e24-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05e24-109">See also</span></span>

- [<span data-ttu-id="05e24-110">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05e24-110">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
