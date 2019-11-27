---
title: From-Klausel
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
ms.openlocfilehash: a63fb41fc2b0ad885acf76ad5d56e446922f5b90
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343775"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="d2727-102">From-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2727-102">From Clause (Visual Basic)</span></span>
<span data-ttu-id="d2727-103">Gibt eine oder mehrere Bereichs Variablen und eine abzufragende Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="d2727-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2727-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2727-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="d2727-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="d2727-105">Parts</span></span>  
  
|<span data-ttu-id="d2727-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="d2727-106">Term</span></span>|<span data-ttu-id="d2727-107">Definition</span><span class="sxs-lookup"><span data-stu-id="d2727-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="d2727-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="d2727-108">Required.</span></span> <span data-ttu-id="d2727-109">Eine *Bereichs Variable* , die verwendet wird, um die Elemente der Auflistung zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="d2727-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="d2727-110">Eine Bereichs Variable wird verwendet, um auf die einzelnen Member des `collection` zu verweisen, während die Abfrage die `collection`durchläuft.</span><span class="sxs-lookup"><span data-stu-id="d2727-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="d2727-111">Muss ein Aufzähl Bare-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="d2727-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="d2727-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="d2727-112">Optional.</span></span> <span data-ttu-id="d2727-113">Der `element`-Typ.</span><span class="sxs-lookup"><span data-stu-id="d2727-113">The type of `element`.</span></span> <span data-ttu-id="d2727-114">Wenn keine `type` angegeben wird, wird der Typ der `element` von `collection`abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="d2727-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="d2727-115">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="d2727-115">Required.</span></span> <span data-ttu-id="d2727-116">Verweist auf die Auflistung, die abgefragt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2727-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="d2727-117">Muss ein Aufzähl Bare-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="d2727-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2727-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2727-118">Remarks</span></span>  
 <span data-ttu-id="d2727-119">Die `From`-Klausel wird verwendet, um die Quelldaten für eine Abfrage und die Variablen zu identifizieren, die verwendet werden, um auf ein Element aus der Quell Auflistung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d2727-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="d2727-120">Diese Variablen werden als *Bereichs Variablen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d2727-120">These variables are called *range variables*.</span></span> <span data-ttu-id="d2727-121">Die `From`-Klausel ist für eine Abfrage erforderlich, außer wenn die `Aggregate`-Klausel verwendet wird, um eine Abfrage zu identifizieren, die nur aggregierte Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d2727-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="d2727-122">Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="d2727-122">For more information, see [Aggregate Clause](../../../visual-basic/language-reference/queries/aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="d2727-123">Sie können mehrere `From` Klauseln in einer Abfrage angeben, um mehrere Sammlungen zu identifizieren, die verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2727-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="d2727-124">Wenn mehrere Sammlungen angegeben werden, werden Sie unabhängig voneinander durchlaufen, oder Sie können Sie verknüpfen, wenn Sie verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="d2727-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="d2727-125">Sie können Auflistungen implizit mit der `Select`-Klausel oder explizit mithilfe der Klauseln `Join` oder `Group Join` verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="d2727-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="d2727-126">Als Alternative können Sie mehrere Bereichs Variablen und Auflistungen in einer einzigen `From`-Klausel angeben, wobei jede zugehörige Bereichs Variable und Auflistung durch ein Komma von den anderen getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="d2727-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="d2727-127">Das folgende Codebeispiel zeigt beide Syntax Optionen für die `From`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="d2727-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="d2727-128">Die `From`-Klausel definiert den Gültigkeitsbereich einer Abfrage, die dem Bereich einer `For` Schleife ähnelt.</span><span class="sxs-lookup"><span data-stu-id="d2727-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="d2727-129">Daher muss jede `element` Range-Variable im Gültigkeitsbereich einer Abfrage einen eindeutigen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d2727-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="d2727-130">Da Sie mehrere `From` Klauseln für eine Abfrage angeben können, können nachfolgende `From` Klauseln auf Bereichs Variablen in der `From`-Klausel verweisen, oder Sie können in einer früheren `From`-Klausel auf Bereichs Variablen verweisen.</span><span class="sxs-lookup"><span data-stu-id="d2727-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="d2727-131">Das folgende Beispiel zeigt beispielsweise eine `From`-Klausel, bei der die Auflistung in der zweiten Klausel auf einer Eigenschaft der Bereichs Variablen in der ersten Klausel basiert.</span><span class="sxs-lookup"><span data-stu-id="d2727-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="d2727-132">Auf jede `From`-Klausel kann eine beliebige Kombination zusätzlicher Abfrage Klauseln folgen, um die Abfrage zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="d2727-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="d2727-133">Es gibt folgende Möglichkeiten, um die Abfrage zu verfeinern:</span><span class="sxs-lookup"><span data-stu-id="d2727-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="d2727-134">Kombinieren Sie mehrere Auflistungen implizit mithilfe der Klauseln `From` und `Select` oder explizit mithilfe der Klauseln `Join` oder `Group Join`.</span><span class="sxs-lookup"><span data-stu-id="d2727-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="d2727-135">Verwenden Sie die `Where`-Klausel, um das Abfrageergebnis zu filtern.</span><span class="sxs-lookup"><span data-stu-id="d2727-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="d2727-136">Sortieren Sie das Ergebnis mithilfe der `Order By`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="d2727-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="d2727-137">Gruppieren Sie ähnliche Ergebnisse mit der `Group By`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="d2727-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="d2727-138">Verwenden Sie die `Aggregate`-Klausel, um Aggregatfunktionen zu identifizieren, die für das gesamte Abfrageergebnis ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2727-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="d2727-139">Verwenden Sie die `Let`-Klausel, um eine Iterations Variable einzuführen, deren Wert durch einen Ausdruck anstelle einer Auflistung bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="d2727-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="d2727-140">Verwenden Sie die `Distinct`-Klausel, um doppelte Abfrageergebnisse zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="d2727-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="d2727-141">Identifizieren Sie mithilfe der Klauseln `Skip`, `Take`, `Skip While`und `Take While` Teile des Ergebnisses, das zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="d2727-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2727-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2727-142">Example</span></span>  
 <span data-ttu-id="d2727-143">Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um für jedes `Customer`-Objekt in der `customers` Auflistung eine Bereichs Variable `cust` zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="d2727-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="d2727-144">Die `Where`-Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="d2727-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="d2727-145">Die `For Each`-Schleife zeigt den Firmennamen für jeden Kunden im Abfrageergebnis an.</span><span class="sxs-lookup"><span data-stu-id="d2727-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="d2727-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2727-146">See also</span></span>

- [<span data-ttu-id="d2727-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="d2727-147">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="d2727-148">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2727-148">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="d2727-149">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d2727-149">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="d2727-150">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d2727-150">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="d2727-151">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-151">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="d2727-152">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-152">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
- [<span data-ttu-id="d2727-153">Aggregate-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-153">Aggregate Clause</span></span>](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [<span data-ttu-id="d2727-154">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-154">Distinct Clause</span></span>](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [<span data-ttu-id="d2727-155">Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-155">Join Clause</span></span>](../../../visual-basic/language-reference/queries/join-clause.md)
- [<span data-ttu-id="d2727-156">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-156">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="d2727-157">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-157">Order By Clause</span></span>](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="d2727-158">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-158">Let Clause</span></span>](../../../visual-basic/language-reference/queries/let-clause.md)
- [<span data-ttu-id="d2727-159">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-159">Skip Clause</span></span>](../../../visual-basic/language-reference/queries/skip-clause.md)
- [<span data-ttu-id="d2727-160">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-160">Take Clause</span></span>](../../../visual-basic/language-reference/queries/take-clause.md)
- [<span data-ttu-id="d2727-161">Skip While-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-161">Skip While Clause</span></span>](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [<span data-ttu-id="d2727-162">Take While-Klausel</span><span class="sxs-lookup"><span data-stu-id="d2727-162">Take While Clause</span></span>](../../../visual-basic/language-reference/queries/take-while-clause.md)
