---
title: Schreiben von LINQ-Abfragen in C#
description: Schreiben von Abfragen.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: f3efbfd232bd7e19d3db56289f57724c71dca064
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="431ed-104">Schreiben von LINQ-Abfragen in C#</span><span class="sxs-lookup"><span data-stu-id="431ed-104">Write LINQ queries in C#</span></span>

<span data-ttu-id="431ed-105">In diesem Thema werden alle drei Möglichkeiten vorgestellt, mit denen man eine LINQ-Abfrage in C# schreiben kann:</span><span class="sxs-lookup"><span data-stu-id="431ed-105">This topic shows the three ways in which you can write a LINQ query in C#:</span></span>  
  
1.  <span data-ttu-id="431ed-106">Verwenden der Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="431ed-106">Use query syntax.</span></span>  
  
2.  <span data-ttu-id="431ed-107">Verwenden der Methodensyntax.</span><span class="sxs-lookup"><span data-stu-id="431ed-107">Use method syntax.</span></span>  
  
3.  <span data-ttu-id="431ed-108">Verwenden einer Kombination aus Abfragesyntax und Methodensyntax.</span><span class="sxs-lookup"><span data-stu-id="431ed-108">Use a combination of query syntax and method syntax.</span></span>  
  
 <span data-ttu-id="431ed-109">Die folgenden Beispiele veranschaulichen einige einfache LINQ-Abfragen anhand der oben aufgelisteten Herangehensweisen.</span><span class="sxs-lookup"><span data-stu-id="431ed-109">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="431ed-110">Im Allgemeinen gilt die Regel, wann immer möglich (1) zu verwenden, und (2) und (3) wenn nötig.</span><span class="sxs-lookup"><span data-stu-id="431ed-110">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="431ed-111">Diese Abfragen funktionieren auf Grundlage einfacher im Speicher enthaltener Auflistungen; die grundlegende Syntax entspricht jedoch genau der in „LINQ to Entities“ und „LINQ to XML“ verwendeten Syntax.</span><span class="sxs-lookup"><span data-stu-id="431ed-111">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>  
  
## <a name="example"></a><span data-ttu-id="431ed-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="431ed-112">Example</span></span>  
  
## <a name="query-syntax"></a><span data-ttu-id="431ed-113">Abfragesyntax</span><span class="sxs-lookup"><span data-stu-id="431ed-113">Query syntax</span></span>  
 <span data-ttu-id="431ed-114">Die empfohlene Methode, die meisten Abfragen zu schreiben, ist die Verwendung der *Abfragesyntax* zum Erstellen von *Abfrageausdrücken*.</span><span class="sxs-lookup"><span data-stu-id="431ed-114">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="431ed-115">Im folgenden Beispiel werden drei Abfrageausdrücke gezeigt.</span><span class="sxs-lookup"><span data-stu-id="431ed-115">The following example shows three query expressions.</span></span> <span data-ttu-id="431ed-116">Der erste Abfrageausdruck veranschaulicht, wie man Ergebnisse durch Anwenden von Bedingungen mit einer `where`-Klausel filtern und einschränken kann.</span><span class="sxs-lookup"><span data-stu-id="431ed-116">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="431ed-117">Er gibt alle Elemente in der Quellsequenz zurück, deren Wert größer als 7 oder kleiner als 3 ist.</span><span class="sxs-lookup"><span data-stu-id="431ed-117">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="431ed-118">Der zweite Ausdruck veranschaulicht, wie man die zurückgegebenen Ergebnisse sortiert.</span><span class="sxs-lookup"><span data-stu-id="431ed-118">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="431ed-119">Der dritte Ausdruck veranschaulicht, wie man Ergebnisse nach einem Schlüssel gruppiert.</span><span class="sxs-lookup"><span data-stu-id="431ed-119">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="431ed-120">Diese Abfrage gibt basierend auf dem ersten Buchstaben des Worts zwei Gruppen zurück.</span><span class="sxs-lookup"><span data-stu-id="431ed-120">This query returns two groups based on the first letter of the word.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#5](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]  
  
 <span data-ttu-id="431ed-121">Beachten Sie, dass der Typ der Abfrage <xref:System.Collections.Generic.IEnumerable%601> ist.</span><span class="sxs-lookup"><span data-stu-id="431ed-121">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="431ed-122">Alle diese Abfragen können mithilfe von `var` geschrieben werden, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="431ed-122">All of these queries could be written using `var` as shown in the following example:</span></span>  
  
 `var query = from num in numbers...`  
  
 <span data-ttu-id="431ed-123">In allen vorherigen Beispielen werden die Abfragen nicht ausgeführt, bis Sie die Iteration über die Abfragevariable in einer `foreach`- oder einer anderen Anweisung durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="431ed-123">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="431ed-124">Weitere Informationen finden Sie unter [Introduction to LINQ Queries (Einführung in LINQ-Abfragen)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="431ed-124">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="431ed-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="431ed-125">Example</span></span>  
  
## <a name="method-syntax"></a><span data-ttu-id="431ed-126">Methodensyntax</span><span class="sxs-lookup"><span data-stu-id="431ed-126">Method syntax</span></span>  
 <span data-ttu-id="431ed-127">Einige Abfragevorgänge müssen als Methodenaufruf ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="431ed-127">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="431ed-128">Die häufigsten derartigen Methoden sind die, die einzelne numerische Werte zurückgeben, wie z.B. <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> usw.</span><span class="sxs-lookup"><span data-stu-id="431ed-128">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="431ed-129">Diese Methoden müssen in einer Abfrage immer zuletzt aufgerufen werden, da sie nur einen einzelnen Wert darstellen und nicht als Quelle für einen zusätzlichen Abfragevorgang dienen können.</span><span class="sxs-lookup"><span data-stu-id="431ed-129">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="431ed-130">Im folgenden Beispiel wird ein Methodenaufruf in einem Abfrageausdruck dargestellt:</span><span class="sxs-lookup"><span data-stu-id="431ed-130">The following example shows a method call in a query expression:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#6](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="431ed-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="431ed-131">Example</span></span>  
 <span data-ttu-id="431ed-132">Wenn die Methode über Aktions- oder Func-Parameter verfügt, werden diese in Form eines [Lambdaausdruckes](../programming-guide/statements-expressions-operators/lambda-expressions.md) zur Verfügung gestellt, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="431ed-132">If the method has  Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#7](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]  
  
 <span data-ttu-id="431ed-133">Von den vorherigen Abfragen wird nur die vierte Abfrage sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="431ed-133">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="431ed-134">Dies liegt daran, dass es einen einzelnen Wert zurückgibt und keine generische <xref:System.Collections.Generic.IEnumerable%601>-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="431ed-134">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="431ed-135">Die Methode selbst muss `foreach` verwenden, um einen Wert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="431ed-135">The method itself has to use `foreach` in order to compute its value.</span></span>  
  
 <span data-ttu-id="431ed-136">Alle vorherigen Abfragen können mithilfe von implizierter Typisierung mit [var](../language-reference/keywords/var.md) geschrieben werden. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="431ed-136">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#8](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]  
  
## <a name="example"></a><span data-ttu-id="431ed-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="431ed-137">Example</span></span>  
  
## <a name="mixed-query-and-method-syntax"></a><span data-ttu-id="431ed-138">Gemischte Abfrage und Methodensyntax</span><span class="sxs-lookup"><span data-stu-id="431ed-138">Mixed query and method syntax</span></span>  
 <span data-ttu-id="431ed-139">In diesem Beispiel wird veranschaulicht, wie Sie die Methodensyntax auf die Ergebnisse einer Abfrageklausel anwenden können.</span><span class="sxs-lookup"><span data-stu-id="431ed-139">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="431ed-140">Umschließen Sie einfach den Abfrageausdruck mit Klammern, wenden Sie anschließend den Punktoperator an, und rufen Sie die Methode auf.</span><span class="sxs-lookup"><span data-stu-id="431ed-140">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="431ed-141">Im folgenden Beispiel wird von der siebten Abfrage die Anzahl der Zahlen zurückgegeben, deren Wert zwischen 3 und 7 liegt.</span><span class="sxs-lookup"><span data-stu-id="431ed-141">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="431ed-142">Im Allgemeinen ist es jedoch besser, eine zweite Variable zu verwenden, um das Ergebnis des zweiten Methodenaufrufs zu speichern.</span><span class="sxs-lookup"><span data-stu-id="431ed-142">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="431ed-143">Auf diese Weise ist es unwahrscheinlicher, dass dieses Ergebnis mit dem Ergebnis der Abfrage verwechselt wird.</span><span class="sxs-lookup"><span data-stu-id="431ed-143">In this manner, the query is less likely to be confused with the results of the query.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#9](../../../samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]  
  
 <span data-ttu-id="431ed-144">Da Abfrage Nr.7 einen einzelnen Wert und keine Auflistung zurückgibt, wird die Abfrage sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="431ed-144">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>  
  
 <span data-ttu-id="431ed-145">Die vorherige Abfrage kann mithilfe der implizierten Typisierung mit `var` wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="431ed-145">The previous query can be written by using implicit typing with `var`, as follows:</span></span>  
  
```csharp  
var numCount = (from num in numbers...  
```  
  
 <span data-ttu-id="431ed-146">Sie kann folgendermaßen in Methodensyntax geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="431ed-146">It can be written in method syntax as follows:</span></span>  
  
```csharp  
var numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
 <span data-ttu-id="431ed-147">Sie kann mithilfe der implizierten Typisierung wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="431ed-147">It can be written by using explicit typing, as follows:</span></span>  
  
```csharp  
int numCount = numbers.Where(n => n < 3 || n > 7).Count();  
```  
  
## <a name="see-also"></a><span data-ttu-id="431ed-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="431ed-148">See Also</span></span>  
  <span data-ttu-id="431ed-149">[Exemplarische Vorgehensweise: Schreiben von Abfragen in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span><span class="sxs-lookup"><span data-stu-id="431ed-149">[Walkthrough: Writing Queries in C#](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md) </span></span>  
 [<span data-ttu-id="431ed-150">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="431ed-150">LINQ Query Expressions</span></span>](index.md)  
 [<span data-ttu-id="431ed-151">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="431ed-151">where clause</span></span>](../language-reference/keywords/where-clause.md)
