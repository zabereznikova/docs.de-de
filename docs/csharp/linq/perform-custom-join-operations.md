---
title: Ausführen von benutzerdefinierten JOIN-Vorgängen (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie benutzerdefinierte LINQ-JOIN-Vorgänge in C# ausführen.
ms.date: 12/01/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: 7051007c67bd64cd11ede2f4d5352ce3d497255f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61659851"
---
# <a name="perform-custom-join-operations"></a><span data-ttu-id="757fe-103">Ausführen von benutzerdefinierten Verknüpfungsoperationen</span><span class="sxs-lookup"><span data-stu-id="757fe-103">Perform custom join operations</span></span>

<span data-ttu-id="757fe-104">Dieses Beispiel veranschaulicht, wie Sie JOIN-Vorgänge ausführen, die nicht mit der `join`-Klausel ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="757fe-104">This example shows how to perform join operations that aren't possible with the `join` clause.</span></span> <span data-ttu-id="757fe-105">In einem Abfrageausdruck ist die `join`-Klausel auf Gleichheitsverknüpfungen, den bei weitem häufigsten Typ einer Verknüpfungsoperation, beschränkt und dafür optimiert.</span><span class="sxs-lookup"><span data-stu-id="757fe-105">In a query expression, the `join` clause is limited to, and optimized for, equijoins, which are by far the most common type of join operation.</span></span> <span data-ttu-id="757fe-106">Wenn eine Gleichheitsverknüpfung ausgeführt wird, erhalten Sie die beste Leistung wahrscheinlich immer mit der `join`-Klausel.</span><span class="sxs-lookup"><span data-stu-id="757fe-106">When performing an equijoin, you will probably always get the best performance by using the `join` clause.</span></span>

<span data-ttu-id="757fe-107">Die `join`-Klausel kann jedoch nicht in den folgenden Fällen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="757fe-107">However, the `join` clause cannot be used in the following cases:</span></span>

- <span data-ttu-id="757fe-108">Wenn die Verknüpfung auf einem Ausdruck der Ungleichheit basiert (eine Ungleichheitsverknüpfung)</span><span class="sxs-lookup"><span data-stu-id="757fe-108">When the join is predicated on an expression of inequality (a non-equijoin).</span></span>

- <span data-ttu-id="757fe-109">Wenn die Verknüpfung auf mehr als einem Ausdruck der Gleich- oder Ungleichheit basiert</span><span class="sxs-lookup"><span data-stu-id="757fe-109">When the join is predicated on more than one expression of equality or inequality.</span></span>

- <span data-ttu-id="757fe-110">Wenn Sie eine temporäre Bereichsvariable für die rechte (innere) Sequenz vor der Verknüpfungsoperation einführen müssen.</span><span class="sxs-lookup"><span data-stu-id="757fe-110">When you have to introduce a temporary range variable for the right side (inner) sequence before the join operation.</span></span>

 <span data-ttu-id="757fe-111">Wenn Sie Verknüpfungen ausführen möchten, die keine Gleichheitsverknüpfungen sind, können Sie mehrere `from`-Klauseln verwenden, um jede Datenquelle einzeln einzuführen.</span><span class="sxs-lookup"><span data-stu-id="757fe-111">To perform joins that aren't equijoins, you can use multiple `from` clauses to introduce each data source independently.</span></span> <span data-ttu-id="757fe-112">Sie wenden anschließend einen Prädikatsausdruck in einer `where`-Klausel auf die Bereichsvariable für jede Quelle an.</span><span class="sxs-lookup"><span data-stu-id="757fe-112">You then apply a predicate expression in a `where` clause to the range variable for each source.</span></span> <span data-ttu-id="757fe-113">Der Ausdruck kann auch die Form eines Methodenaufrufs annehmen.</span><span class="sxs-lookup"><span data-stu-id="757fe-113">The expression also can take the form of a method call.</span></span>

> [!NOTE]
> <span data-ttu-id="757fe-114">Verwechseln Sie diese Art des benutzerdefinierten JOIN-Vorgangs nicht mit der Verwendung mehrerer `from`-Klauseln für den Zugriff auf interne Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="757fe-114">Don't confuse this kind of custom join operation with the use of multiple `from` clauses to access inner collections.</span></span> <span data-ttu-id="757fe-115">Weitere Informationen finden Sie unter [join-Klausel](../language-reference/keywords/join-clause.md).</span><span class="sxs-lookup"><span data-stu-id="757fe-115">For more information, see [join clause](../language-reference/keywords/join-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="757fe-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="757fe-116">Example</span></span>

<span data-ttu-id="757fe-117">Die erste Methode im folgenden Beispiel zeigt eine einfache Kreuzverknüpfung.</span><span class="sxs-lookup"><span data-stu-id="757fe-117">The first method in the following example shows a simple cross join.</span></span> <span data-ttu-id="757fe-118">Kreuzverknüpfungen müssen mit Bedacht verwendet werden, da sie einen sehr großen Ergebnissatz erzeugen können.</span><span class="sxs-lookup"><span data-stu-id="757fe-118">Cross joins must be used with caution because they can produce very large result sets.</span></span> <span data-ttu-id="757fe-119">Sie können jedoch in manchen Szenarios nützlich sein, um Quellsequenzen zu erstellen, mit denen zusätzliche Abfragen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="757fe-119">However, they can be useful in some scenarios for creating source sequences against which additional queries are run.</span></span>

<span data-ttu-id="757fe-120">Die zweite Methode erzeugt eine Sequenz aller Produkte, deren Kategorie-ID in der Kategorieliste auf der linken Seite aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="757fe-120">The second method produces a sequence of all the products whose category ID is listed in the category list on the left side.</span></span> <span data-ttu-id="757fe-121">Beachten Sie, dass Sie mit der Verwendung der `let`-Klausel und der `Contains`-Methode ein temporäres Array erstellen.</span><span class="sxs-lookup"><span data-stu-id="757fe-121">Note the use of the `let` clause and the `Contains` method to create a temporary array.</span></span> <span data-ttu-id="757fe-122">Es ist auch möglich, das Array vor der Abfrage zu erstellen und die erste `from`-Klausel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="757fe-122">It also is possible to create the array before the query and eliminate the first `from` clause.</span></span>

[!code-csharp[csProgGuideLINQ#64](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]

## <a name="example"></a><span data-ttu-id="757fe-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="757fe-123">Example</span></span>

<span data-ttu-id="757fe-124">Im folgenden Beispiel muss die Abfrage zwei Sequenzen anhand übereinstimmender Schlüssel verknüpfen, die bei der inneren (rechten) Sequenz nicht vor der eigentlichen Join-Klausel abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="757fe-124">In the following example, the query must join two sequences based on matching keys that, in the case of the inner (right side) sequence, cannot be obtained prior to the join clause itself.</span></span> <span data-ttu-id="757fe-125">Wenn diese Verknüpfung mit einer `join`-Klausel ausgeführt werden würde, müsste anschließend die `Split`-Methode für jedes Element aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="757fe-125">If this join were performed with a `join` clause, then the `Split` method would have to be called for each element.</span></span> <span data-ttu-id="757fe-126">Mit der Verwendung von mehreren `from`-Klauseln kann die Abfrage den Mehraufwand des wiederholten Methodenaufrufs vermeiden.</span><span class="sxs-lookup"><span data-stu-id="757fe-126">The use of multiple `from` clauses enables the query to avoid the overhead of the repeated method call.</span></span> <span data-ttu-id="757fe-127">Da `join` jedoch optimiert ist, könnte es in diesem Sonderfall trotzdem schneller sein als mehrere `from`-Klauseln zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="757fe-127">However, since `join` is optimized, in this particular case it might still be faster than using multiple `from` clauses.</span></span> <span data-ttu-id="757fe-128">Die Ergebnisse variieren hauptsächlich nach Aufwand des Methodenaufrufs.</span><span class="sxs-lookup"><span data-stu-id="757fe-128">The results will vary depending primarily on how expensive the method call is.</span></span>

[!code-csharp[csProgGuideLINQ#13](~/samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]

## <a name="see-also"></a><span data-ttu-id="757fe-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="757fe-129">See also</span></span>

- [<span data-ttu-id="757fe-130">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="757fe-130">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="757fe-131">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="757fe-131">join clause</span></span>](../language-reference/keywords/join-clause.md)
- [<span data-ttu-id="757fe-132">Sortieren der Ergebnisse einer Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="757fe-132">Order the results of a join clause</span></span>](order-the-results-of-a-join-clause.md)
