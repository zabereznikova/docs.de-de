---
title: "Ausführen von benutzerdefinierten Verknüpfungsoperationen"
description: "So führen Sie benutzerdefinierte Verknüpfungsoperationen aus."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: fef146c92a5cbbf21f8f1688f221c2bd45c99de7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="31447-104">Ausführen von benutzerdefinierten Verknüpfungsoperationen</span><span class="sxs-lookup"><span data-stu-id="31447-104">Perform custom join operations</span></span>

<span data-ttu-id="31447-105">In diesem Beispiel wird gezeigt, wie Verknüpfungsoperationen ausgeführt werden, die nicht mit der `join`-Klausel möglich sind.</span><span class="sxs-lookup"><span data-stu-id="31447-105">This example shows how to perform join operations that are not possible with the `join` clause.</span></span> <span data-ttu-id="31447-106">In einem Abfrageausdruck ist die `join`-Klausel auf Gleichheitsverknüpfungen, den bei weitem häufigsten Typ einer Verknüpfungsoperation, beschränkt und dafür optimiert.</span><span class="sxs-lookup"><span data-stu-id="31447-106">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="31447-107">Wenn eine Gleichheitsverknüpfung ausgeführt wird, erhalten Sie die beste Leistung wahrscheinlich immer mit der `join`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="31447-107">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>  
  
 <span data-ttu-id="31447-108">Die `join`-Klausel kann jedoch nicht in den folgenden Fällen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="31447-108">However, the `join` clause cannot be used in the following cases:</span></span>  
  
-   <span data-ttu-id="31447-109">Wenn die Verknüpfung auf einem Ausdruck der Ungleichheit basiert (eine Ungleichheitsverknüpfung)</span><span class="sxs-lookup"><span data-stu-id="31447-109">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>  
  
-   <span data-ttu-id="31447-110">Wenn die Verknüpfung auf mehr als einem Ausdruck der Gleich- oder Ungleichheit basiert</span><span class="sxs-lookup"><span data-stu-id="31447-110">When the join is predicated on more than one expression of equality or inequality.</span></span>  
  
-   <span data-ttu-id="31447-111">Wenn Sie eine temporäre Bereichsvariable für die rechte (innere) Sequenz vor der Verknüpfungsoperation einführen müssen.</span><span class="sxs-lookup"><span data-stu-id="31447-111">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>  
  
 <span data-ttu-id="31447-112">Sie können zum Ausführen von Verknüpfungen, die keine Gleichheitsverknüpfungen sind, mehrere `from`-Klauseln verwenden, um jede Datenquelle einzeln einzuführen.</span><span class="sxs-lookup"><span data-stu-id="31447-112">To perform joins that are not equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="31447-113">Sie wenden anschließend einen Prädikatsausdruck in einer `where`-Klausel auf die Bereichsvariable für jede Quelle an.</span><span class="sxs-lookup"><span data-stu-id="31447-113">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="31447-114">Der Ausdruck kann auch die Form eines Methodenaufrufs annehmen.</span><span class="sxs-lookup"><span data-stu-id="31447-114">The expression also can take the form of a method call.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="31447-115">Verwechseln Sie diese Art der benutzerdefinierten Verknüpfungsoperationen nicht mit der Verwendung mehrerer `from`-Klauseln, um auf innere Auflistungen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="31447-115">Do not confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="31447-116">Weitere Informationen finden Sie unter [Join-Klausel](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="31447-116">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31447-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31447-117">Example</span></span>  
 <span data-ttu-id="31447-118">Die erste Methode im folgenden Beispiel zeigt eine einfache Kreuzverknüpfung.</span><span class="sxs-lookup"><span data-stu-id="31447-118">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="31447-119">Kreuzverknüpfungen müssen mit Bedacht verwendet werden, da sie einen sehr großen Ergebnissatz erzeugen können.</span><span class="sxs-lookup"><span data-stu-id="31447-119">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="31447-120">Sie können jedoch in manchen Szenarios nützlich sein, um Quellsequenzen zu erstellen, mit denen zusätzliche Abfragen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="31447-120">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>  
  
 <span data-ttu-id="31447-121">Die zweite Methode erzeugt eine Sequenz aller Produkte, deren Kategorie-ID in der Kategorieliste auf der linken Seite aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="31447-121">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="31447-122">Beachten Sie, dass Sie mit der Verwendung der `let`-Klausel und der `Contains`-Methode ein temporäres Array erstellen.</span><span class="sxs-lookup"><span data-stu-id="31447-122">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="31447-123">Es ist auch möglich, das Array vor der Abfrage zu erstellen und die erste `from`-Klausel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="31447-123">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="31447-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31447-124">Example</span></span>  
 <span data-ttu-id="31447-125">Im folgenden Beispiel muss die Abfrage zwei Sequenzen anhand übereinstimmender Schlüssel verknüpfen, die bei der inneren (rechten) Sequenz nicht vor der eigentlichen Join-Klausel abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="31447-125">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="31447-126">Wenn diese Verknüpfung mit einer `join`-Klausel ausgeführt werden würde, müsste anschließend die `Split`-Methode für jedes Element aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="31447-126">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="31447-127">Mit der Verwendung von mehreren `from`-Klauseln kann die Abfrage den Mehraufwand des wiederholten Methodenaufrufs vermeiden.</span><span class="sxs-lookup"><span data-stu-id="31447-127">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="31447-128">Da `join` jedoch optimiert ist, könnte es in diesem Sonderfall trotzdem schneller sein als mehrere `from`-Klauseln zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="31447-128">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="31447-129">Die Ergebnisse variieren hauptsächlich nach Aufwand des Methodenaufrufs.</span><span class="sxs-lookup"><span data-stu-id="31447-129">The results will vary depending primarily on how expensive the method call is.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="31447-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31447-130">See also</span></span>  
 [<span data-ttu-id="31447-131">LINQ-Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="31447-131">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="31447-132">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="31447-132">join clause</span></span>](../language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="31447-133">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="31447-133">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
