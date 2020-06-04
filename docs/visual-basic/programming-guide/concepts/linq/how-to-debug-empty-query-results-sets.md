---
title: 'Vorgehensweise: Debuggen von leeren Abfrageergebnissen'
ms.date: 07/20/2015
ms.assetid: b242c90a-d2b8-4309-8a1e-e4e70736c727
ms.openlocfilehash: b2059ccd4638d2fb77c524773cb4bd50f721b5b9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84398037"
---
# <a name="how-to-debug-empty-query-results-sets-visual-basic"></a><span data-ttu-id="2ec34-102">Gewusst wie: Debuggen von leeren Abfrageergebnis Sätzen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ec34-102">How to: Debug Empty Query Results Sets (Visual Basic)</span></span>

<span data-ttu-id="2ec34-103">Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.</span><span class="sxs-lookup"><span data-stu-id="2ec34-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>

<span data-ttu-id="2ec34-104">Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen und dann nicht ordnungsgemäß abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="2ec34-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>

<span data-ttu-id="2ec34-105">Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ec34-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>

<span data-ttu-id="2ec34-106">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="2ec34-106">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>

## <a name="example"></a><span data-ttu-id="2ec34-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ec34-107">Example</span></span>

<span data-ttu-id="2ec34-108">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="2ec34-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>

```vb
Dim root As XElement = _
    <Root xmlns='http://www.adventure-works.com'>
        <Child>1</Child>
        <Child>2</Child>
        <Child>3</Child>
        <AnotherChild>4</AnotherChild>
        <AnotherChild>5</AnotherChild>
        <AnotherChild>6</AnotherChild>
    </Root>
Dim c1 As IEnumerable(Of XElement) = _
        From el In root.<Child> _
        Select el
Console.WriteLine("Result set follows:")
For Each el As XElement In c1
    Console.WriteLine(el.Value)
Next
Console.WriteLine("End of result set")
```

<span data-ttu-id="2ec34-109">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="2ec34-109">This example produces the following result:</span></span>

```console
Result set follows:
End of result set
```

## <a name="example"></a><span data-ttu-id="2ec34-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ec34-110">Example</span></span>

<span data-ttu-id="2ec34-111">Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.</span><span class="sxs-lookup"><span data-stu-id="2ec34-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>

<span data-ttu-id="2ec34-112">Die Lösung besteht darin, einen globalen Standard Namespace zu deklarieren und zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="2ec34-112">The solution is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="2ec34-113">Dadurch werden alle XML-Eigenschaften im Standardnamespace platziert.</span><span class="sxs-lookup"><span data-stu-id="2ec34-113">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="2ec34-114">Weitere Änderungen sind für das ordnungsgemäße Funktionieren des Beispiels nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2ec34-114">No other modifications are required to the example to make it work properly.</span></span>

```vb
Imports <xmlns="http://www.adventure-works.com">

Module Module1
    Sub Main()
        Dim root As XElement = _
            <Root xmlns='http://www.adventure-works.com'>
                <Child>1</Child>
                <Child>2</Child>
                <Child>3</Child>
                <AnotherChild>4</AnotherChild>
                <AnotherChild>5</AnotherChild>
                <AnotherChild>6</AnotherChild>
            </Root>
        Dim c1 As IEnumerable(Of XElement) = _
                From el In root.<Child> _
                Select el
        Console.WriteLine("Result set follows:")
        For Each el As XElement In c1
            Console.WriteLine(CInt(el))
        Next
        Console.WriteLine("End of result set")
    End Sub
End Module
```

<span data-ttu-id="2ec34-115">Dieses Beispiel liefert das folgende Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="2ec34-115">This example produces the following result:</span></span>

```console
Result set follows:
1
2
3
End of result set
```

## <a name="see-also"></a><span data-ttu-id="2ec34-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ec34-116">See also</span></span>

- [<span data-ttu-id="2ec34-117">Grundlegende Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2ec34-117">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](basic-queries-linq-to-xml.md)
