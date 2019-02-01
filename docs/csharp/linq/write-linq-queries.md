---
title: Schreiben von LINQ-Abfragen in C#
description: Erfahren Sie, wie LINQ-Abfragen in C# geschrieben werden.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: 0837ebc6ebb2282ea26fad29ac1c31c87a0627ce
ms.sourcegitcommit: 5dcfeb59179e81071f54840d4902cbe00b184294
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54857813"
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="9370a-103">Schreiben von LINQ-Abfragen in C#</span><span class="sxs-lookup"><span data-stu-id="9370a-103">Write LINQ queries in C#</span></span> #

<span data-ttu-id="9370a-104">In diesem Artikel werden drei Möglichkeiten vorgestellt, mit denen eine LINQ-Abfrage in C# geschrieben werden kann:</span><span class="sxs-lookup"><span data-stu-id="9370a-104">This article shows the three ways in which you can write a LINQ query in C#:</span></span>

1. <span data-ttu-id="9370a-105">Verwenden der Abfragesyntax.</span><span class="sxs-lookup"><span data-stu-id="9370a-105">Use query syntax.</span></span>

2. <span data-ttu-id="9370a-106">Verwenden der Methodensyntax.</span><span class="sxs-lookup"><span data-stu-id="9370a-106">Use method syntax.</span></span>

3. <span data-ttu-id="9370a-107">Verwenden einer Kombination aus Abfragesyntax und Methodensyntax.</span><span class="sxs-lookup"><span data-stu-id="9370a-107">Use a combination of query syntax and method syntax.</span></span>

<span data-ttu-id="9370a-108">Die folgenden Beispiele veranschaulichen einige einfache LINQ-Abfragen anhand der oben aufgelisteten Herangehensweisen.</span><span class="sxs-lookup"><span data-stu-id="9370a-108">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="9370a-109">Im Allgemeinen gilt die Regel, wann immer möglich (1) zu verwenden, und (2) und (3) wenn nötig.</span><span class="sxs-lookup"><span data-stu-id="9370a-109">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="9370a-110">Diese Abfragen funktionieren auf Grundlage einfacher im Speicher enthaltener Auflistungen; die grundlegende Syntax entspricht jedoch genau der in „LINQ to Entities“ und „LINQ to XML“ verwendeten Syntax.</span><span class="sxs-lookup"><span data-stu-id="9370a-110">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>

## <a name="example---query-syntax"></a><span data-ttu-id="9370a-111">Beispiel: Abfragesyntax</span><span class="sxs-lookup"><span data-stu-id="9370a-111">Example - Query syntax</span></span>

<span data-ttu-id="9370a-112">Die empfohlene Methode, die meisten Abfragen zu schreiben, ist die Verwendung der *Abfragesyntax* zum Erstellen von *Abfrageausdrücken*.</span><span class="sxs-lookup"><span data-stu-id="9370a-112">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="9370a-113">Im folgenden Beispiel werden drei Abfrageausdrücke gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9370a-113">The following example shows three query expressions.</span></span> <span data-ttu-id="9370a-114">Der erste Abfrageausdruck veranschaulicht, wie man Ergebnisse durch Anwenden von Bedingungen mit einer `where`-Klausel filtern und einschränken kann.</span><span class="sxs-lookup"><span data-stu-id="9370a-114">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="9370a-115">Er gibt alle Elemente in der Quellsequenz zurück, deren Wert größer als 7 oder kleiner als 3 ist.</span><span class="sxs-lookup"><span data-stu-id="9370a-115">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="9370a-116">Der zweite Ausdruck veranschaulicht, wie man die zurückgegebenen Ergebnisse sortiert.</span><span class="sxs-lookup"><span data-stu-id="9370a-116">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="9370a-117">Der dritte Ausdruck veranschaulicht, wie man Ergebnisse nach einem Schlüssel gruppiert.</span><span class="sxs-lookup"><span data-stu-id="9370a-117">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="9370a-118">Diese Abfrage gibt basierend auf dem ersten Buchstaben des Worts zwei Gruppen zurück.</span><span class="sxs-lookup"><span data-stu-id="9370a-118">This query returns two groups based on the first letter of the word.</span></span>

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

<span data-ttu-id="9370a-119">Beachten Sie, dass der Typ der Abfrage <xref:System.Collections.Generic.IEnumerable%601> ist.</span><span class="sxs-lookup"><span data-stu-id="9370a-119">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="9370a-120">Alle diese Abfragen können mithilfe von `var` geschrieben werden, wie im folgenden Beispiel gezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="9370a-120">All of these queries could be written using `var` as shown in the following example:</span></span>

`var query = from num in numbers...`

<span data-ttu-id="9370a-121">In allen vorherigen Beispielen werden die Abfragen nicht ausgeführt, bis Sie die Iteration über die Abfragevariable in einer `foreach`- oder einer anderen Anweisung durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="9370a-121">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="9370a-122">Weitere Informationen finden Sie unter [Introduction to LINQ Queries (Einführung in LINQ-Abfragen)](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="9370a-122">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="example---method-syntax"></a><span data-ttu-id="9370a-123">Beispiel: Methodensyntax</span><span class="sxs-lookup"><span data-stu-id="9370a-123">Example - Method syntax</span></span>

<span data-ttu-id="9370a-124">Einige Abfragevorgänge müssen als Methodenaufruf ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="9370a-124">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="9370a-125">Die häufigsten derartigen Methoden sind die, die einzelne numerische Werte zurückgeben, wie z.B. <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> usw.</span><span class="sxs-lookup"><span data-stu-id="9370a-125">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="9370a-126">Diese Methoden müssen in einer Abfrage immer zuletzt aufgerufen werden, da sie nur einen einzelnen Wert darstellen und nicht als Quelle für einen zusätzlichen Abfragevorgang dienen können.</span><span class="sxs-lookup"><span data-stu-id="9370a-126">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="9370a-127">Im folgenden Beispiel wird ein Methodenaufruf in einem Abfrageausdruck dargestellt:</span><span class="sxs-lookup"><span data-stu-id="9370a-127">The following example shows a method call in a query expression:</span></span>

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

<span data-ttu-id="9370a-128">Wenn die Methode über Aktions- oder Funktionsparameter verfügt, werden diese wie im folgenden Beispiel dargestellt in Form eines [Lambdaausdrucks](../programming-guide/statements-expressions-operators/lambda-expressions.md) zur Verfügung gestellt:</span><span class="sxs-lookup"><span data-stu-id="9370a-128">If the method has Action or Func parameters, these are provided in the form of a [lambda](../programming-guide/statements-expressions-operators/lambda-expressions.md) expression, as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

<span data-ttu-id="9370a-129">Von den vorherigen Abfragen wird nur die vierte Abfrage sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9370a-129">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="9370a-130">Dies liegt daran, dass es einen einzelnen Wert zurückgibt und keine generische <xref:System.Collections.Generic.IEnumerable%601>-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="9370a-130">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="9370a-131">Die Methode selbst muss `foreach` verwenden, um einen Wert zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="9370a-131">The method itself has to use `foreach` in order to compute its value.</span></span>

<span data-ttu-id="9370a-132">Alle vorherigen Abfragen können mithilfe von implizierter Typisierung mit [var](../language-reference/keywords/var.md) geschrieben werden. Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9370a-132">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a><span data-ttu-id="9370a-133">Beispiel: Gemischte Abfrage und Methodensyntax</span><span class="sxs-lookup"><span data-stu-id="9370a-133">Example - Mixed query and method syntax</span></span>

<span data-ttu-id="9370a-134">In diesem Beispiel wird veranschaulicht, wie Sie die Methodensyntax auf die Ergebnisse einer Abfrageklausel anwenden können.</span><span class="sxs-lookup"><span data-stu-id="9370a-134">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="9370a-135">Umschließen Sie einfach den Abfrageausdruck mit Klammern, wenden Sie anschließend den Punktoperator an, und rufen Sie die Methode auf.</span><span class="sxs-lookup"><span data-stu-id="9370a-135">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="9370a-136">Im folgenden Beispiel wird von der siebten Abfrage die Anzahl der Zahlen zurückgegeben, deren Wert zwischen 3 und 7 liegt.</span><span class="sxs-lookup"><span data-stu-id="9370a-136">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="9370a-137">Im Allgemeinen ist es jedoch besser, eine zweite Variable zu verwenden, um das Ergebnis des zweiten Methodenaufrufs zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9370a-137">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="9370a-138">Auf diese Weise ist es unwahrscheinlicher, dass dieses Ergebnis mit dem Ergebnis der Abfrage verwechselt wird.</span><span class="sxs-lookup"><span data-stu-id="9370a-138">In this manner, the query is less likely to be confused with the results of the query.</span></span>

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

<span data-ttu-id="9370a-139">Da Abfrage Nr.7 einen einzelnen Wert und keine Auflistung zurückgibt, wird die Abfrage sofort ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9370a-139">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>

<span data-ttu-id="9370a-140">Die vorherige Abfrage kann mithilfe der implizierten Typisierung mit `var` wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="9370a-140">The previous query can be written by using implicit typing with `var`, as follows:</span></span>

```csharp
var numCount = (from num in numbers...
```

<span data-ttu-id="9370a-141">Sie kann folgendermaßen in Methodensyntax geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="9370a-141">It can be written in method syntax as follows:</span></span>

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

<span data-ttu-id="9370a-142">Sie kann mithilfe der implizierten Typisierung wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="9370a-142">It can be written by using explicit typing, as follows:</span></span>

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a><span data-ttu-id="9370a-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9370a-143">See also</span></span>

- [<span data-ttu-id="9370a-144">Exemplarische Vorgehensweise: Schreiben von Abfragen in C#</span><span class="sxs-lookup"><span data-stu-id="9370a-144">Walkthrough: Writing Queries in C#</span></span>](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="9370a-145">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="9370a-145">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="9370a-146">where-Klausel</span><span class="sxs-lookup"><span data-stu-id="9370a-146">where clause</span></span>](../language-reference/keywords/where-clause.md)