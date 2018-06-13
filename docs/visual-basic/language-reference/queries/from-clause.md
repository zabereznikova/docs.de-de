---
title: From-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 1f113444efae83de7d299db330593937c7800bb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604717"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="ebd51-102">From-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ebd51-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="ebd51-103">Gibt an, eine oder mehrere Bereichsvariablen und eine Auflistung Abfrage.</span><span class="sxs-lookup"><span data-stu-id="ebd51-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebd51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebd51-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="ebd51-105">Teile</span><span class="sxs-lookup"><span data-stu-id="ebd51-105">Parts</span></span>  
  
|<span data-ttu-id="ebd51-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="ebd51-106">Term</span></span>|<span data-ttu-id="ebd51-107">Definition</span><span class="sxs-lookup"><span data-stu-id="ebd51-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="ebd51-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ebd51-108">Required.</span></span> <span data-ttu-id="ebd51-109">Ein *Bereichsvariable* zum Durchlaufen der Elemente der Auflistung verwendet.</span><span class="sxs-lookup"><span data-stu-id="ebd51-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="ebd51-110">Eine Bereichsvariable wird verwendet, um auf jedes Element einer finden Sie unter der `collection` wie die Abfrage durchläuft die `collection`.</span><span class="sxs-lookup"><span data-stu-id="ebd51-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="ebd51-111">Ein aufzählbarer Typ muss sein.</span><span class="sxs-lookup"><span data-stu-id="ebd51-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="ebd51-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="ebd51-112">Optional.</span></span> <span data-ttu-id="ebd51-113">Der `element`-Typ.</span><span class="sxs-lookup"><span data-stu-id="ebd51-113">The type of `element`.</span></span> <span data-ttu-id="ebd51-114">Wenn kein `type` angegeben wird, den Typ des `element` von hergeleitet `collection`.</span><span class="sxs-lookup"><span data-stu-id="ebd51-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="ebd51-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ebd51-115">Required.</span></span> <span data-ttu-id="ebd51-116">Bezieht sich auf die Auflistung abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="ebd51-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="ebd51-117">Ein aufzählbarer Typ muss sein.</span><span class="sxs-lookup"><span data-stu-id="ebd51-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebd51-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ebd51-118">Remarks</span></span>  
 <span data-ttu-id="ebd51-119">Die `From` -Klausel wird verwendet, identifizieren Sie die Quelldaten für eine Abfrage und die Variablen, die zum Verweisen auf ein Element aus der Auflistung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebd51-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="ebd51-120">Diese Variablen heißen *Bereichsvariablen*.</span><span class="sxs-lookup"><span data-stu-id="ebd51-120">These variables are called *range variables*.</span></span> <span data-ttu-id="ebd51-121">Die `From` -Klausel ist erforderlich für eine Abfrage, außer wenn die `Aggregate` -Klausel wird verwendet, um eine Abfrage zu identifizieren, gibt nur Ergebnisse aggregiert.</span><span class="sxs-lookup"><span data-stu-id="ebd51-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="ebd51-122">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="ebd51-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="ebd51-123">Sie können angeben, dass mehrere `From` Klauseln in einer Abfrage zur Identifizierung von mehreren Sammlungen verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebd51-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="ebd51-124">Wenn mehrere Sammlungen angegeben werden, sie werden unabhängig voneinander durchlaufen, oder können hinzugefügt werden, wenn sie verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="ebd51-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="ebd51-125">Sie können Sammlungen implizit verknüpfen, indem die `Select` -Klausel, oder explizit mit der `Join` oder `Group Join` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="ebd51-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="ebd51-126">Als Alternative können Sie mehrere Bereichsvariablen und Sammlungen angeben, in einer einzelnen `From` -Klausel, wobei alle verwandten Bereichsvariable und Sammlungen, die von den anderen durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="ebd51-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="ebd51-127">Im folgenden Codebeispiel wird gezeigt, beide Optionen zur Abfragesyntax für die `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="ebd51-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="ebd51-128">Die `From` -Klausel definiert den Bereich einer Abfrage, der dem Bereich der ähnelt einer `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="ebd51-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="ebd51-129">Aus diesem Grund jede `element` Bereichsvariable im Bereich einer Abfrage muss einen eindeutigen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ebd51-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="ebd51-130">Da es sich bei Angabe mehrerer `From` Klauseln für eine Abfrage, die nachfolgenden `From` Klauseln können finden Sie in der Bereichsvariablen in der `From` -Klausel, oder sie können auf Bereichsvariablen finden Sie in einem vorherigen `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="ebd51-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="ebd51-131">Das folgende Beispiel zeigt beispielsweise eine geschachtelte `From` Klausel, in die Auflistung in der zweiten Klausel auf eine Eigenschaft der Bereichsvariablen in der ersten Klausel basiert.</span><span class="sxs-lookup"><span data-stu-id="ebd51-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="ebd51-132">Jede `From` Klausel kann eine beliebige Kombination von zusätzliche Abfrageklauseln zum Verfeinern der Abfrage folgen.</span><span class="sxs-lookup"><span data-stu-id="ebd51-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="ebd51-133">Sie können die Abfrage folgendermaßen optimieren:</span><span class="sxs-lookup"><span data-stu-id="ebd51-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="ebd51-134">Kombinieren mehrerer Sammlungen implizit mithilfe der `From` und `Select` Klauseln, oder explizit mit der `Join` oder `Group Join` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="ebd51-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="ebd51-135">Verwenden der `Where` -Klausel, um das Ergebnis der Abfrage zu filtern.</span><span class="sxs-lookup"><span data-stu-id="ebd51-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="ebd51-136">Sortieren des Ergebnisses mithilfe der `Order By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="ebd51-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="ebd51-137">Gruppieren ähnlicher Ergebnisse mithilfe der `Group By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="ebd51-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="ebd51-138">Verwenden der `Aggregate` -Klausel, um Aggregatfunktionen für das gesamte Abfrageergebnis ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ebd51-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="ebd51-139">Verwenden der `Let` -Klausel, um eine Iterationsvariable einführen, deren Wert durch einen Ausdruck statt einer Auflistung festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ebd51-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="ebd51-140">Verwenden der `Distinct` -Klausel, um doppelte Abfrageergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ebd51-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="ebd51-141">Identifiziert DQS Teile des Ergebnisses zurückzugebenden mithilfe der `Skip`, `Take`, `Skip While`, und `Take While` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="ebd51-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebd51-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebd51-142">Example</span></span>  
 <span data-ttu-id="ebd51-143">Die folgende Abfrage Ausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` Objekt in der `customers` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="ebd51-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="ebd51-144">Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="ebd51-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="ebd51-145">Die `For Each` Schleife der Firmenname für jeden Kunden in den Abfrageergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebd51-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ebd51-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebd51-146">See Also</span></span>  
 [<span data-ttu-id="ebd51-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="ebd51-147">Queries</span></span>](../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="ebd51-148">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ebd51-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="ebd51-149">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ebd51-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="ebd51-150">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ebd51-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="ebd51-151">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="ebd51-152">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="ebd51-153">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="ebd51-154">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="ebd51-155">Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="ebd51-156">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="ebd51-157">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="ebd51-158">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="ebd51-159">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="ebd51-160">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="ebd51-161">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="ebd51-162">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="ebd51-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
