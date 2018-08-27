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
ms.openlocfilehash: 71573de48cc51c48291fc4b82a0628d2d0f96caa
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932487"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="0cfa3-102">From-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cfa3-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="0cfa3-103">Gibt einen oder mehrere Bereichsvariable und eine Abfragesammlung an.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cfa3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cfa3-104">Syntax</span></span>  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="0cfa3-105">Teile</span><span class="sxs-lookup"><span data-stu-id="0cfa3-105">Parts</span></span>  
  
|<span data-ttu-id="0cfa3-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0cfa3-106">Term</span></span>|<span data-ttu-id="0cfa3-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0cfa3-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="0cfa3-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-108">Required.</span></span> <span data-ttu-id="0cfa3-109">Ein *Bereichsvariable* verwendet, um das Durchlaufen der Elemente der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="0cfa3-110">Eine Bereichsvariable wird verwendet, um auf jedes Element finden Sie unter den `collection` wie die Abfrage durchläuft die `collection`.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="0cfa3-111">Muss es sich um ein aufzählbarer Typ sein.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="0cfa3-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-112">Optional.</span></span> <span data-ttu-id="0cfa3-113">Der `element`-Typ.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-113">The type of `element`.</span></span> <span data-ttu-id="0cfa3-114">Wenn kein `type` angegeben ist, den Typ des `element` von hergeleitet `collection`.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="0cfa3-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-115">Required.</span></span> <span data-ttu-id="0cfa3-116">Bezieht sich auf die Auflistung, die abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="0cfa3-117">Muss es sich um ein aufzählbarer Typ sein.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cfa3-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cfa3-118">Remarks</span></span>  
 <span data-ttu-id="0cfa3-119">Die `From` -Klausel wird verwendet, identifizieren Sie die Quelldaten für eine Abfrage und die Variablen, die zum Verweisen auf ein Element aus der Auflistung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="0cfa3-120">Diese Variablen heißen *Bereichsvariablen*.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-120">These variables are called *range variables*.</span></span> <span data-ttu-id="0cfa3-121">Die `From` -Klausel ist erforderlich für eine Abfrage, außer wenn die `Aggregate` -Klausel wird verwendet, um eine Abfrage zu identifizieren, dass gibt nur die Ergebnisse aggregiert.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="0cfa3-122">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="0cfa3-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="0cfa3-123">Sie können angeben, dass mehrere `From` Klauseln in einer Abfrage zum Identifizieren von mehreren Sammlungen verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="0cfa3-124">Wenn mehrere Sammlungen angegeben werden, sie einzeln durchlaufen werden, oder Sie können diese verknüpfen, wenn diese verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="0cfa3-125">Sie können Sammlungen implizit verknüpfen, indem die `Select` -Klausel, oder explizit durch Verwenden der `Join` oder `Group Join` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="0cfa3-126">Als Alternative können Sie mehrere Bereichsvariablen und Sammlungen angeben, in einem einzelnen `From` -Klausel, wobei alle entsprechenden Range-Variable und Sammlungen, die durch ein Komma voneinander getrennt.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="0cfa3-127">Im folgenden Codebeispiel wird veranschaulicht, beide Optionen zur Abfragesyntax für die `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 <span data-ttu-id="0cfa3-128">Die `From` -Klausel definiert den Bereich einer Abfrage, der in den Bereich der ähnelt einem `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="0cfa3-129">Aus diesem Grund jede `element` Bereichsvariablen im Bereich einer Abfrage muss einen eindeutigen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="0cfa3-130">Da es sich bei Angabe mehrerer `From` Klauseln für eine Abfrage, die nachfolgenden `From` Klauseln können Bereichsvariablen in finden Sie unter den `From` -Klausel, oder sie können auf Bereichsvariablen in einem vorherigen verweisen `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="0cfa3-131">Das folgende Beispiel zeigt z. B. eine geschachtelte `From` Klausel, in die Auflistung in der zweiten Klausel auf eine Eigenschaft der Bereichsvariablen in der ersten Klausel basiert.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 <span data-ttu-id="0cfa3-132">Jede `From` Klausel kann eine beliebige Kombination von zusätzliche Abfrageklauseln, um die Abfrage zu verfeinern folgen.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="0cfa3-133">Sie können die Abfrage optimieren, es gibt folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="0cfa3-133">You can refine the query in the following ways:</span></span>  
  
-   <span data-ttu-id="0cfa3-134">Kombinieren Sie mehrere Sammlungen implizit mithilfe der `From` und `Select` -Klauseln, oder explizit durch Verwenden der `Join` oder `Group Join` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
-   <span data-ttu-id="0cfa3-135">Verwenden der `Where` -Klausel, um das Abfrageergebnis zu filtern.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-135">Use the `Where` clause to filter the query result.</span></span>  
  
-   <span data-ttu-id="0cfa3-136">Sortieren des Ergebnisses mithilfe der `Order By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-136">Sort the result by using the `Order By` clause.</span></span>  
  
-   <span data-ttu-id="0cfa3-137">Gruppieren ähnliche Ergebnisse mithilfe der `Group By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-137">Group similar results together by using the `Group By` clause.</span></span>  
  
-   <span data-ttu-id="0cfa3-138">Verwenden der `Aggregate` -Klausel, um Aggregatfunktionen für das Ergebnis für die gesamte Abfrage ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
-   <span data-ttu-id="0cfa3-139">Verwenden der `Let` -Klausel, um eine Iterationsvariable eingeführt, deren Wert durch einen Ausdruck anstatt einer Sammlung festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
-   <span data-ttu-id="0cfa3-140">Verwenden der `Distinct` -Klausel, um doppelte Abfrageergebnisse ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
-   <span data-ttu-id="0cfa3-141">Identifizieren Sie Teile des Ergebnisses zurückgegeben mit der `Skip`, `Take`, `Skip While`, und `Take While` Klauseln.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cfa3-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-142">Example</span></span>  
 <span data-ttu-id="0cfa3-143">Der folgende Abfrageausdruck verwendet eine `From` -Klausel, um eine Bereichsvariable deklarieren `cust` für jede `Customer` -Objekt in der `customers` Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="0cfa3-144">Die `Where` -Klausel verwendet die Bereichsvariable, um die Ausgabe auf Kunden aus den angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="0cfa3-145">Die `For Each` -Schleife zeigt den Firmennamen für jeden Kunden in den Abfrageergebnissen.</span><span class="sxs-lookup"><span data-stu-id="0cfa3-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0cfa3-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cfa3-146">See Also</span></span>  
 [<span data-ttu-id="0cfa3-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="0cfa3-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)  
 [<span data-ttu-id="0cfa3-148">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0cfa3-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="0cfa3-149">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0cfa3-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [<span data-ttu-id="0cfa3-150">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0cfa3-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="0cfa3-151">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)  
 [<span data-ttu-id="0cfa3-152">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="0cfa3-153">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [<span data-ttu-id="0cfa3-154">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [<span data-ttu-id="0cfa3-155">Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="0cfa3-156">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="0cfa3-157">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [<span data-ttu-id="0cfa3-158">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)  
 [<span data-ttu-id="0cfa3-159">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [<span data-ttu-id="0cfa3-160">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)  
 [<span data-ttu-id="0cfa3-161">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [<span data-ttu-id="0cfa3-162">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="0cfa3-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
