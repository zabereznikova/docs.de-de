---
title: 'Vorgehensweise: Sortieren von Elementen nach mehreren Schlüsseln'
ms.date: 07/20/2015
ms.assetid: 0c4c1462-3047-4766-b9e2-7e0e9cc7f421
ms.openlocfilehash: de468f999117030942f9e770cd1235966f17e2c7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397738"
---
# <a name="how-to-sort-elements-on-multiple-keys-visual-basic"></a><span data-ttu-id="c9902-102">Gewusst wie: Sortieren von Elementen nach mehreren Schlüsseln (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9902-102">How to: Sort Elements on Multiple Keys (Visual Basic)</span></span>
<span data-ttu-id="c9902-103">In diesem Thema wird das Sortieren nach mehreren Schlüsseln gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9902-103">This topic shows how to sort on multiple keys.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9902-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9902-104">Example</span></span>  
 <span data-ttu-id="c9902-105">Die Ergebnisse in diesem Beispiel werden zunächst nach der Postleitzahl des Versandziels und dann nach dem Auftragsdatum geordnet.</span><span class="sxs-lookup"><span data-stu-id="c9902-105">In this example, the results are ordered first by the shipping postal code, then by the order date.</span></span>  
  
 <span data-ttu-id="c9902-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c9902-106">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim result = _  
    From c In co.<Orders>.<Order> _  
    Order By c.<ShipInfo>.<ShipPostalCode>.Value, Convert.ToDateTime(c.<OrderDate>.Value) _  
    Select New With { _  
        .CustomerID = c.<CustomerID>.Value, _  
        .EmployeeID = c.<EmployeeID>.Value, _  
        .ShipPostalCode = c.<ShipInfo>.<ShipPostalCode>.Value, _  
        .OrderDate = Convert.ToDateTime(c.<OrderDate>.Value) _  
    }  
For Each r In result  
    Console.WriteLine("CustomerID:{0} EmployeeID:{1} ShipPostalCode:{2} OrderDate:{3:d}", _  
                r.CustomerID, r.EmployeeID, r.ShipPostalCode, r.OrderDate)  
Next  
```  
  
 <span data-ttu-id="c9902-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c9902-107">This code produces the following output:</span></span>  
  
```console  
CustomerID:LETSS EmployeeID:1 ShipPostalCode:94117 OrderDate:6/25/1997  
CustomerID:LETSS EmployeeID:8 ShipPostalCode:94117 OrderDate:10/27/1997  
CustomerID:LETSS EmployeeID:6 ShipPostalCode:94117 OrderDate:11/10/1997  
CustomerID:LETSS EmployeeID:4 ShipPostalCode:94117 OrderDate:2/12/1998  
CustomerID:GREAL EmployeeID:6 ShipPostalCode:97403 OrderDate:5/6/1997  
CustomerID:GREAL EmployeeID:8 ShipPostalCode:97403 OrderDate:7/4/1997  
CustomerID:GREAL EmployeeID:1 ShipPostalCode:97403 OrderDate:7/31/1997  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:7/31/1997  
CustomerID:GREAL EmployeeID:6 ShipPostalCode:97403 OrderDate:9/4/1997  
CustomerID:GREAL EmployeeID:3 ShipPostalCode:97403 OrderDate:9/25/1997  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:1/6/1998  
CustomerID:GREAL EmployeeID:3 ShipPostalCode:97403 OrderDate:3/9/1998  
CustomerID:GREAL EmployeeID:3 ShipPostalCode:97403 OrderDate:4/7/1998  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:4/22/1998  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:4/30/1998  
CustomerID:HUNGC EmployeeID:3 ShipPostalCode:97827 OrderDate:12/6/1996  
CustomerID:HUNGC EmployeeID:1 ShipPostalCode:97827 OrderDate:12/25/1996  
CustomerID:HUNGC EmployeeID:3 ShipPostalCode:97827 OrderDate:1/15/1997  
CustomerID:HUNGC EmployeeID:4 ShipPostalCode:97827 OrderDate:7/16/1997  
CustomerID:HUNGC EmployeeID:8 ShipPostalCode:97827 OrderDate:9/8/1997  
CustomerID:LAZYK EmployeeID:1 ShipPostalCode:99362 OrderDate:3/21/1997  
CustomerID:LAZYK EmployeeID:8 ShipPostalCode:99362 OrderDate:5/22/1997  
```  
  
## <a name="example"></a><span data-ttu-id="c9902-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9902-108">Example</span></span>  
 <span data-ttu-id="c9902-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9902-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c9902-110">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c9902-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="c9902-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen in einem Namespace](sample-xml-file-customers-and-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c9902-111">This example uses the following XML document: [Sample XML File: Customers and Orders in a Namespace](sample-xml-file-customers-and-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adventure-works.com'>  
  
Module Module1  
    Sub Main()  
        Dim co As XElement = XElement.Load("CustomersOrdersInNamespace.xml")  
        Dim result = _  
            From c In co.<Orders>.<Order> _  
            Order By c.<ShipInfo>.<ShipPostalCode>.Value, Convert.ToDateTime(c.<OrderDate>.Value) _  
            Select New With { _  
                .CustomerID = c.<CustomerID>.Value, _  
                .EmployeeID = c.<EmployeeID>.Value, _  
                .ShipPostalCode = c.<ShipInfo>.<ShipPostalCode>.Value, _  
                .OrderDate = Convert.ToDateTime(c.<OrderDate>.Value) _  
            }  
        For Each r In result  
            Console.WriteLine("CustomerID:{0} EmployeeID:{1} ShipPostalCode:{2} OrderDate:{3:d}", _  
                        r.CustomerID, r.EmployeeID, r.ShipPostalCode, r.OrderDate)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="c9902-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c9902-112">This code produces the following output:</span></span>  
  
```console  
CustomerID:LETSS EmployeeID:1 ShipPostalCode:94117 OrderDate:6/25/1997  
CustomerID:LETSS EmployeeID:8 ShipPostalCode:94117 OrderDate:10/27/1997  
CustomerID:LETSS EmployeeID:6 ShipPostalCode:94117 OrderDate:11/10/1997  
CustomerID:LETSS EmployeeID:4 ShipPostalCode:94117 OrderDate:2/12/1998  
CustomerID:GREAL EmployeeID:6 ShipPostalCode:97403 OrderDate:5/6/1997  
CustomerID:GREAL EmployeeID:8 ShipPostalCode:97403 OrderDate:7/4/1997  
CustomerID:GREAL EmployeeID:1 ShipPostalCode:97403 OrderDate:7/31/1997  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:7/31/1997  
CustomerID:GREAL EmployeeID:6 ShipPostalCode:97403 OrderDate:9/4/1997  
CustomerID:GREAL EmployeeID:3 ShipPostalCode:97403 OrderDate:9/25/1997  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:1/6/1998  
CustomerID:GREAL EmployeeID:3 ShipPostalCode:97403 OrderDate:3/9/1998  
CustomerID:GREAL EmployeeID:3 ShipPostalCode:97403 OrderDate:4/7/1998  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:4/22/1998  
CustomerID:GREAL EmployeeID:4 ShipPostalCode:97403 OrderDate:4/30/1998  
CustomerID:HUNGC EmployeeID:3 ShipPostalCode:97827 OrderDate:12/6/1996  
CustomerID:HUNGC EmployeeID:1 ShipPostalCode:97827 OrderDate:12/25/1996  
CustomerID:HUNGC EmployeeID:3 ShipPostalCode:97827 OrderDate:1/15/1997  
CustomerID:HUNGC EmployeeID:4 ShipPostalCode:97827 OrderDate:7/16/1997  
CustomerID:HUNGC EmployeeID:8 ShipPostalCode:97827 OrderDate:9/8/1997  
CustomerID:LAZYK EmployeeID:1 ShipPostalCode:99362 OrderDate:3/21/1997  
CustomerID:LAZYK EmployeeID:8 ShipPostalCode:99362 OrderDate:5/22/1997  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9902-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9902-113">See also</span></span>

- [<span data-ttu-id="c9902-114">Grundlegende Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9902-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
