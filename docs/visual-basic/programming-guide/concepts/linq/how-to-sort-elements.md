---
title: 'Gewusst wie: Sortieren von Elementen (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: c2c09279-6c8a-482e-8e71-b1453a815052
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5b36e9717b3366d73ee4c72390c88dde52248496
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-sort-elements-visual-basic"></a><span data-ttu-id="2fc8b-102">Gewusst wie: Sortieren von Elementen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2fc8b-102">How to: Sort Elements (Visual Basic)</span></span>
<span data-ttu-id="2fc8b-103">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage schreiben können, die ihre Ergebnisse sortiert.</span><span class="sxs-lookup"><span data-stu-id="2fc8b-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fc8b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fc8b-104">Example</span></span>  
 <span data-ttu-id="2fc8b-105">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: numerische Daten (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2fc8b-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim prices As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let price = Convert.ToDecimal(el.<Price>.Value) _  
    Order By (price) _  
    Select price  
For Each el As Decimal In prices  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="2fc8b-106">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2fc8b-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="2fc8b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2fc8b-107">Example</span></span>  
 <span data-ttu-id="2fc8b-108">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fc8b-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="2fc8b-109">Weitere Informationen finden Sie unter [arbeiten mit XML-Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="2fc8b-109">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="2fc8b-110">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: numerische Daten in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="2fc8b-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim prices As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let price = Convert.ToDecimal(el.<Price>.Value) _  
            Order By (price) _  
            Select price  
        For Each el As Decimal In prices  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="2fc8b-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2fc8b-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fc8b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fc8b-112">See Also</span></span>  
 <span data-ttu-id="2fc8b-113">[Sortieren von Daten](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md) </span><span class="sxs-lookup"><span data-stu-id="2fc8b-113">[Sorting Data](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md) </span></span>  
<span data-ttu-id="2fc8b-114"> [Standardabfragen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="2fc8b-114"> [Basic Queries (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)</span></span>
