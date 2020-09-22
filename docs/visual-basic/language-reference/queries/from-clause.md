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
ms.openlocfilehash: 120ba6da11bffc3a0e81873d1fd606633724723d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875259"
---
# <a name="from-clause-visual-basic"></a><span data-ttu-id="4d827-102">From-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d827-102">From Clause (Visual Basic)</span></span>

<span data-ttu-id="4d827-103">Gibt eine oder mehrere Bereichs Variablen und eine abzufragende Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="4d827-103">Specifies one or more range variables and a collection to query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d827-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d827-104">Syntax</span></span>  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4d827-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="4d827-105">Parts</span></span>  
  
|<span data-ttu-id="4d827-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="4d827-106">Term</span></span>|<span data-ttu-id="4d827-107">Definition</span><span class="sxs-lookup"><span data-stu-id="4d827-107">Definition</span></span>|  
|---|---|  
|`element`|<span data-ttu-id="4d827-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d827-108">Required.</span></span> <span data-ttu-id="4d827-109">Eine *Bereichs Variable* , die verwendet wird, um die Elemente der Auflistung zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="4d827-109">A *range variable* used to iterate through the elements of the collection.</span></span> <span data-ttu-id="4d827-110">Eine Bereichs Variable wird verwendet, um auf die einzelnen Member von zu verweisen, `collection` während die Abfrage durchläuft `collection` .</span><span class="sxs-lookup"><span data-stu-id="4d827-110">A range variable is used to refer to each member of the `collection` as the query iterates through the `collection`.</span></span> <span data-ttu-id="4d827-111">Muss ein Aufzähl Bare-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="4d827-111">Must be an enumerable type.</span></span>|  
|`type`|<span data-ttu-id="4d827-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="4d827-112">Optional.</span></span> <span data-ttu-id="4d827-113">Der `element`-Typ.</span><span class="sxs-lookup"><span data-stu-id="4d827-113">The type of `element`.</span></span> <span data-ttu-id="4d827-114">Wenn kein `type` angegeben wird, wird der Typ von `element` aus abgeleitet `collection` .</span><span class="sxs-lookup"><span data-stu-id="4d827-114">If no `type` is specified, the type of `element` is inferred from `collection`.</span></span>|  
|`collection`|<span data-ttu-id="4d827-115">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4d827-115">Required.</span></span> <span data-ttu-id="4d827-116">Verweist auf die Auflistung, die abgefragt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d827-116">Refers to the collection to be queried.</span></span> <span data-ttu-id="4d827-117">Muss ein Aufzähl Bare-Typ sein.</span><span class="sxs-lookup"><span data-stu-id="4d827-117">Must be an enumerable type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d827-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4d827-118">Remarks</span></span>  

 <span data-ttu-id="4d827-119">Die `From` -Klausel wird verwendet, um die Quelldaten für eine Abfrage und die Variablen zu identifizieren, die verwendet werden, um auf ein Element aus der Quell Auflistung zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="4d827-119">The `From` clause is used to identify the source data for a query and the variables that are used to refer to an element from the source collection.</span></span> <span data-ttu-id="4d827-120">Diese Variablen werden als *Bereichs Variablen*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4d827-120">These variables are called *range variables*.</span></span> <span data-ttu-id="4d827-121">Die- `From` Klausel ist für eine Abfrage erforderlich, außer wenn die- `Aggregate` Klausel verwendet wird, um eine Abfrage zu identifizieren, die nur aggregierte Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4d827-121">The `From` clause is required for a query, except when the `Aggregate` clause is used to identify a query that returns only aggregated results.</span></span> <span data-ttu-id="4d827-122">Weitere Informationen finden Sie unter [Aggregate-Klausel](aggregate-clause.md).</span><span class="sxs-lookup"><span data-stu-id="4d827-122">For more information, see [Aggregate Clause](aggregate-clause.md).</span></span>  
  
 <span data-ttu-id="4d827-123">Sie können mehrere `From` Klauseln in einer Abfrage angeben, um mehrere Sammlungen zu identifizieren, die verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d827-123">You can specify multiple `From` clauses in a query to identify multiple collections to be joined.</span></span> <span data-ttu-id="4d827-124">Wenn mehrere Sammlungen angegeben werden, werden Sie unabhängig voneinander durchlaufen, oder Sie können Sie verknüpfen, wenn Sie verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="4d827-124">When multiple collections are specified, they are iterated over independently, or you can join them if they are related.</span></span> <span data-ttu-id="4d827-125">Sie können Auflistungen implizit mithilfe der- `Select` Klausel oder explizit mithilfe der- `Join` oder- `Group Join` Klauseln verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="4d827-125">You can join collections implicitly by using the `Select` clause, or explicitly by using the `Join` or `Group Join` clauses.</span></span> <span data-ttu-id="4d827-126">Als Alternative können Sie mehrere Bereichs Variablen und Auflistungen in einer einzelnen `From` Klausel angeben, wobei jede verknüpfte Bereichs Variable und Auflistung durch ein Komma von den anderen getrennt getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="4d827-126">As an alternative, you can specify multiple range variables and collections in a single `From` clause, with each related range variable and collection separated from the others by a comma.</span></span> <span data-ttu-id="4d827-127">Das folgende Codebeispiel zeigt beide Syntax Optionen für die- `From` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4d827-127">The following code example shows both syntax options for the `From` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 <span data-ttu-id="4d827-128">Die- `From` Klausel definiert den Gültigkeitsbereich einer Abfrage, die dem Gültigkeitsbereich einer- `For` Schleife ähnelt.</span><span class="sxs-lookup"><span data-stu-id="4d827-128">The `From` clause defines the scope of a query, which is similar to the scope of a `For` loop.</span></span> <span data-ttu-id="4d827-129">Daher muss jede `element` Bereichs Variable im Gültigkeitsbereich einer Abfrage einen eindeutigen Namen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4d827-129">Therefore, each `element` range variable in the scope of a query must have a unique name.</span></span> <span data-ttu-id="4d827-130">Da Sie mehrere `From` Klauseln für eine Abfrage angeben können, können nachfolgende `From` Klauseln auf Bereichs Variablen in der- `From` Klausel verweisen, oder Sie können in einer vorherigen Klausel auf Bereichs Variablen verweisen `From` .</span><span class="sxs-lookup"><span data-stu-id="4d827-130">Because you can specify multiple `From` clauses for a query, subsequent `From` clauses can refer to range variables in the `From` clause, or they can refer to range variables in a previous `From` clause.</span></span> <span data-ttu-id="4d827-131">Das folgende Beispiel zeigt beispielsweise eine-Klausel, in der die-Auflistung `From` in der zweiten-Klausel auf eine Eigenschaft der Bereichs Variablen in der ersten Klausel basiert.</span><span class="sxs-lookup"><span data-stu-id="4d827-131">For example, the following example shows a nested `From` clause where the collection in the second clause is based on a property of the range variable in the first clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 <span data-ttu-id="4d827-132">`From`Auf jede Klausel kann eine beliebige Kombination zusätzlicher Abfrage Klauseln folgen, um die Abfrage zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="4d827-132">Each `From` clause can be followed by any combination of additional query clauses to refine the query.</span></span> <span data-ttu-id="4d827-133">Es gibt folgende Möglichkeiten, um die Abfrage zu verfeinern:</span><span class="sxs-lookup"><span data-stu-id="4d827-133">You can refine the query in the following ways:</span></span>  
  
- <span data-ttu-id="4d827-134">Kombinieren Sie mehrere Auflistungen implizit mithilfe der `From` -Klausel und der- `Select` Klausel oder explizit mit der- `Join` oder- `Group Join` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4d827-134">Combine multiple collections implicitly by using the `From` and `Select` clauses, or explicitly by using the `Join` or `Group Join` clauses.</span></span>  
  
- <span data-ttu-id="4d827-135">Verwenden Sie die- `Where` Klausel, um das Abfrageergebnis zu filtern.</span><span class="sxs-lookup"><span data-stu-id="4d827-135">Use the `Where` clause to filter the query result.</span></span>  
  
- <span data-ttu-id="4d827-136">Sortieren Sie das Ergebnis mithilfe der- `Order By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4d827-136">Sort the result by using the `Order By` clause.</span></span>  
  
- <span data-ttu-id="4d827-137">Gruppieren Sie ähnliche Ergebnisse mit der- `Group By` Klausel.</span><span class="sxs-lookup"><span data-stu-id="4d827-137">Group similar results together by using the `Group By` clause.</span></span>  
  
- <span data-ttu-id="4d827-138">Verwenden Sie die- `Aggregate` Klausel, um Aggregatfunktionen zu identifizieren, die für das gesamte Abfrageergebnis ausgewertet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4d827-138">Use the `Aggregate` clause to identify aggregate functions to evaluate for the whole query result.</span></span>  
  
- <span data-ttu-id="4d827-139">Verwenden Sie die- `Let` Klausel, um eine Iterations Variable einzuführen, deren Wert durch einen Ausdruck anstelle einer Auflistung bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="4d827-139">Use the `Let` clause to introduce an iteration variable whose value is determined by an expression instead of a collection.</span></span>  
  
- <span data-ttu-id="4d827-140">Verwenden Sie die- `Distinct` Klausel, um doppelte Abfrageergebnisse zu ignorieren.</span><span class="sxs-lookup"><span data-stu-id="4d827-140">Use the `Distinct` clause to ignore duplicate query results.</span></span>  
  
- <span data-ttu-id="4d827-141">Identifizieren Sie mithilfe der `Skip` `Take` Klauseln,, und Teile des Ergebnisses, das zurückgegeben werden soll `Skip While` `Take While` .</span><span class="sxs-lookup"><span data-stu-id="4d827-141">Identify parts of the result to return by using the `Skip`, `Take`, `Skip While`, and `Take While` clauses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d827-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d827-142">Example</span></span>  

 <span data-ttu-id="4d827-143">Der folgende Abfrage Ausdruck verwendet eine- `From` Klausel, um eine Bereichs Variable `cust` für jedes `Customer` Objekt in der Auflistung zu deklarieren `customers` .</span><span class="sxs-lookup"><span data-stu-id="4d827-143">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="4d827-144">Die- `Where` Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="4d827-144">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="4d827-145">In der- `For Each` Schleife wird der Firmenname für jeden Kunden im Abfrageergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d827-145">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="4d827-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d827-146">See also</span></span>

- [<span data-ttu-id="4d827-147">Abfragen</span><span class="sxs-lookup"><span data-stu-id="4d827-147">Queries</span></span>](index.md)
- [<span data-ttu-id="4d827-148">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4d827-148">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4d827-149">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d827-149">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="4d827-150">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4d827-150">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="4d827-151">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-151">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="4d827-152">WHERE-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-152">Where Clause</span></span>](where-clause.md)
- [<span data-ttu-id="4d827-153">Aggregate Clause</span><span class="sxs-lookup"><span data-stu-id="4d827-153">Aggregate Clause</span></span>](aggregate-clause.md)
- [<span data-ttu-id="4d827-154">Distinct-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-154">Distinct Clause</span></span>](distinct-clause.md)
- [<span data-ttu-id="4d827-155">Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-155">Join Clause</span></span>](join-clause.md)
- [<span data-ttu-id="4d827-156">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-156">Group Join Clause</span></span>](group-join-clause.md)
- [<span data-ttu-id="4d827-157">Order By-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-157">Order By Clause</span></span>](order-by-clause.md)
- [<span data-ttu-id="4d827-158">Let-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-158">Let Clause</span></span>](let-clause.md)
- [<span data-ttu-id="4d827-159">Skip-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-159">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="4d827-160">Take-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-160">Take Clause</span></span>](take-clause.md)
- [<span data-ttu-id="4d827-161">SkipWhile-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-161">Skip While Clause</span></span>](skip-while-clause.md)
- [<span data-ttu-id="4d827-162">TakeWhile-Klausel</span><span class="sxs-lookup"><span data-stu-id="4d827-162">Take While Clause</span></span>](take-while-clause.md)
