---
title: Where-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: b80bb047551dee8ab23cfac06b961996992d69b5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359540"
---
# <a name="where-clause-visual-basic"></a><span data-ttu-id="9cf96-102">Where-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9cf96-102">Where Clause (Visual Basic)</span></span>
<span data-ttu-id="9cf96-103">Gibt die Filterbedingung für eine Abfrage an.</span><span class="sxs-lookup"><span data-stu-id="9cf96-103">Specifies the filtering condition for a query.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf96-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cf96-104">Syntax</span></span>  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a><span data-ttu-id="9cf96-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="9cf96-105">Parts</span></span>  
 `condition`  
 <span data-ttu-id="9cf96-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="9cf96-106">Required.</span></span> <span data-ttu-id="9cf96-107">Ein Ausdruck, der bestimmt, ob die Werte für das aktuelle Element in der Auflistung in der Ausgabe Auflistung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9cf96-107">An expression that determines whether the values for the current item in the collection are included in the output collection.</span></span> <span data-ttu-id="9cf96-108">Der Ausdruck muss zu einem- `Boolean` Wert oder dem-Äquivalent eines-Werts ausgewertet werden `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="9cf96-108">The expression must evaluate to a `Boolean` value or the equivalent of a `Boolean` value.</span></span> <span data-ttu-id="9cf96-109">Wenn die Bedingung ergibt `True` , wird das-Element in das Abfrageergebnis eingeschlossen. andernfalls wird das-Element aus dem Abfrageergebnis ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9cf96-109">If the condition evaluates to `True`, the element is included in the query result; otherwise, the element is excluded from the query result.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9cf96-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9cf96-110">Remarks</span></span>  
 <span data-ttu-id="9cf96-111">Mit der- `Where` Klausel können Sie Abfrage Daten filtern, indem Sie nur Elemente auswählen, die bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9cf96-111">The `Where` clause enables you to filter query data by selecting only elements that meet certain criteria.</span></span> <span data-ttu-id="9cf96-112">Elemente, deren Werte bewirken, dass die- `Where` Klausel ausgewertet `True` wird, werden in das Abfrageergebnis eingeschlossen. andere Elemente werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9cf96-112">Elements whose values cause the `Where` clause to evaluate to `True` are included in the query result; other elements are excluded.</span></span> <span data-ttu-id="9cf96-113">Der Ausdruck, der in einer-Klausel verwendet wird, `Where` muss zu einer `Boolean` oder der-Entsprechung von ausgewertet `Boolean` werden, z. b. eine ganze Zahl, die ergibt, `False` Wenn der Wert NULL ist.</span><span class="sxs-lookup"><span data-stu-id="9cf96-113">The expression that is used in a `Where` clause must evaluate to a `Boolean` or the equivalent of a `Boolean`, such as an Integer that evaluates to `False` when its value is zero.</span></span> <span data-ttu-id="9cf96-114">Sie können mehrere Ausdrücke in einer- `Where` Klausel kombinieren, indem Sie logische Operatoren wie `And` , `Or` , `AndAlso` , `OrElse` , `Is` und verwenden `IsNot` .</span><span class="sxs-lookup"><span data-stu-id="9cf96-114">You can combine multiple expressions in a `Where` clause by using logical operators such as `And`, `Or`, `AndAlso`, `OrElse`, `Is`, and `IsNot`.</span></span>  
  
 <span data-ttu-id="9cf96-115">Standardmäßig werden Abfrage Ausdrücke erst ausgewertet, wenn auf Sie zugegriffen wird – z. b. Wenn Sie in einer-Schleife Daten gebunden oder durchlaufen haben `For` .</span><span class="sxs-lookup"><span data-stu-id="9cf96-115">By default, query expressions are not evaluated until they are accessed—for example, when they are data-bound or iterated through in a `For` loop.</span></span> <span data-ttu-id="9cf96-116">Folglich wird die- `Where` Klausel erst ausgewertet, wenn auf die Abfrage zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9cf96-116">As a result, the `Where` clause is not evaluated until the query is accessed.</span></span> <span data-ttu-id="9cf96-117">Wenn Sie Werte außerhalb der Abfrage haben, die in der-Klausel verwendet werden `Where` , stellen Sie sicher, dass der entsprechende Wert in der- `Where` Klausel zum Zeitpunkt der Abfrage Ausführung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9cf96-117">If you have values external to the query that are used in the `Where` clause, ensure that the appropriate value is used in the `Where` clause at the time the query is executed.</span></span> <span data-ttu-id="9cf96-118">Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="9cf96-118">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
 <span data-ttu-id="9cf96-119">Sie können Funktionen innerhalb einer- `Where` Klausel aufzurufen, um eine Berechnung oder einen Vorgang für einen Wert aus dem aktuellen Element in der Auflistung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9cf96-119">You can call functions within a `Where` clause to perform a calculation or operation on a value from the current element in the collection.</span></span> <span data-ttu-id="9cf96-120">Das Aufrufen einer Funktion in einer- `Where` Klausel kann bewirken, dass die Abfrage sofort ausgeführt wird, wenn Sie definiert wird, und nicht, wenn darauf zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="9cf96-120">Calling a function in a `Where` clause can cause the query to be executed immediately when it is defined instead of when it is accessed.</span></span> <span data-ttu-id="9cf96-121">Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="9cf96-121">For more information about query execution, see [Writing Your First LINQ Query](../../programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cf96-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cf96-122">Example</span></span>  
 <span data-ttu-id="9cf96-123">Der folgende Abfrage Ausdruck verwendet eine- `From` Klausel, um eine Bereichs Variable `cust` für jedes `Customer` Objekt in der Auflistung zu deklarieren `customers` .</span><span class="sxs-lookup"><span data-stu-id="9cf96-123">The following query expression uses a `From` clause to declare a range variable `cust` for each `Customer` object in the `customers` collection.</span></span> <span data-ttu-id="9cf96-124">Die- `Where` Klausel verwendet die Range-Variable, um die Ausgabe auf Kunden aus dem angegebenen Bereich zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="9cf96-124">The `Where` clause uses the range variable to restrict the output to customers from the specified region.</span></span> <span data-ttu-id="9cf96-125">In der- `For Each` Schleife wird der Firmenname für jeden Kunden im Abfrageergebnis angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9cf96-125">The `For Each` loop displays the company name for each customer in the query result.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a><span data-ttu-id="9cf96-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9cf96-126">Example</span></span>  
 <span data-ttu-id="9cf96-127">Im folgenden Beispiel werden `And` die `Or` logischen Operatoren und in der- `Where` Klausel verwendet.</span><span class="sxs-lookup"><span data-stu-id="9cf96-127">The following example uses `And` and `Or` logical operators in the `Where` clause.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="9cf96-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9cf96-128">See also</span></span>

- [<span data-ttu-id="9cf96-129">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9cf96-129">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="9cf96-130">Abfragen</span><span class="sxs-lookup"><span data-stu-id="9cf96-130">Queries</span></span>](index.md)
- [<span data-ttu-id="9cf96-131">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="9cf96-131">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="9cf96-132">SELECT-Klausel</span><span class="sxs-lookup"><span data-stu-id="9cf96-132">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="9cf96-133">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9cf96-133">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
