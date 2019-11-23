---
title: Where-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004999"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="a259a-102">Where-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a259a-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="a259a-103">Gibt die Filterbedingung für eine Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="a259a-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a259a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a259a-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="a259a-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="a259a-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="a259a-106">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="a259a-106">Required.</span></span> <span data-ttu-id="a259a-107">Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Ausgabe Auflistung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a259a-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="a259a-108">Der Ausdruck muss zu einem `Boolean` Wert oder der Entsprechung eines `Boolean` Werts ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="a259a-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="a259a-109">Wenn die Bedingung als `True`ausgewertet wird, wird das Element in das Abfrageergebnis eingeschlossen. Andernfalls wird das-Element aus dem Abfrageergebnis ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a259a-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a259a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a259a-110">Remarks</span></span>  
 <span data-ttu-id="a259a-111">Mit der `Where`-Klausel können Sie Abfrage Daten filtern, indem Sie nur Elemente auswählen, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a259a-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="a259a-112">Elemente, deren Werte bewirken, dass die `Where`-Klausel zu `True` ausgewertet wird, sind im Abfrageergebnis enthalten. andere Elemente werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a259a-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="a259a-113">Der Ausdruck, der in einer `Where`-Klausel verwendet wird, muss zu einem `Boolean` oder dem Äquivalent eines `Boolean`ausgewertet werden, z. b. eine ganze Zahl, die `False` ergibt, wenn der Wert 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="a259a-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="a259a-114">Sie können mehrere Ausdrücke in einer `Where`-Klausel kombinieren, indem Sie logische Operatoren wie z. b. `And`, `Or`, `AndAlso`, `OrElse`, `Is`und `IsNot`verwenden.</span><span class="sxs-lookup"><span data-stu-id="a259a-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="a259a-115">Standardmäßig werden Abfrage Ausdrücke erst ausgewertet, wenn auf Sie zugegriffen wird – z. b. Wenn Sie in einer `For` Schleife Daten gebunden oder durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="a259a-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="a259a-116">Folglich wird die `Where`-Klausel erst ausgewertet, wenn auf die Abfrage zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a259a-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="a259a-117">Wenn Sie Werte außerhalb der Abfrage haben, die in der `Where`-Klausel verwendet werden, stellen Sie sicher, dass der entsprechende Wert in der `Where`-Klausel zum Zeitpunkt der Abfrage Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a259a-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="a259a-118">Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="a259a-118">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="a259a-119">Sie können Funktionen innerhalb einer `Where`-Klausel aufzurufen, um eine Berechnung oder einen Vorgang für einen Wert aus dem aktuellen Element in der Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a259a-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="a259a-120">Wenn Sie eine Funktion in einer `Where`-Klausel aufrufen, kann dies dazu führen, dass die Abfrage sofort ausgeführt wird, wenn Sie definiert wird, anstatt dass Sie aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a259a-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="a259a-121">Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="a259a-121">For more information about query execution, see [Writing Your First LINQ Query](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a259a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a259a-122">Example</span></span>  
 <span data-ttu-id="a259a-123">Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um für jedes `Customer`-Objekt in der `customers` Auflistung eine Bereichs Variable `cust` zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a259a-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="a259a-124">Die `Where`-Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="a259a-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="a259a-125">Die `For Each`-Schleife zeigt den Firmennamen für jeden Kunden im Abfrageergebnis an.</span><span class="sxs-lookup"><span data-stu-id="a259a-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="a259a-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a259a-126">Example</span></span>  
 <span data-ttu-id="a259a-127">Im folgenden Beispiel werden die logischen Operatoren `And` und `Or` in der `Where`-Klausel verwendet.</span><span class="sxs-lookup"><span data-stu-id="a259a-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="a259a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a259a-128">See also</span></span>

- [<span data-ttu-id="a259a-129">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a259a-129">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="a259a-130">Abfragen</span><span class="sxs-lookup"><span data-stu-id="a259a-130">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="a259a-131">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="a259a-131">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="a259a-132">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="a259a-132">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="a259a-133">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a259a-133">For Each...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
