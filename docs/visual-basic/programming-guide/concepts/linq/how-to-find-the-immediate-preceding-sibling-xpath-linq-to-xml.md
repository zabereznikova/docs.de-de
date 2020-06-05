---
title: 'Vorgehensweise: Suchen nach dem unmittelbar vorhergehenden nebengeordneten Knoten (XPath-LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: 8b0071b2f39b8debdd52083718fe928c1f9fb6f3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364525"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="94e50-102">Gewusst wie: Suchen des unmittelbar vorhergehenden neben geordneten Elements (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94e50-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="94e50-103">Es kann passieren, dass Sie den unmittelbar vorhergehenden nebengeordneten Knoten eines Knotens ermitteln möchten.</span><span class="sxs-lookup"><span data-stu-id="94e50-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="94e50-104">Aufgrund des semantischen Unterschieds bei Positionsprädikaten für die Achsen vorhergehender nebengeordneter Knoten in XPath im Vergleich zu [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist dies einer der interessanteren Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="94e50-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>

## <a name="example"></a><span data-ttu-id="94e50-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94e50-105">Example</span></span>

<span data-ttu-id="94e50-106">In diesem Beispiel verwendet die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfrage den <xref:System.Linq.Enumerable.Last%2A>-Operator, um nach dem letzten Knoten in der Auflistung zu suchen, der von <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="94e50-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="94e50-107">Im Unterschied dazu verwendet der XPath-Ausdruck für die Suche nach dem unmittelbar vorhergehenden Element ein Prädikat mit dem Wert 1.</span><span class="sxs-lookup"><span data-stu-id="94e50-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>

```vb
Dim root As XElement = _
    <Root>
        <Child1/>
        <Child2/>
        <Child3/>
        <Child4/>
    </Root>
Dim child4 As XElement = root.Element("Child4")

' LINQ to XML query
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()

' XPath expression
Dim el2 As XElement = _
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _
    IEnumerable).Cast(Of XElement)().First()

If el1 Is el2 Then
    Console.WriteLine("Results are identical")
Else
    Console.WriteLine("Results differ")
End If
Console.WriteLine(el1)
```

<span data-ttu-id="94e50-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="94e50-108">This example produces the following output:</span></span>

```console
Results are identical
<Child3 />
```

## <a name="see-also"></a><span data-ttu-id="94e50-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94e50-109">See also</span></span>

- [<span data-ttu-id="94e50-110">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94e50-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
