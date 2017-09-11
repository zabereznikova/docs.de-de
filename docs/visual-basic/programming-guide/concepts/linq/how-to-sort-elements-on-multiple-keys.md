---
title: "Gewusst wie: Sortieren von Elementen nach mehreren Schlüsseln (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 0c4c1462-3047-4766-b9e2-7e0e9cc7f421
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: ebb71092cb8341df0eaae71ac77f69ff41dd4b30
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="how-to-sort-elements-on-multiple-keys-visual-basic"></a><span data-ttu-id="066c4-102">Gewusst wie: Sortieren von Elementen nach mehreren Schlüsseln (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="066c4-102">How to: Sort Elements on Multiple Keys (Visual Basic)</span></span>
<span data-ttu-id="066c4-103">In diesem Thema wird das Sortieren nach mehreren Schlüsseln gezeigt.</span><span class="sxs-lookup"><span data-stu-id="066c4-103">This topic shows how to sort on multiple keys.</span></span>  
  
## <a name="example"></a><span data-ttu-id="066c4-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="066c4-104">Example</span></span>  
 <span data-ttu-id="066c4-105">Die Ergebnisse in diesem Beispiel werden zunächst nach der Postleitzahl des Versandziels und dann nach dem Auftragsdatum geordnet.</span><span class="sxs-lookup"><span data-stu-id="066c4-105">In this example, the results are ordered first by the shipping postal code, then by the order date.</span></span>  
  
 <span data-ttu-id="066c4-106">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="066c4-106">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="066c4-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="066c4-107">This code produces the following output:</span></span>  
  
```  
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
  
## <a name="example"></a><span data-ttu-id="066c4-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="066c4-108">Example</span></span>  
 <span data-ttu-id="066c4-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="066c4-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="066c4-110">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="066c4-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="066c4-111">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Kunden und Bestellungen in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="066c4-111">This example uses the following XML document: [Sample XML File: Customers and Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="066c4-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="066c4-112">This code produces the following output:</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="066c4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="066c4-113">See Also</span></span>  
 [<span data-ttu-id="066c4-114">Standardabfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="066c4-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)

