---
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: be2e401c7931b2637c14a3ea3b742a2c09917939
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869986"
---
# <a name="aggregate-clause-visual-basic"></a><span data-ttu-id="0fb32-102">Aggregate-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fb32-102">Aggregate Clause (Visual Basic)</span></span>

<span data-ttu-id="0fb32-103">Wendet eine oder mehrere Aggregatfunktionen auf eine Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="0fb32-103">Applies one or more aggregate functions to a collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fb32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fb32-104">Syntax</span></span>  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a><span data-ttu-id="0fb32-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="0fb32-105">Parts</span></span>  
  
|<span data-ttu-id="0fb32-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0fb32-106">Term</span></span>|<span data-ttu-id="0fb32-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0fb32-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="0fb32-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fb32-108">Required.</span></span> <span data-ttu-id="0fb32-109">Variable, mit der die Elemente der Auflistung durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="0fb32-109">Variable used to iterate through the elements of the collection.</span></span>|  
|`type`|<span data-ttu-id="0fb32-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0fb32-110">Optional.</span></span> <span data-ttu-id="0fb32-111">Der `element`-Typ.</span><span class="sxs-lookup"><span data-stu-id="0fb32-111">The type of `element`.</span></span> <span data-ttu-id="0fb32-112">Wenn kein Typ angegeben ist, wird der Typ von `element` aus abgeleitet `collection` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-112">If no type is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="0fb32-113">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fb32-113">Required.</span></span> <span data-ttu-id="0fb32-114">Verweist auf die Auflistung, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fb32-114">Refers to the collection to operate on.</span></span>|  
|`clause`|<span data-ttu-id="0fb32-115">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0fb32-115">Optional.</span></span> <span data-ttu-id="0fb32-116">Eine oder mehrere Abfrage Klauseln, wie z. b. eine- `Where` Klausel, um das Abfrageergebnis zum Anwenden der Aggregat Klausel oder-Klauseln zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="0fb32-116">One or more query clauses, such as a `Where` clause, to refine the query result to apply the aggregate clause or clauses to.</span></span>|  
|`expressionList`|<span data-ttu-id="0fb32-117">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0fb32-117">Required.</span></span> <span data-ttu-id="0fb32-118">Mindestens ein durch Trennzeichen getrennter Ausdruck, der eine Aggregatfunktion identifiziert, die auf die Auflistung angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fb32-118">One or more comma-delimited expressions that identify an aggregate function to apply to the collection.</span></span> <span data-ttu-id="0fb32-119">Sie können einen Alias auf eine Aggregatfunktion anwenden, um einen Elementnamen für das Abfrageergebnis anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0fb32-119">You can apply an alias to an aggregate function to specify a member name for the query result.</span></span> <span data-ttu-id="0fb32-120">Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fb32-120">If no alias is supplied, the name of the aggregate function is used.</span></span> <span data-ttu-id="0fb32-121">Beispiele finden Sie im Abschnitt zu Aggregatfunktionen weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="0fb32-121">For examples, see the section about aggregate functions later in this topic.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fb32-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0fb32-122">Remarks</span></span>  

 <span data-ttu-id="0fb32-123">Die- `Aggregate` Klausel kann verwendet werden, um Aggregatfunktionen in Ihre Abfragen einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="0fb32-123">The `Aggregate` clause can be used to include aggregate functions in your queries.</span></span> <span data-ttu-id="0fb32-124">Aggregatfunktionen führen Überprüfungen und Berechnungen für einen Satz von Werten aus und geben einen einzelnen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="0fb32-124">Aggregate functions perform checks and computations over a set of values and return a single value.</span></span> <span data-ttu-id="0fb32-125">Sie können auf den berechneten Wert zugreifen, indem Sie einen Member des Abfrageergebnis Typs verwenden.</span><span class="sxs-lookup"><span data-stu-id="0fb32-125">You can access the computed value by using a member of the query result type.</span></span> <span data-ttu-id="0fb32-126">Die standardmäßigen Aggregatfunktionen, die Sie verwenden können `All` , sind die `Any` Funktionen,, `Average` , `Count` , `LongCount` , `Max` , `Min` und `Sum` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-126">The standard aggregate functions that you can use are the `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, and `Sum` functions.</span></span> <span data-ttu-id="0fb32-127">Diese Funktionen sind Entwicklern vertraut, die mit Aggregaten in SQL vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="0fb32-127">These functions are familiar to developers who are familiar with aggregates in SQL.</span></span> <span data-ttu-id="0fb32-128">Diese werden im folgenden Abschnitt dieses Themas beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0fb32-128">They are described in the following section of this topic.</span></span>  
  
 <span data-ttu-id="0fb32-129">Das Ergebnis einer Aggregatfunktion ist im Abfrageergebnis als Feld des Abfrageergebnis Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="0fb32-129">The result of an aggregate function is included in the query result as a field of the query result type.</span></span> <span data-ttu-id="0fb32-130">Sie können einen Alias für das Aggregat Funktionsergebnis angeben, um den Namen des Members des Abfrageergebnis Typs anzugeben, der den Aggregatwert enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="0fb32-130">You can supply an alias for the aggregate function result to specify the name of the member of the query result type that will hold the aggregate value.</span></span> <span data-ttu-id="0fb32-131">Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="0fb32-131">If no alias is supplied, the name of the aggregate function is used.</span></span>  
  
 <span data-ttu-id="0fb32-132">Die- `Aggregate` Klausel kann eine Abfrage beginnen, oder Sie kann als zusätzliche Klausel in eine Abfrage eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="0fb32-132">The `Aggregate` clause can begin a query, or it can be included as an additional clause in a query.</span></span> <span data-ttu-id="0fb32-133">Wenn die- `Aggregate` Klausel eine Abfrage startet, ist das Ergebnis ein einzelner Wert, der das Ergebnis der Aggregatfunktion ist, die in der-Klausel angegeben ist `Into` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-133">If the `Aggregate` clause begins a query, the result is a single value that is the result of the aggregate function specified in the `Into` clause.</span></span> <span data-ttu-id="0fb32-134">Wenn mehr als eine Aggregatfunktion in der-Klausel angegeben ist `Into` , gibt die Abfrage einen einzelnen Typ mit einer separaten Eigenschaft zurück, um auf das Ergebnis jeder Aggregatfunktion in der-Klausel zu verweisen `Into` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-134">If more than one aggregate function is specified in the `Into` clause, the query returns a single type with a separate property to reference the result of each aggregate function in the `Into` clause.</span></span> <span data-ttu-id="0fb32-135">Wenn die `Aggregate` Klausel als zusätzliche Klausel in einer Abfrage enthalten ist, verfügt der in der Abfrage Auflistung zurückgegebene Typ über eine separate Eigenschaft, die auf das Ergebnis jeder Aggregatfunktion in der- `Into` Klausel verweist.</span><span class="sxs-lookup"><span data-stu-id="0fb32-135">If the `Aggregate` clause is included as an additional clause in a query, the type returned in the query collection will have a separate property to reference the result of each aggregate function in the `Into` clause.</span></span>  
  
## <a name="aggregate-functions"></a><span data-ttu-id="0fb32-136">Aggregatfunktionen</span><span class="sxs-lookup"><span data-stu-id="0fb32-136">Aggregate Functions</span></span>

<span data-ttu-id="0fb32-137">Die folgenden standardmäßigen Aggregatfunktionen können mit der-Klausel verwendet werden `Aggregate` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-137">The following are the standard aggregate functions that can be used with the `Aggregate` clause.</span></span>  
  
### <a name="all"></a><span data-ttu-id="0fb32-138">All</span><span class="sxs-lookup"><span data-stu-id="0fb32-138">All</span></span>

<span data-ttu-id="0fb32-139">Gibt zurück `true` , wenn alle Elemente in der Auflistung eine angegebene Bedingung erfüllen; andernfalls wird zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-139">Returns `true` if all elements in the collection satisfy a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="0fb32-140">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-140">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a><span data-ttu-id="0fb32-141">Any</span><span class="sxs-lookup"><span data-stu-id="0fb32-141">Any</span></span>

<span data-ttu-id="0fb32-142">Gibt zurück `true` , wenn ein beliebiges Element in der Auflistung eine angegebene Bedingung erfüllt; andernfalls wird zurückgegeben `false` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-142">Returns `true` if any element in the collection satisfies a specified condition; otherwise returns `false`.</span></span> <span data-ttu-id="0fb32-143">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-143">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a><span data-ttu-id="0fb32-144">Durchschnitt</span><span class="sxs-lookup"><span data-stu-id="0fb32-144">Average</span></span>

<span data-ttu-id="0fb32-145">Berechnet den Durchschnitt aller Elemente in der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fb32-145">Computes the average of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0fb32-146">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-146">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a><span data-ttu-id="0fb32-147">Anzahl</span><span class="sxs-lookup"><span data-stu-id="0fb32-147">Count</span></span>

<span data-ttu-id="0fb32-148">Zählt die Anzahl der Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fb32-148">Counts the number of elements in the collection.</span></span> <span data-ttu-id="0fb32-149">Sie können einen optionalen `Boolean` Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0fb32-149">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="0fb32-150">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-150">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a><span data-ttu-id="0fb32-151">Group</span><span class="sxs-lookup"><span data-stu-id="0fb32-151">Group</span></span>

<span data-ttu-id="0fb32-152">Bezieht sich auf Abfrageergebnisse, die als Ergebnis einer-oder-Klausel gruppiert sind `Group By` `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-152">Refers to query results that are grouped as a result of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="0fb32-153">Die- `Group` Funktion ist nur in der- `Into` Klausel einer-oder-Klausel gültig `Group By` `Group Join` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-153">The `Group` function is valid only in the `Into` clause of a `Group By` or `Group Join` clause.</span></span> <span data-ttu-id="0fb32-154">Weitere Informationen und Beispiele finden Sie unter [Group By-Klausel](group-by-clause.md) und [Group Join-Klausel](group-join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0fb32-154">For more information and examples, see [Group By Clause](group-by-clause.md) and [Group Join Clause](group-join-clause.md).</span></span>

### <a name="longcount"></a><span data-ttu-id="0fb32-155">LongCount</span><span class="sxs-lookup"><span data-stu-id="0fb32-155">LongCount</span></span>

<span data-ttu-id="0fb32-156">Zählt die Anzahl der Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fb32-156">Counts the number of elements in the collection.</span></span> <span data-ttu-id="0fb32-157">Sie können einen optionalen `Boolean` Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0fb32-157">You can supply an optional `Boolean` expression to count only the number of elements in the collection that satisfy a condition.</span></span> <span data-ttu-id="0fb32-158">Gibt das Ergebnis als zurück `Long` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-158">Returns the result as a `Long`.</span></span> <span data-ttu-id="0fb32-159">Ein Beispiel finden Sie unter der `Count` Aggregatfunktion.</span><span class="sxs-lookup"><span data-stu-id="0fb32-159">For an example, see the `Count` aggregate function.</span></span>

### <a name="max"></a><span data-ttu-id="0fb32-160">Max</span><span class="sxs-lookup"><span data-stu-id="0fb32-160">Max</span></span>

<span data-ttu-id="0fb32-161">Berechnet den maximalen Wert aus der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fb32-161">Computes the maximum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0fb32-162">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-162">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a><span data-ttu-id="0fb32-163">Min</span><span class="sxs-lookup"><span data-stu-id="0fb32-163">Min</span></span>

<span data-ttu-id="0fb32-164">Berechnet den minimalen Wert aus der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fb32-164">Computes the minimum value from the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0fb32-165">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-165">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a><span data-ttu-id="0fb32-166">SUM</span><span class="sxs-lookup"><span data-stu-id="0fb32-166">Sum</span></span>

<span data-ttu-id="0fb32-167">Berechnet die Summe aller Elemente in der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0fb32-167">Computes the sum of all elements in the collection, or computes a supplied expression for all elements in the collection.</span></span> <span data-ttu-id="0fb32-168">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fb32-168">The following is an example:</span></span>

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a><span data-ttu-id="0fb32-169">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fb32-169">Example</span></span>  

<span data-ttu-id="0fb32-170">Im folgenden Beispiel wird gezeigt, wie die- `Aggregate` Klausel zum Anwenden von Aggregatfunktionen auf ein Abfrageergebnis verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0fb32-170">The following example shows how to use the `Aggregate` clause to apply aggregate functions to a query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a><span data-ttu-id="0fb32-171">Erstellen von benutzerdefinierten Aggregatfunktionen</span><span class="sxs-lookup"><span data-stu-id="0fb32-171">Creating User-Defined Aggregate Functions</span></span>

 <span data-ttu-id="0fb32-172">Sie können eigene benutzerdefinierte Aggregatfunktionen in einen Abfrage Ausdruck einschließen, indem Sie dem Typ Erweiterungs Methoden hinzufügen <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="0fb32-172">You can include your own custom aggregate functions in a query expression by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> type.</span></span> <span data-ttu-id="0fb32-173">Die benutzerdefinierte Methode kann dann eine Berechnung oder einen Vorgang für die Aufzähl Bare-Auflistung ausführen, die auf die Aggregatfunktion verwiesen hat.</span><span class="sxs-lookup"><span data-stu-id="0fb32-173">Your custom method can then perform a calculation or operation on the enumerable collection that has referenced your aggregate function.</span></span> <span data-ttu-id="0fb32-174">Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Extension Methods (Erweiterungsmethoden)](../../programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="0fb32-174">For more information about extension methods, see [Extension Methods](../../programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
 <span data-ttu-id="0fb32-175">Das folgende Beispiel zeigt beispielsweise eine benutzerdefinierte Aggregatfunktion, die den Medianwert einer Auflistung von Zahlen berechnet.</span><span class="sxs-lookup"><span data-stu-id="0fb32-175">For example, the following example shows a custom aggregate function that calculates the median value of a collection of numbers.</span></span> <span data-ttu-id="0fb32-176">Es gibt zwei über Ladungen der `Median` Erweiterungsmethode.</span><span class="sxs-lookup"><span data-stu-id="0fb32-176">There are two overloads of the `Median` extension method.</span></span> <span data-ttu-id="0fb32-177">Die erste Überladung akzeptiert als Eingabe eine Auflistung vom Typ `IEnumerable(Of Double)` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-177">The first overload accepts, as input, a collection of type `IEnumerable(Of Double)`.</span></span> <span data-ttu-id="0fb32-178">Wenn die `Median` Aggregatfunktion für ein Abfragefeld vom Typ aufgerufen wird `Double` , wird diese Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0fb32-178">If the `Median` aggregate function is called for a query field of type `Double`, this method will be called.</span></span> <span data-ttu-id="0fb32-179">Der zweiten Überladung der- `Median` Methode können alle generischen Typen übergebenen werden.</span><span class="sxs-lookup"><span data-stu-id="0fb32-179">The second overload of the `Median` method can be passed any generic type.</span></span> <span data-ttu-id="0fb32-180">Die generische Überladung der- `Median` Methode nimmt einen zweiten Parameter an, der `Func(Of T, Double)` auf den Lambda-Ausdruck verweist, um einen Wert für einen Typ (aus einer Auflistung) als entsprechenden Wert des Typs zu projizieren `Double` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-180">The generic overload of the `Median` method takes a second parameter that references the `Func(Of T, Double)` lambda expression to project a value for a type (from a collection) as the corresponding value of type `Double`.</span></span> <span data-ttu-id="0fb32-181">Anschließend wird die Berechnung des Median Werts an die andere Überladung der- `Median` Methode delegiert.</span><span class="sxs-lookup"><span data-stu-id="0fb32-181">It then delegates the calculation of the median value to the other overload of the `Median` method.</span></span> <span data-ttu-id="0fb32-182">Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0fb32-182">For more information about lambda expressions, see [Lambda Expressions](../../programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 <span data-ttu-id="0fb32-183">Das folgende Beispiel zeigt Beispielabfragen, die die `Median` Aggregatfunktion für eine Auflistung vom Typ `Integer` und eine Auflistung vom Typ aufzurufen `Double` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-183">The following example shows sample queries that call the `Median` aggregate function on a collection of type `Integer`, and a collection of type `Double`.</span></span> <span data-ttu-id="0fb32-184">Die Abfrage, die die `Median` Aggregatfunktion für die Auflistung vom Typ aufruft, `Double` Ruft die Überladung der Methode auf, `Median` die als Eingabe eine Auflistung vom Typ akzeptiert `Double` .</span><span class="sxs-lookup"><span data-stu-id="0fb32-184">The query that calls the `Median` aggregate function on the collection of type `Double` calls the overload of the `Median` method that accepts, as input, a collection of type `Double`.</span></span> <span data-ttu-id="0fb32-185">Die Abfrage, die die `Median` Aggregatfunktion für die-Auflistung des Typs aufruft, `Integer` Ruft die generische Überladung der- `Median` Methode auf.</span><span class="sxs-lookup"><span data-stu-id="0fb32-185">The query that calls the `Median` aggregate function on the collection of type `Integer` calls the generic overload of the `Median` method.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="0fb32-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0fb32-186">See also</span></span>

- [<span data-ttu-id="0fb32-187">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fb32-187">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="0fb32-188">Abfragen</span><span class="sxs-lookup"><span data-stu-id="0fb32-188">Queries</span></span>](index.md)
- [<span data-ttu-id="0fb32-189">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="0fb32-189">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="0fb32-190">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="0fb32-190">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="0fb32-191">WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="0fb32-191">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="0fb32-192">Group By-Klausel</span><span class="sxs-lookup"><span data-stu-id="0fb32-192">Group By Clause</span></span>](group-by-clause.md)
