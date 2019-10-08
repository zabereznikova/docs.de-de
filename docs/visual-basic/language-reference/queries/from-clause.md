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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004779"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="f07f6-102">From-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f07f6-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="f07f6-103">Gibt eine oder mehrere Bereichs Variablen und eine abzufragende Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="f07f6-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f07f6-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="f07f6-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f07f6-105">Parts</span></span>  
  
|<span data-ttu-id="f07f6-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f07f6-106">Term</span></span>|<span data-ttu-id="f07f6-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f07f6-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="f07f6-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f07f6-108">Required.</span></span> <span data-ttu-id="f07f6-109">Eine *Bereichs Variable* , die verwendet wird, um die Elemente der Auflistung zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="f07f6-110">Eine Bereichs Variable wird verwendet, um auf die einzelnen Member des `collection` zu verweisen, während die Abfrage den `collection` durchläuft.</span><span class="sxs-lookup"><span data-stu-id="f07f6-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="f07f6-111">Muss ein Aufzähl Bare-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="f07f6-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="f07f6-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="f07f6-112">Optional.</span></span> <span data-ttu-id="f07f6-113">Der `element`-Typ.</span><span class="sxs-lookup"><span data-stu-id="f07f6-113">The type of `element`.</span></span> <span data-ttu-id="f07f6-114">Wenn keine `type` angegeben wird, wird der Typ von `element` von `collection` abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="f07f6-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="f07f6-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f07f6-115">Required.</span></span> <span data-ttu-id="f07f6-116">Verweist auf die Auflistung, die abgefragt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f07f6-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="f07f6-117">Muss ein Aufzähl Bare-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="f07f6-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f07f6-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f07f6-118">Remarks</span></span>  
 <span data-ttu-id="f07f6-119">Die `From`-Klausel wird verwendet, um die Quelldaten für eine Abfrage und die Variablen zu identifizieren, die verwendet werden, um auf ein Element aus der Quell Auflistung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="f07f6-120">Diese Variablen werden als *Bereichs Variablen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f07f6-120">These variables are called *range variables*.</span></span> <span data-ttu-id="f07f6-121">Die `From`-Klausel ist für eine Abfrage erforderlich, außer wenn die `Aggregate`-Klausel verwendet wird, um eine Abfrage zu identifizieren, die nur aggregierte Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f07f6-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="f07f6-122">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="f07f6-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="f07f6-123">Sie können mehrere `From`-Klauseln in einer Abfrage angeben, um mehrere Sammlungen zu identifizieren, die verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="f07f6-124">Wenn mehrere Sammlungen angegeben werden, werden Sie unabhängig voneinander durchlaufen, oder Sie können Sie verknüpfen, wenn Sie verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="f07f6-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="f07f6-125">Sie können Auflistungen implizit mit der `Select`-Klausel oder explizit mithilfe der Klauseln `Join` oder `Group Join` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="f07f6-126">Als Alternative können Sie mehrere Bereichs Variablen und Auflistungen in einer einzigen `From`-Klausel angeben, wobei jede verknüpfte Bereichs Variable und Auflistung durch ein Komma von anderen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="f07f6-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="f07f6-127">Das folgende Codebeispiel zeigt beide Syntax Optionen für die `From`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f07f6-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="f07f6-128">Die `From`-Klausel definiert den Gültigkeitsbereich einer Abfrage, die dem Bereich einer `For`-Schleife ähnelt.</span><span class="sxs-lookup"><span data-stu-id="f07f6-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="f07f6-129">Daher muss jede `element`-Bereichs Variable im Gültigkeitsbereich einer Abfrage einen eindeutigen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="f07f6-130">Da Sie mehrere `From`-Klauseln für eine Abfrage angeben können, können nachfolgende `From`-Klauseln auf Bereichs Variablen in der `From`-Klausel verweisen, oder Sie können in einer früheren `From`-Klausel auf Bereichs Variablen verweisen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="f07f6-131">Das folgende Beispiel zeigt beispielsweise eine `From`-Klausel, bei der die Auflistung in der zweiten Klausel auf einer Eigenschaft der Bereichs Variablen in der ersten Klausel basiert.</span><span class="sxs-lookup"><span data-stu-id="f07f6-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="f07f6-132">Auf jede `From`-Klausel kann eine beliebige Kombination zusätzlicher Abfrage Klauseln folgen, um die Abfrage zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="f07f6-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="f07f6-133">Es gibt folgende Möglichkeiten, um die Abfrage zu verfeinern:</span><span class="sxs-lookup"><span data-stu-id="f07f6-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="f07f6-134">Kombinieren Sie mehrere Auflistungen implizit mithilfe der Klauseln `From` und `Select` oder explizit mithilfe der Klauseln `Join` oder `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="f07f6-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="f07f6-135">Verwenden Sie die `Where`-Klausel, um das Abfrageergebnis zu filtern.</span><span class="sxs-lookup"><span data-stu-id="f07f6-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="f07f6-136">Sortieren Sie das Ergebnis mithilfe der `Order By`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f07f6-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="f07f6-137">Gruppieren Sie ähnliche Ergebnisse mit der `Group By`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="f07f6-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="f07f6-138">Verwenden Sie die `Aggregate`-Klausel, um Aggregatfunktionen zu identifizieren, die für das gesamte Abfrageergebnis ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f07f6-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="f07f6-139">Verwenden Sie die `Let`-Klausel, um eine Iterations Variable einzuführen, deren Wert durch einen Ausdruck anstelle einer Auflistung bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="f07f6-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="f07f6-140">Verwenden Sie die `Distinct`-Klausel, um doppelte Abfrageergebnisse zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="f07f6-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="f07f6-141">Identifizieren Sie Teile des Ergebnisses, die zurückgegeben werden sollen, indem Sie die `Skip`-, `Take`-, `Skip While`-und `Take While`-Klauseln verwenden.</span><span class="sxs-lookup"><span data-stu-id="f07f6-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f07f6-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f07f6-142">Example</span></span>  
 <span data-ttu-id="f07f6-143">Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um eine Bereichs Variable `cust` für jedes `Customer`-Objekt in der `customers`-Auflistung zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f07f6-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="f07f6-144">Die `Where`-Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="f07f6-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="f07f6-145">Die `For Each`-Schleife zeigt den Firmennamen für jeden Kunden im Abfrageergebnis an.</span><span class="sxs-lookup"><span data-stu-id="f07f6-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="f07f6-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f07f6-146">See also</span></span>

- [<span data-ttu-id="f07f6-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="f07f6-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="f07f6-148">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f07f6-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="f07f6-149">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f07f6-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="f07f6-150">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f07f6-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="f07f6-151">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="f07f6-152">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="f07f6-153">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="f07f6-154">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="f07f6-155">Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="f07f6-156">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="f07f6-157">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="f07f6-158">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="f07f6-159">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="f07f6-160">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="f07f6-161">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="f07f6-162">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="f07f6-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
