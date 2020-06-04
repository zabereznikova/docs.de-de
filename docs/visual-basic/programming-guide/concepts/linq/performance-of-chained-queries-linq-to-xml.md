---
title: Leistung verketteter Abfragen (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
ms.openlocfilehash: 6b87f2744f663ebd45dceb036dcaac71b80765fc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396388"
---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="0e7a9-102">Leistung verketteter Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e7a9-102">Performance of Chained Queries (LINQ to XML) (Visual Basic)</span></span>

<span data-ttu-id="0e7a9-103">Einer der wichtigsten Vorteile von LINQ (und LINQ to XML) besteht darin, dass verkettete Abfragen wie eine einzelne große, kompliziertere Abfrage ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>

<span data-ttu-id="0e7a9-104">Eine verkettete Abfrage ist eine Abfrage, die als Quelle eine andere Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="0e7a9-105">Beispielsweise ist im folgenden einfachen Code `query2` die Quelle von `query1`:</span><span class="sxs-lookup"><span data-stu-id="0e7a9-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>

```vb
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))

Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x

Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e

For Each i As var In query2
    Console.WriteLine("{0}", CInt(i))
Next
```

<span data-ttu-id="0e7a9-106">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0e7a9-106">This example produces the following output:</span></span>

```console
4
```

<span data-ttu-id="0e7a9-107">Diese verkettete Abfrage bietet dasselbe Leistungsprofil wie das Durchlaufen einer verknüpften Liste.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>

- <span data-ttu-id="0e7a9-108">Die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse bietet im Wesentlichen die gleiche Leistung wie das Durchlaufen einer verknüpften Liste.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="0e7a9-109"><xref:System.Xml.Linq.XContainer.Elements%2A> wird als Iterator mit verzögerter Ausführung implementiert.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="0e7a9-110">Dies bedeutet, dass neben dem Durchlaufen der verknüpften Liste einige zusätzliche Arbeitsschritte ausgeführt werden, z. B. die Zuweisung des Iteratorobjekts und das Nachverfolgen des Ausführungsstatus.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="0e7a9-111">Diese Arbeitsschritte können in zwei Kategorien eingeteilt werden: einerseits die Schritte, die beim Einrichten des Iterators durchgeführt werden, und andererseits die Schritte, die in jeder Iteration durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="0e7a9-112">Zum Einrichten sind nur wenige, festgelegte Arbeitsschritte erforderlich, und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, sind proportional zur Anzahl der Elemente in der Quellauflistung.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>

- <span data-ttu-id="0e7a9-113">In `query1` wird von der Abfrage durch die `Where`-Klausel die <xref:System.Linq.Enumerable.Where%2A>-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-113">In `query1`, the `Where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="0e7a9-114">Diese Methode ist auch als Iterator implementiert.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="0e7a9-115">Die Einrichtung besteht neben den normalen Einrichtungsschritten für einen Iterator aus dem Instanziieren des Delegaten, der auf den Lambdaausdruck verweist.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="0e7a9-116">Der Delegat wird bei jeder Iteration aufgerufen, um das Prädikat auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="0e7a9-117">Diese Einrichtungsschritte und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, ähneln den Arbeitsschritten, die beim Durchlaufen einer Iteration der Achse durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>

- <span data-ttu-id="0e7a9-118">In `query1` wird von der Abfrage durch die <xref:System.Linq.Enumerable.Select%2A>select<xref:System.Linq.Enumerable.Select%2A>-Klausel die {3}-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="0e7a9-119">Diese Methode weist dasselbe Leistungsprofil wie die <xref:System.Linq.Enumerable.Where%2A>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>

- <span data-ttu-id="0e7a9-120">In `query2` verfügen sowohl die `Where`-Klausel als auch die `Select`-Klausel über dasselbe Leistungsprofil wie in `query1`.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-120">In `query2`, both the `Where` clause and the `Select` clause have the same performance profile as in `query1`.</span></span>

 <span data-ttu-id="0e7a9-121">Die Iteration durch `query2` ist daher direkt proportional zur Anzahl der Elemente in der Quelle der ersten Abfrage, mit anderen Worten, zeitlich linear.</span><span class="sxs-lookup"><span data-stu-id="0e7a9-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e7a9-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e7a9-122">See also</span></span>

- [<span data-ttu-id="0e7a9-123">Leistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e7a9-123">Performance (LINQ to XML) (Visual Basic)</span></span>](performance-linq-to-xml.md)
