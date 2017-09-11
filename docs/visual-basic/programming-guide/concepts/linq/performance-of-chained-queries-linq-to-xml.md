---
title: Leistung verketteter Abfragen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: ab3bf1a195fbe83a546df7c3ae6080cc8f39e887
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017


---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="ebc2a-102">Leistung verketteter Abfragen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebc2a-102">Performance of Chained Queries (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ebc2a-103">Einer der wichtigsten Vorteile von LINQ (und LINQ to XML) besteht darin, dass verkettete Abfragen wie eine einzelne große, kompliziertere Abfrage ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-103">One of the most important benefits of LINQ (and LINQ to XML) is that chained queries can perform as well as a single larger, more complicated query.</span></span>  
  
 <span data-ttu-id="ebc2a-104">Eine verkettete Abfrage ist eine Abfrage, die als Quelle eine andere Abfrage verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-104">A chained query is a query that uses another query as its source.</span></span> <span data-ttu-id="ebc2a-105">Beispielsweise ist im folgenden einfachen Code `query2` die Quelle von `query1`:</span><span class="sxs-lookup"><span data-stu-id="ebc2a-105">For example, in the following simple code, `query2` has `query1` as its source:</span></span>  
  
```vb  
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))  
  
Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x  
  
Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e  
  
For Each i As var In query2  
    Console.WriteLine("{0}", CInt(i))  
Next  
```  
  
 <span data-ttu-id="ebc2a-106">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ebc2a-106">This example produces the following output:</span></span>  
  
```  
4  
```  
  
 <span data-ttu-id="ebc2a-107">Diese verkettete Abfrage bietet dasselbe Leistungsprofil wie das Durchlaufen einer verknüpften Liste.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-107">This chained query provides the same performance profile as iterating through a linked list.</span></span>  
  
-   <span data-ttu-id="ebc2a-108">Die <xref:System.Xml.Linq.XContainer.Elements%2A>-Achse bietet im Wesentlichen die gleiche Leistung wie das Durchlaufen einer verknüpften Liste.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="ebc2a-108">The <xref:System.Xml.Linq.XContainer.Elements%2A> axis has essentially the same performance as iterating through a linked list.</span></span> <span data-ttu-id="ebc2a-109"><xref:System.Xml.Linq.XContainer.Elements%2A>wird als Iterator mit verzögerter Ausführung implementiert.</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="ebc2a-109"><xref:System.Xml.Linq.XContainer.Elements%2A> is implemented as an iterator with deferred execution.</span></span> <span data-ttu-id="ebc2a-110">Dies bedeutet, dass neben dem Durchlaufen der verknüpften Liste einige zusätzliche Arbeitsschritte ausgeführt werden, z. B. die Zuweisung des Iteratorobjekts und das Nachverfolgen des Ausführungsstatus.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-110">This means that it does some work in addition to iterating through the linked list, such as allocating the iterator object and keeping track of execution state.</span></span> <span data-ttu-id="ebc2a-111">Diese Arbeitsschritte können in zwei Kategorien eingeteilt werden: einerseits die Schritte, die beim Einrichten des Iterators durchgeführt werden, und andererseits die Schritte, die in jeder Iteration durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-111">This work can be divided into two categories: the work that is done at the time the iterator is set up, and the work that is done during each iteration.</span></span> <span data-ttu-id="ebc2a-112">Zum Einrichten sind nur wenige, festgelegte Arbeitsschritte erforderlich, und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, sind proportional zur Anzahl der Elemente in der Quellauflistung.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-112">The setup work is a small, fixed amount of work and the work done during each iteration is proportional to the number of items in the source collection.</span></span>  
  
-   <span data-ttu-id="ebc2a-113">In `query1`, `Where` -Klausel bewirkt, dass die Abfrage zum Aufrufen der <xref:System.Linq.Enumerable.Where%2A>-Methode.</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="ebc2a-113">In `query1`, the `Where` clause causes the query to call the <xref:System.Linq.Enumerable.Where%2A> method.</span></span> <span data-ttu-id="ebc2a-114">Diese Methode ist auch als Iterator implementiert.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-114">This method is also implemented as an iterator.</span></span> <span data-ttu-id="ebc2a-115">Die Einrichtung besteht neben den normalen Einrichtungsschritten für einen Iterator aus dem Instanziieren des Delegaten, der auf den Lambdaausdruck verweist.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-115">The setup work consists of instantiating the delegate that will reference the lambda expression, plus the normal setup for an iterator.</span></span> <span data-ttu-id="ebc2a-116">Der Delegat wird bei jeder Iteration aufgerufen, um das Prädikat auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-116">With each iteration, the delegate is called to execute the predicate.</span></span> <span data-ttu-id="ebc2a-117">Diese Einrichtungsschritte und die Arbeitsschritte, die in jeder Iteration durchgeführt werden, ähneln den Arbeitsschritten, die beim Durchlaufen einer Iteration der Achse durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-117">The setup work and the work done during each iteration is the similar to the work done while iterating through the axis.</span></span>  
  
-   <span data-ttu-id="ebc2a-118">In `query1`, die select-Klausel wird von der Abfrage zum Aufrufen der <xref:System.Linq.Enumerable.Select%2A>-Methode.</xref:System.Linq.Enumerable.Select%2A></span><span class="sxs-lookup"><span data-stu-id="ebc2a-118">In `query1`, the select clause causes the query to call the <xref:System.Linq.Enumerable.Select%2A> method.</span></span> <span data-ttu-id="ebc2a-119">Diese Methode weist dasselbe Leistungsprofil wie die <xref:System.Linq.Enumerable.Where%2A>-Methode.</xref:System.Linq.Enumerable.Where%2A></span><span class="sxs-lookup"><span data-stu-id="ebc2a-119">This method has the same performance profile as the <xref:System.Linq.Enumerable.Where%2A> method.</span></span>  
  
-   <span data-ttu-id="ebc2a-120">In `query2` verfügen sowohl die `Where`-Klausel als auch die `Select`-Klausel über dasselbe Leistungsprofil wie in `query1`.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-120">In `query2`, both the `Where` clause and the `Select` clause have the same performance profile as in `query1`.</span></span>  
  
 <span data-ttu-id="ebc2a-121">Die Iteration durch `query2` ist daher direkt proportional zur Anzahl der Elemente in der Quelle der ersten Abfrage, mit anderen Worten, zeitlich linear.</span><span class="sxs-lookup"><span data-stu-id="ebc2a-121">The iteration through `query2` is therefore directly proportional to the number of items in the source of the first query, in other words, linear time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebc2a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebc2a-122">See Also</span></span>  
 [<span data-ttu-id="ebc2a-123">Leistung (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebc2a-123">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

