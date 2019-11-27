---
title: Join-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b0baca9f897a00b3c6c67699629477ff385d6ef7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353266"
---
# <a name="join-clause-visual-basic"></a><span data-ttu-id="4dbba-102">Join-Klausel (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4dbba-102">Join Clause (Visual Basic)</span></span>

<span data-ttu-id="4dbba-103">Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen.</span><span class="sxs-lookup"><span data-stu-id="4dbba-103">Combines two collections into a single collection.</span></span> <span data-ttu-id="4dbba-104">Der Joinvorgang basiert auf übereinstimmenden Schlüsseln und verwendet den `Equals`-Operator.</span><span class="sxs-lookup"><span data-stu-id="4dbba-104">The join operation is based on matching keys and uses the `Equals` operator.</span></span>

## <a name="syntax"></a><span data-ttu-id="4dbba-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dbba-105">Syntax</span></span>

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a><span data-ttu-id="4dbba-106">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="4dbba-106">Parts</span></span>

<span data-ttu-id="4dbba-107">`element` ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dbba-107">`element` Required.</span></span> <span data-ttu-id="4dbba-108">Die Steuerelement Variable für die Auflistung, die verknüpft wird.</span><span class="sxs-lookup"><span data-stu-id="4dbba-108">The control variable for the collection being joined.</span></span>

`collection`  
<span data-ttu-id="4dbba-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4dbba-109">Required.</span></span> <span data-ttu-id="4dbba-110">Die Auflistung, die mit der auf der linken Seite des `Join` Operators identifizierten Auflistung kombiniert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4dbba-110">The collection to combine with the collection identified on the left side of the `Join` operator.</span></span> <span data-ttu-id="4dbba-111">Eine `Join`-Klausel kann in einer anderen `Join`-Klausel oder in einer `Group Join`-Klausel eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="4dbba-111">A `Join` clause can be nested in another `Join` clause, or in a `Group Join` clause.</span></span>

`joinClause`  
<span data-ttu-id="4dbba-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dbba-112">Optional.</span></span> <span data-ttu-id="4dbba-113">Mindestens eine zusätzliche `Join`-Klausel, um die Abfrage weiter zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="4dbba-113">One or more additional `Join` clauses to further refine the query.</span></span>

`groupJoinClause`  
<span data-ttu-id="4dbba-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dbba-114">Optional.</span></span> <span data-ttu-id="4dbba-115">Mindestens eine zusätzliche `Group Join`-Klausel, um die Abfrage weiter zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="4dbba-115">One or more additional `Group Join` clauses to further refine the query.</span></span>

<span data-ttu-id="4dbba-116">`key1` `Equals` `key2`</span><span class="sxs-lookup"><span data-stu-id="4dbba-116">`key1` `Equals` `key2`</span></span>  
<span data-ttu-id="4dbba-117">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4dbba-117">Required.</span></span> <span data-ttu-id="4dbba-118">Identifiziert Schlüssel für die Auflistungen, die verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="4dbba-118">Identifies keys for the collections being joined.</span></span> <span data-ttu-id="4dbba-119">Sie müssen den `Equals`-Operator verwenden, um Schlüssel aus den Auflistungen zu vergleichen, die verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="4dbba-119">You must use the `Equals` operator to compare keys from the collections being joined.</span></span> <span data-ttu-id="4dbba-120">Joinbedingungen können mithilfe des `And`-Operators kombiniert werden, um mehrere Schlüssel zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4dbba-120">You can combine join conditions by using the `And` operator to identify multiple keys.</span></span> <span data-ttu-id="4dbba-121">`key1` muss von der Auflistung auf der linken Seite des `Join` Operators sein.</span><span class="sxs-lookup"><span data-stu-id="4dbba-121">`key1` must be from the collection on the left side of the `Join` operator.</span></span> <span data-ttu-id="4dbba-122">`key2` muss von der Auflistung auf der rechten Seite des `Join` Operators sein.</span><span class="sxs-lookup"><span data-stu-id="4dbba-122">`key2` must be from the collection on the right side of the `Join` operator.</span></span>

<span data-ttu-id="4dbba-123">Die in der Join-Bedingung verwendeten Schlüssel können Ausdrücke sein, die mehr als ein Element aus der Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="4dbba-123">The keys used in the join condition can be expressions that include more than one item from the collection.</span></span> <span data-ttu-id="4dbba-124">Jeder Schlüssel Ausdruck kann jedoch nur Elemente aus der jeweiligen Auflistung enthalten.</span><span class="sxs-lookup"><span data-stu-id="4dbba-124">However, each key expression can contain only items from its respective collection.</span></span>

## <a name="remarks"></a><span data-ttu-id="4dbba-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4dbba-125">Remarks</span></span>

<span data-ttu-id="4dbba-126">Die `Join`-Klausel kombiniert zwei Auflistungen basierend auf übereinstimmenden Schlüsselwerten aus den verbundenen Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="4dbba-126">The `Join` clause combines two collections based on matching key values from the collections being joined.</span></span> <span data-ttu-id="4dbba-127">Die resultierende Auflistung kann eine beliebige Kombination von Werten aus der Auflistung enthalten, die auf der linken Seite des `Join` Operators und der in der `Join`-Klausel identifizierten Auflistung identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="4dbba-127">The resulting collection can contain any combination of values from the collection identified on the left side of the `Join` operator and the collection identified in the `Join` clause.</span></span> <span data-ttu-id="4dbba-128">Die Abfrage gibt nur Ergebnisse zurück, für die die vom `Equals` Operator angegebene Bedingung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="4dbba-128">The query will return only results for which the condition specified by the `Equals` operator is met.</span></span> <span data-ttu-id="4dbba-129">Dies entspricht einer `INNER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="4dbba-129">This is equivalent to an `INNER JOIN` in SQL.</span></span>

<span data-ttu-id="4dbba-130">Sie können mehrere `Join` Klauseln in einer Abfrage verwenden, um zwei oder mehr Auflistungen in einer einzelnen Auflistung zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="4dbba-130">You can use multiple `Join` clauses in a query to join two or more collections into a single collection.</span></span>

<span data-ttu-id="4dbba-131">Sie können einen impliziten Join ausführen, um Auflistungen ohne die `Join`-Klausel zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="4dbba-131">You can perform an implicit join to combine collections without the `Join` clause.</span></span> <span data-ttu-id="4dbba-132">Fügen Sie zu diesem Zweck mehrere `In`-Klauseln in Ihre `From`-Klausel ein, und geben Sie eine `Where`-Klausel an, die die Schlüssel angibt, die Sie für den Join verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4dbba-132">To do this, include multiple `In` clauses in your `From` clause and specify a `Where` clause that identifies the keys that you want to use for the join.</span></span>

<span data-ttu-id="4dbba-133">Sie können die `Group Join`-Klausel verwenden, um Auflistungen in einer einzelnen hierarchischen Auflistung zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="4dbba-133">You can use the `Group Join` clause to combine collections into a single hierarchical collection.</span></span> <span data-ttu-id="4dbba-134">Dies ist wie eine `LEFT OUTER JOIN` in SQL.</span><span class="sxs-lookup"><span data-stu-id="4dbba-134">This is like a `LEFT OUTER JOIN` in SQL.</span></span>

## <a name="example"></a><span data-ttu-id="4dbba-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dbba-135">Example</span></span>

<span data-ttu-id="4dbba-136">Im folgenden Codebeispiel wird ein impliziter Join durchführt, um eine Liste von Kunden mit Ihren Aufträgen zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="4dbba-136">The following code example performs an implicit join to combine a list of customers with their orders.</span></span>

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a><span data-ttu-id="4dbba-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dbba-137">Example</span></span>

<span data-ttu-id="4dbba-138">Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der `Join`-Klausel miteinander verbunden.</span><span class="sxs-lookup"><span data-stu-id="4dbba-138">The following code example joins two collections by using the `Join` clause.</span></span>

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

<span data-ttu-id="4dbba-139">In diesem Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="4dbba-139">This example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a><span data-ttu-id="4dbba-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dbba-140">Example</span></span>

<span data-ttu-id="4dbba-141">Im folgenden Codebeispiel werden zwei Auflistungen mithilfe der `Join`-Klausel mit zwei Schlüssel Spalten verbunden.</span><span class="sxs-lookup"><span data-stu-id="4dbba-141">The following code example joins two collections by using the `Join` clause with two key columns.</span></span>

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

<span data-ttu-id="4dbba-142">Im Beispiel wird eine Ausgabe ähnlich der folgenden erzeugt:</span><span class="sxs-lookup"><span data-stu-id="4dbba-142">The example will produce output similar to the following:</span></span>

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a><span data-ttu-id="4dbba-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dbba-143">See also</span></span>

- [<span data-ttu-id="4dbba-144">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4dbba-144">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="4dbba-145">Abfragen</span><span class="sxs-lookup"><span data-stu-id="4dbba-145">Queries</span></span>](../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="4dbba-146">Select-Klausel</span><span class="sxs-lookup"><span data-stu-id="4dbba-146">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
- [<span data-ttu-id="4dbba-147">From-Klausel</span><span class="sxs-lookup"><span data-stu-id="4dbba-147">From Clause</span></span>](../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="4dbba-148">Group Join-Klausel</span><span class="sxs-lookup"><span data-stu-id="4dbba-148">Group Join Clause</span></span>](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [<span data-ttu-id="4dbba-149">Where-Klausel</span><span class="sxs-lookup"><span data-stu-id="4dbba-149">Where Clause</span></span>](../../../visual-basic/language-reference/queries/where-clause.md)
