---
title: 'Vorgehensweise: Sortieren von Elementen'
ms.date: 07/20/2015
ms.assetid: c2c09279-6c8a-482e-8e71-b1453a815052
ms.openlocfilehash: 1204fb4dc190d68956d01ffce225ce40e11538a4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397751"
---
# <a name="how-to-sort-elements-visual-basic"></a><span data-ttu-id="c9e03-102">Gewusst wie: Sortieren von Elementen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9e03-102">How to: Sort Elements (Visual Basic)</span></span>
<span data-ttu-id="c9e03-103">In diesem Beispiel wird gezeigt, wie Sie eine Abfrage schreiben können, die ihre Ergebnisse sortiert.</span><span class="sxs-lookup"><span data-stu-id="c9e03-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9e03-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9e03-104">Example</span></span>  
 <span data-ttu-id="c9e03-105">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c9e03-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="c9e03-106">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c9e03-106">This code produces the following output:</span></span>  
  
```console  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="c9e03-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9e03-107">Example</span></span>  
 <span data-ttu-id="c9e03-108">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c9e03-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="c9e03-109">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c9e03-109">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="c9e03-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="c9e03-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="c9e03-111">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c9e03-111">This code produces the following output:</span></span>  
  
```console  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9e03-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9e03-112">See also</span></span>

- [<span data-ttu-id="c9e03-113">Sortieren von Daten</span><span class="sxs-lookup"><span data-stu-id="c9e03-113">Sorting Data</span></span>](sorting-data.md)
- [<span data-ttu-id="c9e03-114">Grundlegende Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9e03-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
