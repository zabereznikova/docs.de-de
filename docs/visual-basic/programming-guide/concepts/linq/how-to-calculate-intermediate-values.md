---
title: 'Vorgehensweise: Berechnen von Zwischenwerten'
ms.date: 07/20/2015
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
ms.openlocfilehash: bc38d4848a26a24aeb00581079c9dd31abb7ba1e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375095"
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="1a0b8-102">Vorgehensweise: Berechnen von zwischen Werten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a0b8-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="1a0b8-103">In diesem Beispiel wird das Berechnen von Zwischenwerten gezeigt, die zum Sortieren, Filtern und Auswählen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1a0b8-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a0b8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a0b8-104">Example</span></span>  
 <span data-ttu-id="1a0b8-105">Im folgenden Beispiel kommt die `Let`-Klausel zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="1a0b8-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="1a0b8-106">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b8-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="1a0b8-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1a0b8-107">This code produces the following output:</span></span>  
  
```console  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="1a0b8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1a0b8-108">Example</span></span>  
 <span data-ttu-id="1a0b8-109">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a0b8-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="1a0b8-110">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b8-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1a0b8-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="1a0b8-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1a0b8-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="1a0b8-112">This code produces the following output:</span></span>  
  
```console  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a0b8-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a0b8-113">See also</span></span>

- [<span data-ttu-id="1a0b8-114">Grundlegende Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1a0b8-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
